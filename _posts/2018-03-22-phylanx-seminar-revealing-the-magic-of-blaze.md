---
layout: post
title:  "Phylanx Seminar: Revealing the Magic of Blaze"
date:   2018-03-22 00:00:00 -0500
author: Adrian Serio
categories: [Phylanx, Seminar]
tags: [Phylanx, PhySL, Seminar, Video]
---
Over the past several weeks, many team members have been asking how
aspects of the Phylanx project are implemented. In this seminar, 
Hartmut explains the techniques used by Blaze to optimize matrix
operations. He implements a matrix addition example which uses types,
templates, and curiously recurring template patterns (CRTP) to reduce
the number of temporaries made during the execution of the code. By
avoiding these extra allocations in a compiler friendly way, Blaze can
drastically reduce the amount of time it takes perform matrix
operations. You can find links to the seminar materials below:


### Seminar Video

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/F5E8cOqHmRU?rel=0" frameborder="0" allowfullscreen="true"></iframe>

Link: <https://youtu.be/F5E8cOqHmRU>

### Code

#### Naive Matrix Implementation:

```cpp

#include <stdexcept>
#include <iostream>
#include <vector>

///////////////////////////////////////////////////////////////////////////////
std::size_t count = 0;

///////////////////////////////////////////////////////////////////////////////
struct matrix
{
    matrix(std::size_t rows, std::size_t columns)
      : rows_(rows)
      , columns_(columns)
      , data_(rows * columns)
    {
        ++count;
    }

    matrix(std::size_t rows, std::size_t columns, std::initializer_list<double> data)
      : rows_(rows)
      , columns_(columns)
      , data_(std::move(data))
    {
        ++count;
    }

    std::size_t rows() const { return rows_; }
    std::size_t columns() const { return columns_; }

    double get(std::size_t r, std::size_t c) const
    {
        return data_[r * columns_ + c];
    }
    void set(std::size_t r, std::size_t c, double v)
    {
        data_[r * columns_ + c] = v;
    }

private:
    std::size_t rows_;
    std::size_t columns_;
    std::vector<double> data_;
};

std::ostream& operator<<(std::ostream& out, matrix const& m)
{
    out << "[";
    for (std::size_t r = 0; r != m.rows(); ++r)
    {
        if (r != 0)
            out << ", ";

        out << "[";
        for (std::size_t c = 0; c != m.columns(); ++c)
        {
            if (c != 0)
                out << ", ";

            out << m.get(r, c);
        }
        out << "]";
    }
    out << "]";
    return out;
}

///////////////////////////////////////////////////////////////////////////////
matrix operator+ (matrix const& lhs, matrix const& rhs)
{
    if (lhs.rows() != rhs.rows() || lhs.columns() != rhs.columns())
    {
        throw std::runtime_error("add: size mismatch");
    }

    matrix result{lhs.rows(), lhs.columns()};
    for (std::size_t r = 0; r != lhs.rows(); ++r)
    {
        for (std::size_t c = 0; c != lhs.columns(); ++c)
        {
            result.set(r, c, lhs.get(r, c) + rhs.get(r, c));
        }
    }
    return result;
}

///////////////////////////////////////////////////////////////////////////////
int main(int argc, char* argv[])
{
    matrix m1 (2, 3, { 1, 2, 3, 4, 5, 6 });

    matrix result = m1 + m1 + m1 + m1;

    std::cout << result << "\n";
    std::cout << count << "\n";
    return 0;
}
```
Link: [(naive_matrix.cpp)](http://stellar.cct.lsu.edu/files/phylanx_seminars/03.21.18_seminar_blaze_magic/naive_matrix_03.21.18.cpp)

#### Optimized Matrix Implementation:

```cpp

#include <stdexcept>
#include <iostream>
#include <typeinfo>
#include <vector>

///////////////////////////////////////////////////////////////////////////////
std::size_t count = 0;

///////////////////////////////////////////////////////////////////////////////
template <typename T>
struct node
{
private:
    T& derived() { return static_cast<T&>(*this); }
    T const& derived() const { return static_cast<T const&>(*this); }

public:
    std::size_t rows() const { return derived().rows_impl(); }
    std::size_t columns() const { return derived().columns_impl(); }

    double get(std::size_t r, std::size_t c) const
    {
        return derived().get_impl(r, c);
    }
    void set(std::size_t r, std::size_t c, double v)
    {
        derived().set_impl(r, c, v);
    }
};

///////////////////////////////////////////////////////////////////////////////
struct matrix : node<matrix>
{
    matrix(std::size_t rows, std::size_t columns)
      : rows_(rows)
      , columns_(columns)
      , data_(rows * columns)
    {
        ++count;
    }

    matrix(std::size_t rows, std::size_t columns, std::initializer_list<double> data)
      : rows_(rows)
      , columns_(columns)
      , data_(std::move(data))
    {
        ++count;
    }

    std::size_t rows_impl() const { return rows_; }
    std::size_t columns_impl() const { return columns_; }

    double get_impl(std::size_t r, std::size_t c) const
    {
        return data_[r * columns_ + c];
    }
    void set_impl(std::size_t r, std::size_t c, double v)
    {
        data_[r * columns_ + c] = v;
    }

    template <typename T>
    matrix(node<T> const& rhs)
      : rows_(rhs.rows())
      , columns_(rhs.columns())
      , data_(rows_ * columns_)
    {
        ++count;

        for (std::size_t r = 0; r != rhs.rows(); ++r)
        {
            for (std::size_t c = 0; c != rhs.columns(); ++c)
            {
                set(r, c, rhs.get(r, c));
            }
        }
    }

    template <typename T>
    matrix& operator=(node<T> const& rhs)
    {
        data_.resize(rhs.rows() * rhs.columns());
        for (std::size_t r = 0; r != lhs.rows(); ++r)
        {
            for (std::size_t c = 0; c != lhs.columns(); ++c)
            {
                set(r, c, rhs.get(r, c));
            }
        }
        return *this;
    }

private:
    std::size_t rows_;
    std::size_t columns_;
    std::vector<double> data_;
};

template <typename T>
std::ostream& operator<<(std::ostream& out, node<T> const& m)
{
    out << "[";
    for (std::size_t r = 0; r != m.rows(); ++r)
    {
        if (r != 0)
            out << ", ";

        out << "[";
        for (std::size_t c = 0; c != m.columns(); ++c)
        {
            if (c != 0)
                out << ", ";

            out << m.get(r, c);
        }
        out << "]";
    }
    out << "]";
    return out;
}

///////////////////////////////////////////////////////////////////////////////
template <typename L, typename R>
struct add : node<add<L, R>>
{
    add(node<L> const& lhs, node<R> const& rhs)
      : lhs_(lhs)
      , rhs_(rhs)
    {
        if (lhs.rows() != rhs.rows() || lhs.columns() != rhs.columns())
        {
            throw std::runtime_error("add: size mismatch");
        }
    }

    std::size_t rows_impl() const { return lhs_.rows(); }
    std::size_t columns_impl() const { return rhs_.columns(); }

    double get_impl(std::size_t r, std::size_t c) const
    {
        return lhs_.get(r, c) + rhs_.get(r, c);
    }
    void set_impl(std::size_t r, std::size_t c, double v)
    {
        throw std::runtime_error("add: shouldn't be called");
    }

private:
    node<L> const& lhs_;
    node<R> const& rhs_;
};

///////////////////////////////////////////////////////////////////////////////
template <typename L, typename R>
add<L, R> operator+ (node<L> const& lhs, node<R> const& rhs)
{
    return add<L, R>{lhs, rhs};
}

///////////////////////////////////////////////////////////////////////////////
int main(int argc, char* argv[])
{
    matrix m1 (2, 3, { 1, 2, 3, 4, 5, 6 });

    auto result = m1 + m1 + m1 + m1;
    std::cout << typeid(result).name() << "\n";

    std::cout << matrix{result} << "\n";
    std::cout << count << "\n";
    return 0;
}
```
Link: [(optimized_matrix.cpp)](http://stellar.cct.lsu.edu/files/phylanx_seminars/03.21.18_seminar_blaze_magic/optimized_matrix_03.21.18.cpp)

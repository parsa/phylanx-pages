---
layout: post
title:  "Phylanx Seminar"
date:   2017-10-06 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Meeting, Seminar, Video]
---
Friday the Phylanx team at LSU held a seminar on the current theory, techniques, and methodology used by the Phylanx project. During the lecture Hartmut laid out the scope of the challenge we are trying to solve and the three components of the project as we have them today. Additionally, he explained the grammar we are using to describe expression trees and the current and future role Python is playing in the project.

You can watch the seminar, as well as, follow along with the overheads and examples provided below.

### Seminar Video

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/o11VyxgbQII?rel=0" frameborder="0" allowfullscreen></iframe>

Link: <https://youtu.be/o11VyxgbQII>

### Overhead Notes
<object style="height: 640px; width: 100%" data="/assets/seminars/10.13.17_project_overview/phylanx_seminar_overhead_notes_10.13.17.pdf" type="application/pdf"></object>

Link: [(.pdf)](/assets/seminars/10.13.17_project_overview/phylanx_seminar_overhead_notes_10.13.17.pdf)

### Code Snippet 1
```python
import phylanx

# A + B

A = phylanx.ast.identifier('A')
B = phylanx.ast.identifier('B')

expr = phylanx.ast.expression(A)
expr.append(phylanx.ast.operation(phylanx.ast.optoken.op_plus, B))

print(expr)

ast = phylanx.ast.generate_ast('A + B')
print(ast)

def visitor(ast):
    print(ast)
    return True

phylanx.ast.traverse(ast, visitor)
```

Link: [(.py)](/assets/seminars/10.13.17_project_overview/phylanx_seminar_code1_10.13.17.txt)

### Code Snippet 2
```python
import phylanx

# A + B

variables = {
    'A' : phylanx.execution_tree.var(1.0),
    'B' : phylanx.execution_tree.var(41.0)
}

p = phylanx.execution_tree.generate_tree('A + B', variables)
print(p.eval())

variables['B'].assign(66.0)
print(p.eval())
```

Link: [(.py)](/assets/seminars/10.13.17_project_overview/phylanx_seminar_code2_10.13.17.txt)

# Truth Table Builder

This is a simple web application that builds a truth table for a boolean expression. It's intended as an aid 
to learning boolean arithmetic.

Given an expression like

```
~p | q
```

it displays the truth table:

![Truth table for ~p | q](assets/table.png)

The first columns, two in this case, show the value of each variable used in the expression. 

Next comes one colum for each intermediate sub-expression. There's just one in this example, the column for ```~p```.

The last column is the value of the full expression ```(~p | q)```.


## Highlighting

Rows are highlighted when you hover over the table. Furthermore, if you place the mouse over a cell in one of the
expression columns, all the variables used in that expression (or sub-expression) are also highlighted, like this:

![Table highlight on hover](assets/hover.png)


## Expression syntax

Expression may use the following variables and operators:

| Symbol  | Description            | Example   |
| :-----: | :----                  | :----:    |
| a-z A-Z | variables              |  p        |
|    &    | and / conjunction / ∧  |  p & q    |
|   \|    | or / disjunction / ∨   |  a \| b   |
|    ^    | xor / exclusive or / ⊕ |  x ^ y    |
|    ~    | not / negation / ¬     |  ~p       |
|   ( )   | parentheses            |  ~(a & b) |

#### Order of operations

```~``` has highest precedence so ```~p & q``` is evaluated as ```(~p) & q``` rather than ```~(p & q)```.

The binary operators associate left-to-right so ```a | b & c``` is evaluated at ```(a | b) & c``` 
rather than ```a | (b & c)```. 

Use parentheses to control the order of operations. The truth table shows expressions fully parenthesized so you 
can see in what order operators were evaluated.

#### Table size

Note that the table grows exponentially with the number of variables so more than 5 or 6 is unwieldy. Your browser
will probably run out of memory if you really go crazy. Go ahead, try it, you know you want to.


## Installation

Since this is just an HTML page with Javascript there isn't anything to install. Just open *truth.html* in your browser.

This link should also work as a live preview from github: [truth.html](http://htmlpreview.github.io/?https://github.com/dwschultz/truth-table/blob/initial/truth.html)


## Background

I wrote this app to help my daughter with her boolean algebra homework when she was in high school. That was a while
ago and I haven't updated it, except to clean it up a bit and add some comments. Perhaps I'll update it to modern
standards at some point.


## License

See the [LICENSE](LICENSE) file for license rights and limitations (MIT).



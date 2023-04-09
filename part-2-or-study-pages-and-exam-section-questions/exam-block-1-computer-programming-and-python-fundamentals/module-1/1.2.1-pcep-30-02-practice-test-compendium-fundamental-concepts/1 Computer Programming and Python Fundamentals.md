# 1.2.1.1 PCEP-30-02 Practice Test Compendium – Fundamental Concepts

## Understanding fundamental concepts

01\) A **language** is a means (and a tool) for expressing and recording thoughts.

02\) A **natural language** is a language people use to communicate with each other in everyday life. English, Russian, German, Swahili, and Hindi are examples of natural languages.

03\) A **programming language** is a language developed by humans and used to communicate with computers. A programming language has a set of means to instruct a computer what to do and how.

04\) A **high-level programming language** is a programming language which operates on a high level of abstraction thereby allowing the developer to ignore the physical details of the computer's hardware, for example the CPU type, memory size and organization, etc. Python, JavaScript, and C/C++ are all examples of high-level programming languages.

05\) A **machine language** is a language placed at the lowest level of computer programming. It's a sequence of bits (binary digits usually recognized as **0** and **1**) which directly forces the CPU to execute the desired elementary operations.

06\) An **instruction list** (abbreviated to **IL**) is a list of all elementary (atomic) operations which can be executed by a certain CPU. For example, **x86** (used in personal computers) and **arm** (used in mobile devices) processors have different and incompatible instruction lists).

07\) A **source code** is a text encoded in any of the programming languages (regardless of the language's level). Usually, the source code is put inside a text file which resides inside the developer's computer filesystem, while the file name's extension reveals the programming language used to write the code (for example, files with names which ends with `.py` contain Python source code, while the `.cpp` extension marks files which hold C++ (usually pronounced as _see-plus-plus_) source code.

08\) Any language (no matter if it's natural or artificial) is constituted by:

* an **alphabet** understood as a set of symbols used to build words of a certain language (e.g. the Latin alphabet for English, the Cyrillic alphabet for Russian, Kanji for Japanese, and so on).
* a **lexis**, also known as a **dictionary**, is a set of words the language offers its users (for example, the word "chat" is present both in English and French dictionaries, but its meaning is obviously different).
* **syntax** is a set of rules used to determine if a certain sequence of words forms a valid sentence.
* **semantics** is defined as a set of rules which settle whether or not a certain phrase or sentence makes sense in a given language.

09\) A source code **cannot be directly executed by a computer**. To make it possible the source code has to be **translated** into a machine code accepted by a target computer and its CPU. This task can be done using two different techniques:

* **compilation** performed by a one-time translation of the source program; an executable binary file is created in effect – the file can be run at any time without the need to have the source code; the program that performs the above translation is called a **compiler** or **translator**.
* **interpretation** which involves a dedicated program designed to translate the source program on-the-fly each time it has to be run; the program performing this task is called an **interpreter**; this means that the interpreter is needed whenever the source code has to be executed.

10\) A specific programming language is designed to be the object of either compilation or interpretation (this choice imposes certain distinctive features onto the language). For example, **Python** is an **interpreted** programming language, while **C++** is a compiled one.

11\) The interpreter and its environment, created and distributed by the [**Python Software Foundation**](https://www.python.org/psf-landing/) (PSF) is written mostly in the C programming language. It allows Python to be easily ported and migrated to all platforms providing the ability to compile and run C language programs. This is also why the PSF implementation is often referred to as **CPython**. CPython is the most widely used implementation of Python.

# 1.2.1.2 PCEP Practice Test Compendium – Python basic types and literals

## Python basic types and literals

01\) A **literal** is data whose value is **determined by the literal itself**. Different kinds of data are coded in different ways, enabling Python (and the human reader of the source code) to determine each literal's **type**. Knowing each argument's type is crucial to understand what operations are legal, and what results can be returned.

02\) **Integer** (`int` for short) is a type dedicated to storing **integral numbers**, that is, numbers that lack fractional parts. For example, 1 is an integral number and 1.5 is not.

03\) Most used integer literals in Python consist of a sequence of **decimal digits**. Such a sequence cannot include white spaces, but can contain any number of `_` (underscore) characters. Note: there must not be more than one underscore between two digits, and the underscore must be neither the last nor the first character of the literal. Underscores don't change a literal's value, and their only role is to improve literal readability. Integer literals can be preceded by any number of `-` (minus) or `+` (plus) characters, which are applied to set the literal's sign.

04\) Here are some examples of correct integer literals:

* `1_111` and `1111` encode the same integer value (_one thousand one hundred and eleven_)
* `-+-3` and `-3` denote the same integer value (_minus three_)
* `+1` and `1` encode the same integer value (_one_)

05\) Integer literals may be written using radices other than 10:

* if a literal starts with either a `0o` or `0O` digraph, it's an **octal** value (note: it must contain octal digits only!)
* `0o10` encodes an integer value equal to _eight_.
* if a literal starts with either a `0x` or `0X` digraph, it's a hexadecimal value (note: letters from **a** to **f** used as hexadecimal digits may be upper- or lower-case)
* `0X11` encodes an integer value equal to _seventeen_.
* if a literal starts with either a `0b` or `0B` digraph, it's a binary value (note: it must contain **0**s and **1**s only!)
* 0b111 encodes an integer value equal to seven.

06\) **Floating point** (`float` for short) is a type designed to store **real** numbers (in the mathematical sense), that is, numbers whose decimal expansion is or can be non-zero. Such a class of numbers includes fractions (integers don't).

07\) Float literals are distinguished from integers by the fact that they contain a **dot** (`.`) or the letter _e_ (lower- or upper-case) or both. If the only digits which exist before or after the dot are zeros, they can be omitted. Like integers, floats can be preceded by any number of `-` and `+` characters, which determine the number's sign. White spaces are not allowed, while underscores are.

08\) If the float literal contains the letter _e_, it means that its value is **scaled**, that is, it's multiplied by a **power of 10** while the exponent (which must be an integer!) is placed directly after the letter. A record like this:

`mEn`

is treated as a value equal to:

`m × 10n`

This syntax is called _scientific notation_ and is used to denote a number whose absolute value is extremely large (close to infinity) or extremely small (close to zero).

09\) Here are some examples of correct float literals:

* `1.1` – _one and one-tenth_
* `1.0` (`1.` for short) – _one point zero_
* `0.1` (`.1` for short) – _one-tenth_
* `1E1` – _ten point zero_
* `1e-1` – _one-tenth_
* `-1.1E-1` – _minus eleven hundredths_

# 1.2.1.3 PCEP Practice Test Compendium – Python basic types and literals

## **Python basic types and literals: continued**

10\) **String** literals are sequences (including empty ones) of characters (digits, letters, punctuation marks, etc.). There are two kinds of string literal:

* **single-line**, when the string itself begins and ends in the same line of code: these literals are enclosed in a pair of `'` (apostrophe) or `"` (quote) marks.
* **multi-line**, when the string may extend to more than one line of code: these literals are enclosed in a pair of trigraphs either `"""` or `'''`
* strings enclosed inside apostrophes can contain quotes, and vice versa.
* if you need to put an apostrophe inside an apostrophe-limited string, or a quote inside a quote-limited string, you must precede them with the `\` (backslash) sign, which acts as an escape character (a character which changes the meaning of the character that follows it); some of the most used escape sequences are:
  * `\\` – backslash
  * `\'` – apostrophe
  * `\"` – quote
  * &#x20;– newline character
  * &#x20;– carriage return character
  * &#x20;– horizontal tab character

11\) Here are some examples of correct string literals:

* `"Hello world"`
* `'Goodbye!'`
* `''` (an empty string)
* `"Python's den"`
* `'Python\'s den'`
* `"""Two`\
  `lines"""`

12\) **Boolean literals** denote **the only two possible values** used by the _Boolean algebra_ – their only acceptable denotations are `True` and `False`.

13\) The `None` literal denotes an **empty value** and can be used to indicate that a certain item contains no usable value.
# 1.2.1.4 PCEP-30-02 Practice Test Compendium – Operators

## Operators

01\) An operator is a symbol that **determines an operation to perform**. The operator along with its arguments (operands) forms an expression that is subject to evaluation and provides a result.

02\) There are three basic groups of operators in Python:

* arithmetic, whose arguments are numbers;
* string, which operates on strings or strings and numbers;
* Boolean, which expects that their arguments are Boolean values.

03\) A unary operator is an operator with only one operand.

04\) A binary operator is an operator with two operands.

## Unary arithmetic operators

| Operator | Meaning                  | Example                  |
| -------- | ------------------------ | ------------------------ |
| `-`      | Change argument's sign   | `-(-2)` is equal to `2`  |
| `+`      | Preserve argument's sign | `+(-2)` is equal to `-2` |

## Binary arithmetic operators (ordered according to descending priority)

| Priority | Operator | Name               | Example  | Meaning | Result | Result Type                                                                                                                                                           |
| -------- | -------- | ------------------ | -------- | ------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Highest  | `**`     | Exponentiation     | `2 ** 3` | $$2^3$$ | `8`    | <ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li></ul>                                                                    |
|          | `*`      | Multiplication     | `2 * 3`  | 2 × 3   | `6`    | <ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li></ul>                                                                    |
|          | `/`      | Division           | `4 / 2`  | 4 ÷ 2   | `2.0`  | <ul><li>always <code>float</code></li><li>raises <code>ZeroDivisionError</code> when divider is zero</li></ul>                                                        |
|          | `//`     | Integer division   | `5 // 2` |         | `2`    | <ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li><li>raises <code>ZeroDivisionError</code> when divider is zero</li></ul> |
|          | `%`      | Remainder (modulo) | `5 % 2`  | 5 mod 2 | `1`    | <ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li><li>raises <code>ZeroDivisionError</code> when divider is zero</li></ul> |
| Lowest   | `+`      | Addition           | `2 + 1`  | 2 + 1   | `3`    | <ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li></ul>                                                                    |
|          | `-`      | Subtraction        | `2 - 1`  | 2 − 1   | `1`    | <p></p><ul><li><code>int</code> if both arguments are ints</li><li><code>float</code> otherwise</li></ul>                                                             |

pairs of parentheses can be used to change the order of operations, for example:

* `2 + 3 * 4` evaluates to `24`
* `(2 + 3) * 4` evaluates to `20`

when operators of the same priority (other than `**`) are placed side-by-side in the same expression, they are evaluated **from left to right**: therefore, the expression:

```python
1 / 2 * 2
```

evaluates to `1.0`, not to `0.25`.

This convention is called **left-sided binding**.

when more than one `**` operator is placed side-by-side in the same expression, they are evaluated **from right to left**: therefore, the expression:

```python
2 ** 2 ** 3
```

evaluates to `256` ($$2^8$$), not to `64` ($$4^3$$) – this is **right-sided binding**.

# 1.2.1.5 PCEP-30-02 Practice Test Compendium – Operators

## String operators (ordered according to descending priorities)

The rules governing the use of operators and parentheses remain the same, and left-sided binding is in effect.

| Priority | Operator | Name          | Example                                                 | Result                                        | Result type     |
| -------- | -------- | ------------- | ------------------------------------------------------- | --------------------------------------------- | --------------- |
| Highest  | `*`      | Replication   | <p><code>'a' * 3</code><br><code>3 * 'a'</code></p>     | `'aaa'`                                       | Always a string |
| Middle   | `+`      | Concatenation | <p><code>'a' + 'z'</code><br><code>'z' + 'a'</code></p> | <p><code>'az'</code><br><code>'za'</code></p> | Always a string |

## Boolean operators (ordered according to descending priorities)

Boolean operators demand Boolean arguments, and always result in a Boolean result. The rules governing the use of operators and parentheses remain the same, including left-sided binding.

| Priority | Operator | Name        | Example           | Result  |
| -------- | -------- | ----------- | ----------------- | ------- |
| Highest  | `not`    | negation    | `not false`       | `True`  |
|          |          |             | `not True`        | `False` |
| Middle   | `and`    | conjunction | `False and False` | `False` |
|          |          |             | `False and True`  | `False` |
|          |          |             | `True and False`  | `False` |
|          |          |             | `True and True`   | `True`  |
| Lowest   | `or`     | disjunction | `False or False`  | `False` |
|          |          |             | `False or True`   | `True`  |
|          |          |             | `True or False`   | `True`  |
|          |          |             | `True or True`    | `True`  |

## Relational operators

Relational operators compare their arguments to diagnose the relationship between them, and always return a Boolean value indicating the comparison result.

| Operator | Name             | Example                                                     | Result                                         |
| -------- | ---------------- | ----------------------------------------------------------- | ---------------------------------------------- |
| `==`     | equal to         | `2 == 1`                                                    | `False`                                        |
| `!=`     | not equal to     | `2 != 1`                                                    | `True`                                         |
| `>`      | greater than     | `2 > 1`                                                     | `True`                                         |
| `>=`     | greater or equal | <p><code>2 >= 1</code><br><code>1 >= 1</code></p>           | <p><code>True</code><br><code>True</code></p>  |
| `<`      | less than        | `2 < 1`                                                     | `False`                                        |
| `<=`     | less or equal    | <p><code>2 &#x3C;= 1</code><br><code>1 &#x3C;= 1</code></p> | <p><code>False</code><br><code>True</code></p> |

# 1.2.1.6 PCEP-30-02 Practice Test Compendium – Variables, assignments, comments

## Variables

01\) A variable is **a named container able to store data**.

02\) A variable's name can consist of:

* **letters** (including non-Latin ones)
* **digits**
* **underscores** (`_`)

and **must start with a letter** (note: underscores count as letters). Upper- and lower-case letters are treated as different.

03\) Variable names which start with underscores play a specific role in Python – don't use them unless you know what you're doing.

04\) Variable names are not limited in length.

05\) The name of the variable must not be any of Python's **keywords** (also known as **reserved words**). The complete list of Python 3.8 keywords looks as follows:

```python
'False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield'
```

\* Note: Python 3.9 introduced a new keyword, `__peg_parser__`, which is an easter egg related to the rollout of a new PEG parser for CPython. You can read more about this in [PEP 617](https://www.python.org/dev/peps/pep-0617/). The keyword will most probably be removed in Python 3.10.

06\) These are some legal, but not necessarily the best, Python variable names:

* `i`
* `counter_2`
* `_`
* `Tax22`

## The assignment operator

01\) The assignment operator `=` is designed to assign a value to a variable:

```python
variable = expression
```

For example:

```python
counter = 0
pi2 = 3.1415 ** 2
```

or – when more than one variable is assigned with the same value:

```python
variable_1 = variable_2 = ... = expression
```

For example:

```python
counter = stages = 0
```

02\) A variable must be **assigned (defined)** before its first use – using a variable without prior definition (assignment) raises the _NameError_ exception.

03\) Python is a **dynamically typed** language, which means that a variable can freely change its type according to the last assignment it took part in.

04\) There are some **short-cut (compound) operators** which simplify certain kinds of assignments.

# 1.2.1.7 PCEP-30-02 Practice Test Compendium – Variables, assignments, comments

## Compound operators

### **Compound Arithmetic Operators**

| Operator                  | Meaning                               | Example                     |
| ------------------------- | ------------------------------------- | --------------------------- |
| `variable += expression`  | `variable = variable + (expression)`  | `counter += 1`              |
| `variable -= expression`  | `variable = variable - (expression)`  | `due -= ret`                |
| `variable *= expression`  | `variable = variable * (expression)`  | `next_power *= next_power`  |
| `variable /= expression`  | `variable = variable / (expression)`  | `fraction /= fraction`      |
| `variable //= expression` | `variable = variable // (expression)` | `always_one //= always_one` |
| `variable %= expression`  | `variable = variable % (expression)`  | `always_zero %= 1`          |
| `variable **= expression` | `variable = variable ** (expression)` | `square_me **= 2`           |

### **Compound String Operators**

| Operator                 | Meaning                              | Example            |
| ------------------------ | ------------------------------------ | ------------------ |
| `variable += expression` | `variable = variable + (expression)` | `header += '****'` |
| `variable *= expression` | `variable = variable * (expression)` | `doubled *= 2`     |

Note: Boolean operators have no short-cut variants.

## Comments

01\) A part of the code line which starts with hash (`#`), which is not a part of a string literal, is considered a **comment** (a part of the code which is ignored by the interpreter)

For example, these two lines contain comments:

```python
# This is a line which is completely ignored by the Python interpreter.
result = True # only part of this line is a comment
```

# 1.2.1.8 PCEP-30-02 Practice Test Compendium – Basic Input/Output

## Basic Input/Output

1. The `input()` function is used to interact with the user, allowing them to suspend program execution and to enter a sequence (including an empty one) of characters, which is the function's **result**.
2. If the user presses `<Enter>` while providing no other input, the `input()` function returns an empty string as a result.\
   For example, the `name` variable is assigned with a string inputted by the user:\
   `name = input()`
3. The `input()` function accepts an optional argument which is a string; the argument is printed on the screen before the actual input begins.\
   For example, the user is prompted to input the name:\
   `name = input('What is your name?')`
4. To convert the user's input into an integer number, the `int()` function can be used.
5. An operation during which the data changes its type is called **type casting**.\
   For example, the user is asked to input a year of birth. The input is converted into an integer number and assigned to the `b_year` variable:\
   `b_year = int(input('What is your year of birth?'))`
6. To convert the user's input into a float number, the `float()` function can be used.\
   For example, the user is asked to input a height measured in meters. The input is converted into a float number and assigned to the `m_stature` variable:\
   `m_stature = float(input('What is your height in meters?'))`
7. If the `int()` or `float()` is not able to perform the conversion due to the incorrect contents of the user's input, the `ValueError` exception is raised.
8. Unless otherwise specified, the printed values are separated by single spaces.\
   For example, the following snippet sends `1 2 3` to the screen:\
   `print(1, 2, 3)`
9. If the invocation makes use of the `sep` keyword parameter, the parameter's value (even when it's empty) is used to separate outputted values instead of spaces.\
   For example, the following snippet sends `1*2*3` to the screen:\
   `print(1, 2, 3, sep='*')`
10. Unless otherwise specified, each `print()` function invocation sends the newline character to the screen before its completion, therefore each `print()` function's output starts on a new line.\
    For example, the following snippet produces two lines of output on the screen:\
    `print('Alpha')`\
    `print('Bravo')`
11. If the invocation makes use of the `end` keyword parameter, the parameter's value is (even when it's empty) used to complete the output instead of the newline.\
    For example, the following snippet produces one line of output on the screen:\
    `print('Alpha', end='')`\
    `print('Bravo')`
12. The `end` and `sep` parameters can be used together.\
    For example, the following snippet produces one line of asterisk-separated letters:\
    `print('A', 'B', sep='*', end='*')`\
    `print('C')`

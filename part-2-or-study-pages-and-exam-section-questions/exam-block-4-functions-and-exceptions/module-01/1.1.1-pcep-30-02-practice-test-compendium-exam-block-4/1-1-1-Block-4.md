# 1.1.1.0 PCEP-30-02 Practice Test Compendium – Exam Block #4

## Exam block #4: Functions and Exceptions

### **Study Pages**

Objectives covered by the block:

### **PCEP 4.1 Decompose the code using functions**

* defining and invoking user-defined functions and generators; the _return_ keyword, returning results, the _None_ keyword, recursion.

### **PCEP 4.2 Organize interaction between the function and its environment**

* parameters vs. arguments; positional, keyword and mixed argument passing; default parameter values, name scopes, name hiding (shadowing), the _global_ keyword.

### **PCEP 4.3 Python Built-In Exceptions Hierarchy**

* _BaseException_, _Exception_, _SystemExit_, _KeyboardInterrupt_, abstract exceptions, _ArithmeticError_, _LookupError_ along with _IndexError_ and _KeyError_; _TypeError_ and _ValueError_ exceptions, the _AssertError_ exception along with the _assert keyword_.

### **PCEP 4.4 Basics of Python Exception Handling**

* _try-except_, _try-except_ Exception, ordering the _except_ branches, propagating exceptions through function boundaries; delegating responsibility for handling exceptions.

![](<../../../../.gitbook/assets/Exam block #4 Functions and Exceptions.png>)
# 1.1.1.1 PCEP-30-02 Practice Test Compendium – Exam Block #4

## Functions and Exceptions

This exam block is the fourth and last section that appears in the exam. It constitutes a maximum of **28%** of the overall exam score. It contains **eight (8)** exam items, each graded to a maximum of 20, 30, or 40 points.

### **Specifications**

* Section weight: 28%
* Max raw score: 280
* Questions drawn: 8
* Question types: single- and multiple-choice, drag & drop, sorting, code ordering
* Points per question: 4+4+4+4+4, 6+6+6+6+6, 7+6+7 (drag & drop, sorting, code ordering), 20, 30 (single-choice), 10+10, 20+20, 10+20, (multiple-choice)

![](<../../../../.gitbook/assets/Functions and Exceptions.png>)
# 1.2.1.1 PCEP-30-02 Practice Test Compendium – Functions

## Functions

01\) A **function** is a named, separate part of the code that can be **activated on demand**. A function can **perform an action**, or **return a result**, or **both**.

02\) The simplest function, which does nothing and returns no result, can be defined in the following way:

```python
def lazy():
    pass
```

03\) Activating a function is done by the **function invocation** (function call). The `lazy()` function defined above can be invoked by the following clause:

```python
lazy()
```

04\) Function definition must **precede its invocation**. Breaking this rule raises the `NameError` exception.

05\) A function can be equipped with an arbitrary number of **parameters**. The parameters behave like variables known inside the function only, and their values are set during the invocation. The invocation must provide **as many arguments as needed to initialize all parameters**. Breaking this rule results in raising the `TypeError` exception.

06\) If a function is supposed to evaluate a result, it must perform the `return` _expression_ instruction, which immediately terminates function execution and causes the function to return the _expression_ value to the invoker. If the function does not execute the instruction, or utilizes return without an expression, the None value is returned implicitly. For example, the following snippet prints `True None` to the screen:

```python
def function(parameter):
    if parameter == False:
        return True


print(function(False), function(True))
```

07\) A function definition can declare **default values** for some or all of its parameters. When the invocation does not provide arguments for these parameters, the default values are taken into consideration. Note: parameters with default values must not precede the ones without them. For example, the following snippet prints `True False` to the screen:

```python
def function(parameter = False):
    return parameter


print(function(True), function())
```

08\) The **positional** parameter passing technique is a technique based on the assumption that the arguments are associated with the parameters **based upon their position** (i.e. the first argument value goes to the first parameter, and so on) For example, the following snippet outputs `1 2 3` to the screen:

```python
def function(a, b, c):
    print(a, b, c)


function(1, 2, 3)
```

09\) The **keyword** parameter passing technique is a technique based on the assumption that the arguments are associated with the parameters based upon the parameter's **names**, which must be explicitly specified during the invocation. For example, the following snippet outputs `1 2 3` to the screen:

```python
def function(a, b, c):
    print(a, b, c)


function(c=3, a=1, b=2)
```

# 1.2.1.2 PCEP-30-02 Practice Test Compendium – Functions

## Functions – continued

10\) A function definition can declare **default values** for some or all of its parameters. When the invocation does not provide arguments for these parameters, the default values are taken into consideration. Note: parameters with default values must not precede the ones without them. For example, the following snippet prints `1 2 3` to the screen:

```python
def function(a, b, c):
    print(a, b, c)


function(1, c=3, b=2)
```

11\) Note that the following invocation is incorrect and will raise the `TypeError` exception, because the a parameter is set twice (once with the positional passing and once with the keyword passing) while the `c` parameter is not set at all.

```python
function(1, a=1, b=2)
```

12\) A **scope** is the part of the code where a certain name is properly recognizable.

13\) A variable existing outside a function has a scope which includes the function's bodies.

14\) A variable defined inside the function has a scope inside the function's body only.

15\) If a certain variable is used inside a function and the variable’s name is listed as an argument of the `global` keyword, it has **global scope**, and it is also recognizable outside the function. For example, the following snippet outputs `2` to the screen:

```python
def function():
    global variable
    variable += 1


variable = 1
function()
print(variable)
```

Note: removing the line containing the `global` keyword will spoil the code and the `UnboundLocalError` exception will be raised.

16\) Changing the parameter's value **doesn't propagate it** outside the function. For example, the following snippet outputs `[1]` to the screen:

```python
def function(parameter):
    parameter = [2]


the_list = [1]
function(the_list)
print(the_list)
```

17\) If the parameter is a **list** or a **dictionary**, changing its contents **propagates them** outside the function. For example, the following snippet outputs `[2]` to the screen:

```python
def function(parameter):
    parameter[0] = 2


the_list = [1]
function(the_list)
print(the_list)
```

18\) **Recursion** is a programming technique in which the function **invokes itself** to perform a complex task. For example, the following snippet contains a function that evaluates the factorial of its argument and prints `120` to the screen:

```python
def factorial(n):
    if n < 2:
        return n
    else:
        return n * factorial(n - 1)


print(factorial(5))
```
# 1.2.1.3 PCEP-30-02 Practice Test Compendium – Exceptions and debugging

## Exceptions and debugging

01\) An **exception** is an event caused by an execution error which can induce program termination if not properly handled by the programmer. The situation in which the exception is created and propagated is called **raising** the exception.

02\) Python professes its philosophy expressed with the sentence: _It's better to beg for forgiveness than ask for permission._ The recommendation hidden behind these words says that the programmer should **allow the exceptions to occur and handle them properly** instead of persistently avoiding problems and protecting the code from all possible errors with all their might.

03\) To **control** exceptions and to handle them, Python provides a dedicated construction consisting of the `try` and `except` branches.

04\) The `try` block encloses a part of the code that may cause an exception and when it happens, the execution of the block is terminated and the control jumps into the `except` block, which is dedicated to recognizing the problem and handling it. For example, the following snippet prints `PROCEEDING` even though the code provokes division by zero:

```python
try:
    x = 1 / 0
except:
    x = None
print('PROCEEDING')
```

05\) Here is a list of the most common Python exceptions:

* `ZeroDivisionError`: raised by a division in which the divider is **zero** or is indistinguishable from zero (/, //, and %)
* `ValueError`: raised by the use of values that are **inappropriate** in the current context, for example, when a function receives an argument of a proper type, but its value is **unacceptable**, for example, int('')
* `TypeError`: raised by attempts to apply data of a **type** which cannot be accepted in the current context, for example, `int(None)`
* `AttributeError`: raised – among other occasions – when the code tries to activate a **method** that doesn't exist in a certain item, for example, `the_list.apend()` (note the typo!)
* `SyntaxError`: raised when the control reaches a line of code that **violates** Python's grammar, and which has remained undetected until now;
* `NameError`: raised when the code attempts to make use of a **non-existent** (not previously defined) **item**, for example, a variable or a function.

06\) When more than one exception is expected inside the `try` block and these different exceptions require different handling, another syntax is used where there is more than one named `except` branch. The unnamed (anonymous) `except` branch is the **default** one, and is responsible for servicing these exceptions which still need to be handled.

07\) Not more than one `except` branch can be executed.

08\) The default `except` branch – if it exists – must be the last branch.

09\) For example, the following snippet outputs `NAN` when the user enters a string that is not an integer number, `ZERO` when the user enters `0`, and `ERR` in the case of another error:

```python
try:
    print(1 / int(input("Enter a number: ")))
except ValueError:
    print('NAN')
except ZeroDivisionError:
    print('ZERO')
except:
    print('ERR')
```

10\) An error existing in the code is commonly called a **bug**.

11\) The process by which bugs are detected and removed from the code is called **debugging**.

12\) The tool which allows the programmer to run the code in a fully controllable environment is called a **debugger**.

13\) The '**print debugging**' technique is a trivial debugging technique in which the programmer adds some `print()` function invocations which help to trace execution paths and output the values of selected critical variables.

14\) The process in which the code is probed to ensure that it will behave correctly in a production environment is called **testing**. The testing should prove that all execution paths have been executed and caused no errors.

15\) The programming technique in which the tests and test data are created before the code is written or created in parallel with the code is called **unit testing**. It is assumed that every code amendment (even the most trivial) is followed by the execution of all previously defined tests.

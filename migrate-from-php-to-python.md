# Migrate from PHP to Python

Hi all, recently I've decided to move on and learn Python programming. At first, I though that it would be very difficult but in fact... Not that much. So I've decided to write this little gist and show the main differences between both languages.

I will use try to follow the same order used on this website: https://pythonprogramming.net/introduction-to-python-programming/. It was really usefull to improve my understanding of Python programming.

To finish, I'm assuming that you already got basic knowledge in **Object Oriented Programming** and already got skills and understanding of PHP programming. This is not intended to explain you how to code in PHP but if you're coming from Python programming, then this gist might help you to migrate from Python to PHP.

## Official documentations

You should always refer to the documentation while programming to make sure you're doing things properly.

  * Documentation for PHP: https://secure.php.net/docs.php
  * Documentation for Python: [Version 2](https://docs.python.org/2.7/) / [Version 3](https://docs.python.org/3/)
  
> Concerning PHP, the examples given are based on version **7.x**. So if you're coming from version **5.x**, you might have to look at the differences between version **5.x** and **7.x**.
>
> Even latest PHP versions **7.0, 7.1, 7.2** have few differences between them.

## Most visible differences

In Python, you can forget to use characters like **{** and **}** to write your `functions`, `methods` or `classes`. To write them or loops, you will have to use **:** instead.

For those familiar to the alternative syntax of PHP, you will find some similarities.

Another big difference is regarding the line ending characters, no need to use **;** anymore to end your lines.

I know you can also use `print()` in PHP but I've prefered to stay with `echo` statement for this gist as it's also the common way to output content in PHP. For more complex `string` handling, we all knows we can use `print()` or `printf()` and similar methods to do that.

> Be very carefull with the indentation, most of your code issues will comes from bad indentation. This is very crucial in Python, much more than it can be in PHP.

## Strings and how to use them

Take a look at this page for the complete guide: https://pythonprogramming.net/python-tutorial-print-function-strings/

### Strings

To write `strings`, both **'** and **"** can be used.

### Escaping

Escaping is done the same way in Python and PHP.

### No more `echo`

To print your string content, you can't use `echo` anymore but instead, you will have to use `print` to do the same thing.

Example:

```php
echo 'your nice string!';
```

Will be written in Python:

```python
print('your nice string')
```

### Comments

In PHP there are few ways to write inline comments but less in Python. For block comments, there is a minor difference.

#### Inline comments

In PHP:

```php
// Inline comment type 1
# Inline comment type 2
/* Inline comment type 3 */
```

In Python:

```python
# Inline comment type
```

#### Block comments

In PHP:

```php
/*
Block comment.
Anything you want to describe
on several lines.
*/
```

In Python:

```python
'''
Block comment.
Anything you want to describe
on several lines.
'''
```

### Concatenation

You can not use **.** anymore to concatenate your `strings`, you will have to use **+** or **,**.

> When using **,** to concatenate `strings` python will add a space between joined `strings`. This is not the case when using **+**.

Example:

```php
$add_to_string = 'will be echoed';

// with space included
echo 'your nice string!' . ' ' . $add_to_string;

// without space included
echo 'your nice string!' . $add_to_string;
```

Will be written in Python:

```python
add_to_string = 'will be printed'

# with space included
print('your nice string', add_to_string)

# without space included
print('your nice string' + add_to_string)
```

## Math basics

I haven't noticed any real differences between PHP and Python to do and write maths. If you want more details, take a look at this page: https://pythonprogramming.net/math-basics-python-3-beginner-tutorial/

## Variables

I've only seen few differences concerning the `variables`. The first one is that you don't need anymore to preceed them by **$**. You may have noticed it on previous examples.

Example:

```php
$my_php_variable = "yo, what's up?";
```

Will be written in Python:

```python
myPythonVariable = "yo, what's up?"
```

Same rules are applied regarding the `variables` contents but the namming scheme looks different. It seems to adviced to use `camelCase` to name your `variables` but it is not mandatory.

For more details, take a look at this page: https://pythonprogramming.net/python-3-variables-tutorial/

## Loops

There are few differences concerning the `loops` in Python, I will you them.

### Using `while`

In PHP:

```php
// Classic syntax:
$i = 1;
while ($i <= 10) {
    echo $i++;
}

// Alternative syntax:
$i = 1;
while ($i <= 10):
    echo $i++;
endwhile;
```

In Python gives:

```python
i = 1
while i < 10:
    print(i)
    i += 1
```

Take a look at this page for all explanations: https://pythonprogramming.net/python-3-loop-tutorial/

### Using `for`

In PHP:

```php
// Classic syntax:
for ($i = 1; $i <= 10; $i++) {
    echo $i;
}

// Alternative syntax:
for ($i = 1; $i <= 10; $i++):
    echo $i;
endfor;
```

In Python gives:

```python
for i in range(1,11):
    print(i)
```

Take a look at this page for all explanations: https://pythonprogramming.net/loop-python-3-basics-tutorial/

### Using `foreach`

Guess what? No more `foreach` in Python! :grin: You'll have to use `for` loops instead.

In PHP:

```php
// Classic syntax:
$arr = array(1, 2, 3, 4);
foreach ($arr as $a) {
    echo $a;
}

// Alternative syntax:
$arr = [1, 2, 3, 4];
foreach ($arr as $a):
    echo $a;
endforeach;
```

In Python gives:

```python
arr = [1, 2, 3, 4]
for a in arr:
    print(a)
```

Take a look at this page for all explanations: https://pythonprogramming.net/loop-python-3-basics-tutorial/

## Control Structures

There is only few differences between both languages, only the way to write them is different.

### (a). `if` statement

In PHP:

```php
// Variables
$x = 5;
$y = 10;

// Classic syntax:
if ($x > $y) {
    echo 'x is greater than y';
}

// Alternative syntax:
if ($x > $y):
    echo 'x is greater than y';
endif;
```

In Python gives:

```python
# Variables
x = 5
y = 10

# Syntax
if x > y:
    print('x is greater than y')
```

Take a look at this page for all explanations: https://pythonprogramming.net/if-statement-python-3-basics-tutorial/

### (b). `elseif` statement

In PHP:

```php
// Variables
$x = 5;
$y = 10;

// Classic syntax:
if ($x > $y) {
    echo 'x is greater than y';
} elseif ($x === $y) {
    echo 'x is equal to y';
} else {
    echo 'x is smaller than y';
}

// Alternative syntax:
if ($x > $y):
    echo 'x is greater than y';
elseif ($x === $y):
    echo 'x is equal to y';
else:
    echo 'x is smaller than y';
endif;
```

> Notice that I'm also verifying the value type by using `===` instead of `==`.

In Python gives:

```python
# Variables
x = 5
y = 10

# Syntax
if x > y:
    print('x is greater than y')
elif x == y:
    print('x is equal to x')
else:
    print('x is smaller than y')
```

> From my actual understanding of Python, there is no `strict` type checking. I might change this comment later.

Take a look at this page for all explanations: https://pythonprogramming.net/elif-else-python-3-tutorial/

### (c). `else` statement

In PHP:

```php
// Variables
$x = 5;
$y = 10;

// Classic syntax:
if ($x > $y) {
    echo 'x is greater than y';
} else {
    echo 'x is smaller than y';
}

// Alternative syntax:
if ($x > $y):
    echo 'x is greater than y';
else:
    echo 'x is smaller than y';
endif;
```

In Python gives:

```python
# Variables
x = 5
y = 10

# Syntax
if x > y:
    print('x is greater than y')
else:
    print('x is smaller than y')
```

Take a look at this page for all explanations: https://pythonprogramming.net/else-python-3-tutorial/

### (d). Ternary conditions

In PHP, there is another way to write your conditions. It is named `Ternary` conditions.

```php
// Variables
$x = 5;
$y = 10;

// Syntax using ternary condition
echo ($x > $y ? 'x is greater than y' : 'x is smaller than y');
```

You can use this alternative syntax to replace `if`/`elseif`/`else` but it can be less readable:

```php
// Variables
$x = 5;
$y = 10;

// Syntax using ternary condition
echo ($x > $y ? 'x is greater than y' : ($x === $y ? 'x is equal to y' : 'x is smaller than y'));
```

> Again, from my actual understanding of Python, I haven't noticed this possibility.

## Functions

The way you will write your `functions` in Python is radically different than you would do it in PHP. I will show you there the main differences.

In PHP you would do:

```php
function my_func() {
    # function code
}
```

In Python you will do:

```python
def myFunc():
    # function code
```

Take a look at this page for all explanations: https://pythonprogramming.net/functions-python-3-basics-tutorial/

### (a). Parameters

In PHP you would do:

```php
function simple_addition(num1, num2) {
    $answer = $num1 + $num2;
    echo 'Using numbers: ' . $num1 . ' + ' . $num2;
    echo 'Result: ' . $answer;
}

simple_addition(5,3);
```

In Python you will do:

```python
def simple_addition(num1, num2):
    answer = num1 + num2
    print('Using numbers:', num1, '+', num2)
    print('Result:', answer)

simple_addition(5,3)
```

Refer to this page for a detailled explanation: https://pythonprogramming.net/function-parameters-python-3-basics

### (b). Default Parameters

In PHP you would do:

```php
function basic_window($width, $height, $font = 'TNR') {
    # let us just print out everything
    echo $width . ' ' . $height . ' ' . $font;
}

basic_window(350,500);
```

And to re-assign the default value to a new one:

```php
basic_window(350,350,'Courrier');
```

In Python you will do:

```python
def basic_window(width, height, font='TNR'):
    # let us just print out everything
    print(width, height, font)

basic_window(350,500)
```

And to re-assign the default value to a new one:

```php
basic_window(350,350,'Courrier')
```

Refer to this page for a detailled explanation: https://pythonprogramming.net/function-parameter-defaults-python-3-basics/

## Anonymous Functions

From my actual understanding of Python language, there is no `anonymous` functions supported.

If you want to get more details about them, take a look at this page: https://secure.php.net/manual/en/functions.anonymous.php

## Accessing the variables

The rules to access and use the variables are differents between both languages. I will try to show you few examples.

In PHP, the rules are:

```php
// scope = file
$x = 6;

function example() {
    # scope = function

    # won't works
    echo $x;
    echo ($x+5);

    # same here:
    $x += 6;

    # The above will fail because $x does not exist in the function scope
    # nor defined as function parameter.

    $y = 10;
    echo $y;

    # The above will work because $y is defined inside the function block.
}

// scope = file
echo $x;
```

By default in PHP, `functions` can't access to variables outside their definition. You have to define your variable inside the function block or make it global.

```php
// scope = file
$x = 6;

function example() {
    # scope = function

    # what we do here is defined x as a global variable. 
    global $x;

    # now we can:
    echo $x;

    $x += 5; // new variable scope = global
    echo $x;
}

// scope = file
echo $x;
```

And in Python:

```python
# scope = file
x = 6

def example():
    # scope = function

    # but this works in python
    print(x)
    print(x+5)

    # then what happens when we go to modify:
    x+=6

    # so there we attempted to take the x var and add 6 to it... but now
    # we are told that we cannot, as we're referencing the variable before
    # its assignment.

# scope = file
print(x)
```

So as you can see, Python can read content from file scopped variable without having to put it in global but it can't modify it.

To modify the variable `x` within the `function` you will have to define `x` as a global variable. At this moment, both languages work the same.

```python
# scope = file
x = 6

def example():
    # scope = function

    # what we do here is defined x as a global variable. 
    global x

    # now we can:
    print(x)

    # new variable scope = global
    x+=5
    print(x)

# scope = file
print(x)
```

> By default, you should avoid the use of the `global` keyword and keep your variable scope inside the `function` block.

### To avoid the use of `global` keyword

There are some situations where you can't avoid the use of `global` keyword but otherwise you can do it most of the time. I will show you how in both languages.

For PHP:

```php
$x = 5;

function example($x) {
    # $x can be used because passed as argument
    echo $x;
}

function example2($x) {
    # $x can be used because passed as argument
    return $x;
}

function example3(&$x) {
    # $x can be modified because passed as argument and by reference using '&'
    $x += 5;
    echo $x;
}

function example4(&$x) {
    # $x can be modified because passed as argument and by reference using '&'
    $x += 5;
    return $x;
}

example($x);

$x = example2($x);
echo $x;

example3($x);

$x = example4($x);
echo $x;
```

> Using `references` in PHP can be really messy and make the debugging much more complex. you should avoid to use them. You should better strictly define the use context/scope of your `variables`.

For Python:

```python
x = 5

def example(x):
    # x can be used because passed as argument
    print(x)

    # to modify x
    x += 5
    print x

    # works but can be confusing
    return x

def example2(arg):
    print(arg)
    arg += 5
    print(arg)
    return arg

def example3():
    # we are using glob_x to store the x value
    glob_x = x
    print(glob_x)

    # and modify it later
    glob_x += 5
    print(glob_x)


x = example(x)
print(x)

x = example2(x)
print(x)

example3()
```

For complete explanation, take a look at this page: https://pythonprogramming.net/global-local-variables/

# Let's get a little more concrete

Ok now I've convered the real basics, the next will be a little more complex but funny! :smile:

## Modules

Even if both languages got the same concept somehow and so giving you the possiblity to include external code to your projects, the usage will differ.

### Using PHP

As you may already know, you can use [Composer](https://getcomposer.org/) or [Packagist](https://packagist.org/) to do it.

> There might be others existing but I don't know them.

### Using Python

No more those you would know, say 'hello!' to [Pip](https://en.wikipedia.org/wiki/Pip_(package_manager)). :smile:

See there for more details: https://pythonprogramming.net/installing-modules-python-3/

## Your new friend `Pip`

If you're wondering why `Pip`, I would recommend this reading: https://packaging.python.org/guides/tool-recommendations/

If you're more interested into it's code, look at here: https://github.com/pypa/pip

> You should have nothing to do regarding `Pip` to install it as it should be already included into your Linux distribution or installed by default with Python.

### Installation

In case you don't have it already, take a look at this page: https://pip.pypa.io/en/latest/installing/

## Common errors in Python

Well, I can't do better than what the owner of [pythonprogramming.net](https://pythonprogramming.net/) did so... You should refer to his work for this section: https://pythonprogramming.net/common-errors-python-3-basics/

> Both languages are radically differents on their syntax and so errors are differents too. I'm also not experienced enough in Python to do a concrete comparison between both languages as done in the other sections.

## File handling

The order I'll use will be different than the one provided on [pythonprogramming.net](https://pythonprogramming.net/) but I feel it more logical in my opinion.

You might also notice that both language are using the same permission bits.

  * **`r`**, for read
  * **`w`**, for write
  * **`wb`**, for write in binary mode
  * **`a`**, for append

I felt that funny. :grin:

### (a). Read a file

In PHP:

```php
```

In Python:

```python
# similar syntax as you've seen, 'r' for read. You can just throw a .read() at
# the end, and you get:
readMe = open('exampleFile.txt','r').read()
print(readMe)

# this will instead read the file into a python list. 
readMe = open('exampleFile.txt','r').readlines()
print(readMe)
```

Full explanation here: https://pythonprogramming.net/reading-file-python-3-tutorial/

### (b). Write a file

In PHP:

```php
$text = "Sample Text to Save\nNew line!";

$fp = fopen('exampleFile.txt', 'w');
fwrite($fp, $text);
fclose($fp);
```

> Note the difference between used quotes.
>
> The given `PHP` sample is very simple but that's wanted. It's to give a closer idea on how you would do it and not the way you should do it in `PHP`. Same goes to the given `Python` sample.

In Python:

```python
text = 'Sample Text to Save\nNew line!'

# notifies Python that you are opening this file, with the intention to write
saveFile = open('exampleFile.txt','w')

# actually writes the information
saveFile.write(text)

# It is important to remember to actually close the file, otherwise it will
# hang for a while and could cause problems in your script
saveFile.close()
```

Full explanation here: https://pythonprogramming.net/writing-file-python-3-basics/

### (c). Append in a file

In PHP:

```php
```

In Python:

```python
# so here, generally it can be a good idea to start with a newline, since
# otherwise it will append data on the same line as the file left off.
# you might want that, but I'll use a new line.
# another option used is to first append just a simple newline
# then append what you want. 
appendMe = '\nNew bit of information'

appendFile = open('exampleFile.txt','a')
appendFile.write(appendMe)
appendFile.close()
```

Full explanation here: https://pythonprogramming.net/appending-file-python-3-tutorial/

# Conclusions

To be honest, I don't really understand why people says that `Python` is better than `PHP`. From my actual understanding of `Python` language, `PHP` looks much more complex and wider than `Python`. Peharps it's due to it's lack of popularity in favour of `Python` in the Scientific community or the fact that most people thinks that `PHP` can be used only in Web context, which is wrong.

I'm actually using `PHP` on an encoding project for it's large feature panel, lightweight and portability compared to other languages. And the best with the choice of `PHP` as main language is that I can provide easily two user interfaces with the same language without having to write a lot of code.

That way, I can provide to the future users of this project, a `CLI` interface and a `Web` interface. Just awesome! :metal:

But I must admit that I can't communicate directly with the hardware as I would and I'm using `PHP` just to control the way `ffmpeg` has to be used.

I must also admit that I'm tempted to rewrite my actual `PHP` code in `Python` just for the fun and also probably to compare the running time and performances by curiosity. :wink:

> This gist is not finished yet... I have to sleep a little. :grin:
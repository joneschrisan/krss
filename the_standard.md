# Coding Standards

## Contents
* 1: [PHP](#1-php)
  * 1.1: [Indent Style](#11-indent-style)
  * 1.2: [Tabs and Spaces](#12-tabs-and-spaces)
  * 1.3: [Naming](#13-naming)
  * 1.4: [Variables](#14-variables)
    * 1.4.1: [Strings](#141-strings)
    * 1.4.2: [Integers](#142-integers)
    * 1.4.3: [Floats](#143-floats)
    * 1.4.4: [Booleans](#144-booleans)
    * 1.4.5: [Arrays](#145-arrays)
    * 1.4.6: [Other Variables](#146-other-variables)
  * 1.5: [IF and Switch Statements](#15-if-and-switch-statements)
    * 1.5.1: [IF Statements](#151-if-statements)
    * 1.5.2: [Switch Statements](#152-switch-statements)
  * 1.6: [Loops](#16-loops)
    * 1.6.1: [Formats](#161-formats)
    * 1.6.2: [Exiting and continuing a loop](#162-exiting-and-continuing-a-loop)
  * 1.7: [Doc Blocks and comments](#17-doc-blocks-and-comments)
    * 1.7.1: [Classes](#171-classes)
    * 1.7.2: [Functions and Methods](#172-functions-and-methods)
    * 1.7.3: [Properties](#173-properties)
    * 1.7.4: [Comments](#174-comments)
  * 1.8: [Functions and Methods](#18-functions-and-methods)
    * 1.8.1: [Format](#181-format)
    * 1.8.2: [Rewriting](#182-rewriting)
  * 1.9: [Classes](#19-classes)
  * 1.10: [Namespaces](#110-namespaces)
  * 1.11: [License Blocks](#111-license-blocks)
* 2: [Javascript](#2-javascript)
  * 2.1: [Variables](#21-variables)
  * 2.2: [Functions and Methods](#22-functions-and-methods)
  * 2.3: [Classes](#23-classes)
* 3: [HTML](#3-html)
* 4: [CSS](#4-css)
* 5: [SQL](#5-sql)
  * 5.1: [Naming](#51-naming)
  * 5.2: [Queries](#52-queries)
  * 5.3: [Tables](#53-tables)
  * 5.4: [Deleting](#54-deleting)
* 6: [TWIG](#6-twig)

&nbsp;  
&nbsp;  

## 1: PHP

*Todo*
* 1.9: Classes
* 1.4.x: All

### 1.1: Indent Style
All code should be written to the K&R indent style variant K&R Steam Style (KRSS) which is bases on the [1TBS or OTBS (One True Brace Style)](https://en.wikipedia.org/wiki/Indent_style#Variant:_1TBS) for code consistency and readability. The most notable difference between K&R and 1TBS is the location of curly braces.

1TBS:  
```php
if ($foo == $bar) {
	// Do something here
} else {
	// Do something else here
}

while ($i > 100) {
	// Do something
}

for ($i = 0; $i < 100; $++) {
	// Do something
}

function foo() {
	// Do something
}

class foo {
	
	method bar() {
		// Do something
	}
	
}
```

The most notable difference between 1TBS and KRSS is that only IF statements have a space preceding the opening bracket.

KRSS:
```php
if ($foo == $bar) {
	// Do something
}

for($i = 0; $ < $foo; $++) {
	// Do something
}

switch($foo) {
	case "bar":
		// Do something
		break;
}
```

Code should start on the same indent as the `PHP` tags and not be indented. All other sub sets should be indented.

```php
<?php

// Code here

// More code here

if ($foo == $bar) {
	// Indented code here
}

// And some more code here
```

Code should never be indented more than three times. If there is a need for more than three indented blocks of code then the code should be put into a [function](#18-functions-and-methods) or [class](#19-classes) / [method](#18-functions-and-methods).

As a general rule, if you can do so the code should be placed within a [class](#19-classes) and not ran linear. Code in non class files should only be used to build objects and run [methods](#18-functions-and-methods) or use properties from within the objects created. This creates reusable code.

### 1.2: Tabs and Spaces

Tabs should be used to indent code and the tab character should be set to the equivalent of four space characters (Note: that does not mean use four spaces to indent code)

### 1.3: Naming

Variable, function, class, and method names should have readable real world names, words be separated by an underscore and all lower case.  
```php
$my_object = new my_custom_object();
```

Private variables and methods within a class should start with an underscore.  
```php
private function _foo() {}
```

Class constants should be readable words separated by underscores and be all capitalized.  
```php
const MY_CONSTANT_VAR = 1;
```

General constants should start with a double underscore, be readable words separated by underscores all capitalized, and end with a double underscore.  
```php
__SYSTEMDIR___
```

### 1.4: Variables

For counting the variables $i, $j, $k, $l, etc should be used and in that order. if a loop has ended and another started the start back through the list again. (More on loops [here](#16-Loops))

#### 1.4.1: Strings
*Todo*

#### 1.4.2: Integers
*Todo*

#### 1.4.3: Floats
*Todo*

#### 1.4.4: Booleans
*Todo*

#### 1.4.5: Arrays
*Todo*

#### 1.4.6: Other Variables
*Todo*

### 1.5: IF and Switch Statements

#### 1.5.1: IF Statements

If statements should be formatted with a space before the opening bracket, a space after the closing bracket, and the opening curly brace on the same line as the closing bracket. If the statement contains any operators the each statement should be surrounded with it's own brackets and each one on a new line tab indented. String values should be surrounded with double quotes and not single quotes. Operators should be separated from the variables and values by a space either side. The closing curly brace shoul be on a line by itself with the same indent as the if statement.

```php
if ($foo == $bar) {
	// Do something
}

if (
	(
		($foo) ||
		($bar) 
	) &&
	($foo == $bar)
) {
	// Do something
}
```

#### 1.5.2: Switch Statements

Switch statements follow the same rules as if statements with the exception that there should not have a space before the opening bracket. Case statements to be on their own line and tab indented from the switch statement, and the line should end with a colon. There should be no space before the colon. Code should then be placed on the next line and tab indented, with a final line containing the `break` and semicolon. The break line should have the same indent as the code. The last clause in the switch statement should also be marked as the default clause unless the default is to do something with a different value from the clause then it should be used with the clause value.

```php
switch($foo) {
	case "bar":
	// Do something
		break;
	case "foo":
	default:
	// Do something
		break;
}

switch($foo) {
	case "bar":
	// Do something
		break;
	case "foo":
	// Do something
		break;
	default:
	// Do something
		break;
}
```



### 1.6: Loops

#### 1.6.1: Formats

Loops should be formatted like [switch statements](#152-switch-statements) with no space before the opening bracket and a space after the closing bracket, the opening curly brace on the same line as the closing bracket, All code indentet from the statement, and the closing curly brace on it's own line with the same indent as the statement.

With multiple values in the statement everything should be space separated as normal.

With nested loops the a the iterator variable should be the next letter in the alphabet starting from `i`

```php
for($i = 0; $i < $foo; $i++) {
	// Do something
}

for($i = 0, $J = 0; $i < $foo; $i++) {
	// Do something
}

for($i = 0; $i < $foo; $i++) {
	for($j = 0; $j < $bar; $j++) {
		// Do something
	}
}

foreach($foo as $value) {
	// Do something
}

foreach($foo as $key => $value) {
	// Do something
}

while($i < 100) {
	// Do something
}
```

#### 1.6.2: Exiting and continuing a loop

You should never return from within a loop, instead, if a value is required, always set a variable and "break" out of a loop then return the variable. If you need to skip the remainder of the logic within a loop after a conditional check then a "continue" should be used.

```php
$reached_5 = false;
for($i = 0; $i < 10; $i++) {
	if ($i == 5) {
		$reached_5 = true;
		break;
	}
}

$count;
for($i = 0; $i < 10; $i++) {
	if ($i % 2 == 0) {
		continue;
	}
	$count++;
}
```

### 1.7: Doc Blocks and Comments

Doc blocks should follow the following format and in the order shown.  
*Note: lines within square brackets are optional lines, those not are mandatory*

#### 1.7.1: Classes

```php
/**
[* @todo]
*
* Description
*
* @package		[Value]
* @category		[Value]
*
* @name			[Value]
* @version		[Value]
* 
* @author		[Value]
* 
* @copyright	[Value]
* @license		[Value]
* 
[* @deprecated]
[* @uses		[Value]]
*/
```

#### 1.7.2: Functions and Methods

```php
/**
[* @todo]
*
* Description
*
* @name			[Value]
* @version		[Value]
* 
[* @author		[Value]]
* 
[* @copyright	[Value]]
[* @license		[Value]]
* 
[* @deprecated]
[* @uses		[Value]]
[* @static]
* 
[* @param]('S)	[Type]		[Name]		[Description]	[default value]]
* 
[* @return		[Type]		[Name]		[Description]]
*
[* @exception	[Type]					[Description]]
*
* @example		[value]
*/
```

#### 1.7.3: Properties

```php
/**
[* @todo]
* 
[* @author		[value]]
* 
[* @copyright	[value]]
[* @license		[value]]
* 
[* @deprecated]
[* @uses		[value]]
[* @static]
*
* @property		[Type]		[Name]		[Description]	[default value]
*/
```

Tabs should be used to keep everything inline as shown above for readability. Doc blocks **must** be used for all classes, functions, methods, and properties. Standard variables do not need doc blocks.

Author, copywrite, and license should always be used on functions but only used on methods and properties if they differ to that used for the class they are contained in.

#### 1.7.4: Comments

Comments should be used when making any change to preexisting code. If deleting a set of code then it should be commented using the `//` single line comment comment on each line that you wish to delete and **not** the `#` single line comment or the `/**/` block comment. The comment added when making a change should be in the following format.

```php
// [Description] [Your Name] [DateTime change made]
```

The **only** DateTime format used should be SQL DateTime (YYYY-MM-DD HH:mm:ss) And the 24 hour clock should be used for time.

Once code has been commented out (prepared for deletion) and **only** after a set period of time to make sure that nothing else breaks with the code change, then the code and deleters comment can be removed.

General comments should **only** be used with `//` and not `#` or `/**/` but can be any type of comment required.

### 1.8: Functions and Methods

#### 1.8.1: Format

Functions and methods should always return a value, if the function or method has nothing to return the a return value of 0 should be set for a pass and a positive integer value for a fail. These integers should be used as error codes and documented above the function or method in a doc block *@errorcode* (More on doc blocks [here](#17-doc-blocks))

If the function or method takes two or more parameters then it is acceptable to split the parameters over several lines tab indented but not if it only takes one parameter. There should be no space between the function name and the opening bracket, one space after the closing bracket and the opening curly bracket on the same line as the closing bracket.

A function or method should be no longer than 20 lines. If it goes over this then then it will need to be split in to multiple.

If three or more lines are repeated anywhere in the code, within or outside functions and methods then that code should be placed inside a function or within a method.

If the code is to do with an object then the code should be placed within a method for that object. Functions should only be created when the functionality has nothing to do with an object or is updating 2 or more objects, though that function should call seperate methods within each object to update each object.

```php
function my_function($foo) {
	// Do something
}

function another_function(
	$foo,
	$bar
) {
	// Do something
}
```

#### 1.8.2: Rewriting

When rewriting a function or method, changing a large portion, or adding / changing functionality that may break or cause advers affects to existing functionality currently using the function or method, the content should be moved to another function or method of the same name and "_v1", a new function or method of the same name and "_v2", the existing function or method should have an extra "version" parameter added to the end of the parameters of "$version = 1" and that used within a switch statement inside the original function or method to decide which of the new functions or methods to call. Any new parameters required for the new functionality should be set to default NULL.

*Existing code*
```php
function foo($bar) {
	// Existing code.
}

foo("my variable");
```

*Altered code*
```php
function foo_v1($bar) {
	// Existing code.
}

function foo_v2($bar, $bar_2) {
	// New code.
}

function foo($bar, $bar_2 = null, $version = 1) {
	$returns = null;
	switch () {
		case 2:
			$returns = foo_v2($bar, $bar_2);
			break;
		case 1:
		default:
			$returns = foo_v1($bar);
			break;
	}
	return $returns;
}

foo("my variable"); // Calls original code
foo("my variable", "my second variable", 2); // Calls new code.
```

All pre existing code using the original function or method should then be checked and converted to use the new function or method, tested thoroughly, and once all instances of the original function or method are ni longer in use, the _v1 function or method can be removed and the _v2 function or method can be moved into the original function or method and the version parameter removed from all instances.

### 1.9: Classes

*Todo*

### 1.10: Namespaces

Namespaces should wither be single line or block, and should be the first line in the file. When using the single lione namespace definition then there should be a blank line between the definition and the first line of code. When using a namespace block then all code within the namespace should be indented from the block, and the first and last lines of the block should be empty lines.

```php
<?php

namespace foo;

// Do something

?>
```

```php
<?php

namespace foo {

	// Do something

}
?>
```

### 1.11: License Blocks

License blocks should be at the top on the file and Square surrounded with a double single line '#' comment and each line space separated from the opening and closing sharp/hash characters. Line content should be no more than 70 characters. The first line should be blank and the last line should be the the last line of the license.

An example of the MIT license would be as follows:

```php
<?php

###########################################################################
##                                                                       ##
## Copyright (c) <year> <copyright holders>                              ##
##                                                                       ##
##                                                                       ##
## Permission is hereby granted, free of charge, to any person obtaining ##
## a copy of this software and associated documentation files            ##
## (the "Software"), to deal in the Software without restriction,        ##
## including without limitation the rights to use, copy, modify, merge,  ##
## publish, distribute, sublicense, and/or sell copies of the Software,  ##
## and to permit persons to whom the Software is furnished to do so,     ##
## subject to the following conditions:                                  ##
##                                                                       ##
## The above copyright notice and this permission notice shall be        ##
## included in all copies or substantial portions of the Software.       ##
##                                                                       ##
## THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,       ##
## EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF    ##
## MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND                 ##
## NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS   ##
## BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN    ##
## ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN     ##
## CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE      ##
## SOFTWARE.                                                             ##
###########################################################################

?>
```

&nbsp;  
&nbsp;  

## 2: Javascript

Javascript should follow the same standards as PHP with the exception of naming. All should be readable real world names but with the following differences.

### 2.1: Variables

Variables should start with a lower case letter, contain no underscores and instead every word after the first to have the first letter capitalized.

### 2.2: Functions and Methods

Function and method names should start with a lower case letter contain no underscores and instead, every word after the first to have the first letter capitalized.

### 2.3: Classes

Class names should contain no underscored and instead have the first letter of every word capitalized.

&nbsp;  
&nbsp;  

## 3: HTML

*Todo*

&nbsp;  
&nbsp;  

## 4: CSS

*Todo*

&nbsp;  
&nbsp;  

## 5: SQL

*Todo*

### 5.1: Naming

*Todo*

### 5.2: Queries

All SQL commands should be capitalized. Queries should **NOT** end with a semicolon. Only single quotes should be used within the statement. When the statement is written in a string then the string should be surrounded with double quotes. The fields to select should be line separated, on a separate line to the select command, tab indented, and a comma at the end of each line. The same goes for where and having clauses. Update and insert statements should follow a similar layout as shown below. A delete statement or any other type of statement which would remove data, should **never** be written.

When used with PDO the the '?' and named placeholders should be used for any user inputted data.

**Example of a select statement:**
```sql
SELECT
	*
FROM `my_table`
WHERE
	`this_column` = 'foo'
	AND `that_column` = 'bar'
```

**Example of an insert statement**
```sql
INSERT INTO
	`my_table`
(
	`this_column`,
	`that_column`
)
VALUES (
	'foo',
	'bar'
)
```

**Example of an update statement**
```sql
UPDATE
	`my_table`
SET
	`this_column` = 'bar'
	`that_column` = 'foo'
WHERE
	`this_column` = 'foo'
	AND `that_column` = 'bar'
```

### 5.3: Tables

If the table has only one primary key then that should be named by table name underscore 'id'. So for the table my_table the primary key field should be ```my_table_id```


All tables must always have the following fields:

* date_created
* date_modified
* date_deleted

The 'date_created' field **can not** be NULL, should be of type *datetime*, but should be set to the date that the row was first created. This field should never be changed except for development purposes.

The 'date_modified' field **can not** be NULL, should be of type *timestamp*, and should **never** be set directly and instead a trigger should be used to update the value of this field to the current timestamp.

The 'date_deleted' field *can* be NULL, should be of type *datetime*, should be set on deletion of a row to the current datetime and set to NULL on un delete of the row. (More on deleting rows [here](#54-deleting))

### 5.4: Deleting

*Todo*

&nbsp;
&nbsp;

## 6: TWIG

*Todo*

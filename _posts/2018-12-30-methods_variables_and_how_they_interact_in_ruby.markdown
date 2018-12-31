---
layout: post
title:      "Methods, Variables, and How They Interact in Ruby"
date:       2018-12-31 00:37:45 +0000
permalink:  methods_variables_and_how_they_interact_in_ruby
---


Some of the core building blocks in the Ruby language are methods and variables. At first glance they can seem like simple concepts but how they interact with each other and certain nuances can give raise to some confusing situations. Before we can go about explaining these circumstances we need to define what methods and variables are separately.

A variable is a piece of data that is labeled with a name by using the single equals operator. A few examples seen below:
```
string_variable = "This is a string that is now set to a variable."
array_variable = ["This", "is", "an", "array", "of", "strings", "set", "to", "a", "variable"]
number_variable = 52
hash_variable = {:key => value, :key2 => value2}
```
The list above is to show that a variable can be set to most forms of data whehter it be a string, number, or hash. Now that the variables have been set using a single equals operator they can be called later on with just the set name: string_variable, array_variable, etc. The important piece about variables is to name it so it is easily located in correspondence with the function of your code. 

A method is similar to a variable in the manner that it saves code to a set name, however, with methods they will also preform functions. The set up of a method is different than using a single equals though, as it requires a "def" key word opener and to be closed with the "end" keyword.
```
def say_hello
puts "Hello World!"
end
```
Once a method is created it can be refered to by using a hash mark in front of its set name like so, #say_hello. To call the method above we would also use the set name, say_hello, and it would preform its function of printing "Hello World!" to the terminal display.

These examples were made to be simple just to explain the definitions of a method and a variable. Now that we know what both are we can talk about how they can interact with each other. Methods can contain variables to help save data for both manipulation and later use to avoid lengthy code. A more complex example of this:
```
def adding_to_an_array(items_to_add)
existing_items = ["basketball", "football", "baseball"]
   items_to_add.each do |item|
     existing_items << item
   end
 existing_items
end
```
The example above shows a variable "existing_items" set to an array of items. This allows the array to be called later for manipulation without having to relist the array and its items. The example is more complex as it includes an iterator "each", don't worry about this piece as it was to portray the interaction of variables and methods.

Where things can get tricky with the interaction between variable and method is something known as **scope**. The scope of something is the area in which it can be called while retaining its set value. It means that not all variables exist everywhere in a program. For instance if you were to have a variable that existing in all areas of a program and wanted to move that piece of code to a new file or program, that program could already have a variable with the same name it could risk overwritting the variable. 

The main forms of scope are global and local. For local scope it refers to either being inside or outside a method. If you set a variable outside of a method, it is local to outside the method will not be able to be called inside. This applies for variables set inside of a method as well, unable to be called on outside. The only way to use a variable set outside of a method inside is to pass it in using it as an agrument.
```
name = "Sam

def say_hello_with_name(name)
puts "Hello #{name}!"
end
```
Here we have the variable "name" being passed in to the method by using parantheses at the end of the method name and called using interpolation. Without setting the option for an argument to be passed in the set variable would not be able to be used inside the method.

Global scope is depicted by using a "$" in front of the variable name like so.
```
$global_variable = "This can be called anywhere in the program"
```
By setting a global variable it allows for it to be called anywhere in the code of a program. However, global variables should be used sparingly if at all as they can cause further complication to your code if used incorrectly.

Hopefully this has helped provide clear understand and direction on how to use methods and variables with each other and will allow stronger foundation for future coding in Ruby!

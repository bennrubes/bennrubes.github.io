---
layout: post
title:      " Objects and Attributes in Ruby"
date:       2019-01-19 23:08:48 +0000
permalink:  objects_and_attributes_in_ruby
---


In Ruby we deal with a lot of different methods, functions, variables, and so much more. Without objects in Ruby this would become very tedious if we needed to create multiple instances of very similar variables to run methods and functions on, as well as having to re-code multiple methods for these similar cases. Luckily Object Orientated Programming allows us to have multiple instaces of variables saved with the same methods and attributes for easy access and use. First lets talk about how to create an object and then we can go further into the attributes of them and their uses.

To create a new object in Ruby we start by having an opener labeled `class`, followed by a name or title for the object, starting with a capital letter to notate that it is in fact a new class, all closed up by the `end` keyword.
```
class Title


end
```
After this class have been created we can make new instances of the object by typing `"Title.new"`. We can also save the created values of our new instances as variables for easy call back, `new_title = Title.new` Once we have this foundation we can begin adding class or Object specific methods and attributes.

To create attributes there are two methods associated, these methods are known as getters/setters or readers/writers. How attributes work is that they require a method to set an appropriately labeled variable as well as one to call the value of that variable. The slight difference in variables within classes is to make them avaiable to each new instance of that object/class they are created as `instance variables` labeled with an `@` before their title/name. Examples of these methods and instance variables are as follows:
```
#this is a setter/writer method
def name=(name)
   @name = name
end

#this is a getter/reader method
def name
   @name
end

#this is our instance variable
@name
```
Here we see that the `name=` method takes in an argument to set the value of the instance variable. Now that these methods have been defined our new object can have the attribute of a name.

Having to always set the value of each attribute to each instance of the object individually can get pretty tedious. Luckily there is a way to have these attributes set when a new instance is created by using the `initialize` method. The initialize method is best put at the begining of our code so we can clearly see right off the bat which attributes and functions we want and have automatically once a new instance is made.
```
@@all = []

def initialize(attribute1, attribute2, attribute3, attribute4)
   @attribute1 = attribute1
	 
	 @attribute2 = attribute2
	 
	 @attribute3 = attribute3
	 
	 @attribute4 = attribute4
	 
	 @@all << self
end

def attribute1=(attribute1)
   @attribute1 = attribute1
end

def attribute2=(attribute2)
   @attribute2 = attribute2
end

def attribute3=(attribute3)
   @attribute3 = attribute3
end

def attribute4=(attribute4)
   @attribute4 = attribute4
end
```
This example requires at the very least a setter/writer method for each attribute otherwise we would get `NoMethodError` for each one trying to be set. The `@@all` in our example is known as a `class variable` notated by `@@` before the title. These tyes of variables are accesiable through all instances of a class. This variable was included to show that setting attributes isn't the only code that can be in the initialize method, we can also add and keep track of each instance created by pushing it's `self` into a class wide array.

Now we know that each attribuate requires either setter/writer method, getter/reader method, or both to be usable in an instance of a class; however, it can get make our code smelly as well as get a little tedious to constantly write out these methods. Once again, Ruby has a built in function to make this process faster, easier, and cleaner.  These options are known as macros. Macros can be used to automatically create the methods for writer methods, reader methods, or both by respectively using `attr_writer`, `attr_reader`, or `attr_accessor`.
```
#attr_writer :name is the same code below
def name=(name)
   @name = name
end

#attr_reader :name is the same code below
def name
   @name
end

#attr_accessor :name is the same code below
def name=(name)
   @name = name
end 

def name
   @name
end
```
Additional attributes can be included like so: `attr_accessor :attribute1, :attribute2,  :attribute3`

These are the definitions and core building blocks of Objects and attributes in Ruby and how they are used together. Once these foundations are set we can go on to adding in new methods into our class to operate on each instance created making it much easier to keep track of similar coded objects and files.


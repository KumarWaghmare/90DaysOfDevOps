**1. Data Types**

Data types are the classification or categorization of data items. It represents the kind of value that tells what operations can be performed on a particular data.
Since everything is an object in Python programming, data types are actually classes and variables are instance (object) of these classes.
Python has the following data types built-in by default: Numeric(Integer, complex, float), Sequential(string, lists, tuples), Boolean, Set, Dictionaries, etc.
To check what is the data type of the variable used, we can simply write:
```
your_variable = 100 
print(type(your_variable))
```
**2. Data Structures**

Data Structures are a way of organizing data so that it can be accessed more efficiently depending upon the situation. Data Structures are fundamentals of any programming language around which a program is built. Python helps to learn the fundamental of these data structures in a simpler way as compared to other programming languages.

Lists Python Lists are just like the arrays, declared in other languages which is an ordered collection of data. It is very flexible as the items in a list do not need to be of the same type
Tuple Python Tuple is a collection of Python objects much like a list but Tuples are immutable in nature i.e. the elements in the tuple cannot be added or removed once created. Just like a List, a Tuple can also contain elements of various types.
Dictionary Python dictionary is like hash tables in any other language with the time complexity of O(1). It is an unordered collection of data values, used to store data values like a map, which, unlike other Data Types that hold only a single value as an element, Dictionary holds the key:value pair. Key-value is provided in the dictionary to make it more optimized.

**3. Give the Difference between List, Tuple and set. Do Hands-on and put screenshots as per your understanding.**

List, Tuple, and Set are all built-in data types in Python that are used to store collections of items. The main difference between them is their properties and usage:

List: Lists are ordered collections of items, enclosed in square brackets [] and items are separated by commas. Lists are mutable, which means you can add, remove, or modify items in a list.
Tuple: Tuples are also ordered collections of items, enclosed in parentheses () and items are separated by commas. Unlike lists, tuples are immutable, which means you cannot add, remove, or modify items in a tuple.
Set: Sets are unordered collections of unique items, enclosed in curly braces {}. Sets are also mutable, like lists.

**4. Create below Dictionary and use Dictionary methods to print your favourite tool just by using the keys of the Dictionary.**
```
fav_tools = {
    1:"Linux", 
    2:"Git", 
    3:"Docker", 
    4:"Kubernetes", 
    5:"Terraform", 
    6:"Ansible", 
    7:"Chef"
}
```
To access the element of the Dictionary using the key, you can use the square brackets [] notation like this:
```
print("My favourite tool is", fav_tools[5]) # this will print "Terraform"
print("My second favourite tool is", fav_tools[4]) # this will print "Kubernetes"
```
![4](https://user-images.githubusercontent.com/121767243/212940845-2c6adce2-72af-46ba-b9b4-98aa82e7c7d6.png)

**5. Create a List of cloud service providers and add an item to a List and sort it in alphabetical order.**

Write a program to add “Digital Ocean” to the list of cloud providers [“AWS”, ”GCP”, ”Azure”] and sort the list in alphabetical order.

This will print [“AWS”, “Azure”, “Digital Ocean”, “GCP”]
![5](https://user-images.githubusercontent.com/121767243/212940936-69c62630-58f1-406e-b2b6-8641d1200df4.png)


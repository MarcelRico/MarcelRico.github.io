---
layout: post
title:      "Avoid These Top 3 Sneaky Ruby Array Pitfalls"
date:       2020-01-12 15:56:46 +0000
permalink:  avoid_these_top_3_sneaky_ruby_array_pitfalls
---


**Arrays** are one of the most important data structures that we come across, when learning a new programming language. They can hold large amounts of information, stored in an ordered fashion, and can contain a variety of data types (Strings, Booleans(TrueClass/FalseClass),Integers, and *Spoiler Alert:* can even contain other nested data structures themselves).

Lets look at some Array Examples:
```
#=> Creates array whose elements are characters of Type: String
array = ['a','b','c','d']       

#=> Creates array whose elements are Boolean values of Type: TrueClass / FalseClass
array = [true,false,true,true]  

#=> Creates array whose elements are numeric values of Type: Integer
array = [1,2,3,4,5]             

#=> Creates an array whose elements are hashes (Array of Hashes NDS)
array = [{name:"John Doe"},{email:"john.doe@example.com"},{age:25},{occupation: "Medical Student"}]
```

The raw power that Ruby Arrays can provide can have you feeling like Vegeta here:


![](https://media.giphy.com/media/m32zTHRBlr8WY/giphy.gif)


But before you go flying off into the sky with your newly found Super Saiyan Ruby Array powers, there are some pitfalls you'll want to avoid. As with any data structure Ruby Arrays have certain requirements that we, the developers, need to take into consideration, and be actively thinking about when using them in our applications.

<hr>

## Ruby Array Indexing

> “ Should array indices start at 0 or 1? My compromise of 0.5 was rejected without, I thought, proper consideration. ”
> [Stan Kelly-Bootle](https://en.wikipedia.org/wiki/Stan_Kelly-Bootle)

Indexing is the mechanism by which we are able to access the elements of an array as needed. In most programming languages (Ruby being no exception), **the elements of an Array are referenced by indices (numbers) starting at the 0th element** and going all the way up to the **length of the array - 1 **

Lets take an Example:

```
array =     ["Hello", "how", "are", "you", "today?"]
Elements:       0       1      2      3       4

```

If we wanted to access the word "are" that is stored in **array** we could do so by using the following line of code:
```
array[2]  #=> "are"
```

Similarly if we wanted to access "Hello", the first element in the **array** we could do this:
```
array[0]  #=> "Hello"
```
<hr>
<br>

Simple enough, except what if we were to forget that** array indices start at the 0th element** and try to get the first element "Hello" like this:
```
array[1]  #=> This will return "how" which is not what we wanted.
```

This leads us to:

**Pitfall #1: Forgeting that Ruby Array indices start at 0**. 


With a small example like this, its relatively easy to catch this type of mistake but as we introduce more and more code these nasty types of errors can creep up on you and blend into your code. 

Worst of all, **They won't throw an error** which means you will only know you have one of these errors if your data is incorrect. **Keep an eye out for Creeping Pitfall #1**

![](https://media.giphy.com/media/COYGe9rZvfiaQ/giphy.gif)
<hr>

Okay great we now know how to access elements of an array, and we remember that indices of an array start at the 0th element, Awesome! But what would happen now if we were to do this:

```
array[5] #=> nil
```

As shown above we would find that we would return nil instead of the last element in the array which is "today?". Why is this? 

**Pitfall #2: Using indices that are greater than (length of array -1)  will return nil since they technically do not exist**

Think about it, our original array was:

```
array =     ["Hello", "how", "are", "you", "today?"]
Elements:       0       1      2      3       4
```

In that case there was no 5th element to reference. **It doesn't exist**. When ruby is asked to return a value from an index that does not exist, it will return nil, as [nil is how ruby represents a non-existant value](https://www.rubyguides.com/2018/01/ruby-nil/).

<hr>

Okay so in a Ruby array, the starting index is 0 and the last index is (length of array - 1), cool! What about negative indices? 

Take for example:

```
array[-1] #=> ?
```

Surely using negative indices will result in Ruby returning **nil**, since we don't have a -1 element right?


Nope. Introducing:

<br>

**Pitfall # 3: Negative indices will reference Ruby Array elements starting from the end of the Array.**
 
 In the case above, Ruby would actually return the value "today?" as it is the last element in the Array:
 
 ```
 array[-1] #=> "today?"
 ```
 
 Lets try another case of negative indices:
 
 ```
 array[-3] #=> "are"
 ```
 
 In that case Ruby would return the word "are" as that element is the 3rd element from the last element in the array moving backwards.
 
 To see this more easily lets take our earlier array model, and swap it with negative numbers:
 
 ```
array =     ["Hello", "how", "are", "you", "today?"]
Elements:      -5      -4     -3     -2      -1
```

Okay last example with negative indices, I promise:

```
array[-8]
```

Here we clearly do not have a -8th element not even if we start from the end of the **array**, so what would happen? In this case Ruby would return  **nil** because
the -8th value is non-existant:

```
array[-8] #=> nil
```

## Last Note
Keep in mind, most of these pitfalls do not happen when you hardcode, but instead usually occur programatically (e.g. one of your methods attempts to reference an element  in your array incorrectly), and thus upon runtime.

That being said don't fear! Arrays are an amazing Data Structure that when used properly, have the potential to take your code to the next level. Become familiar and comfortable using them, and you might find you have a new source of:

![](https://media.giphy.com/media/5M2ZVnDZOwJzi/giphy.gif)
<br>
<hr>

For more information on Ruby Arrays check out the [official ruby documentation here](https://docs.ruby-lang.org/en/2.7.0/Array.html)





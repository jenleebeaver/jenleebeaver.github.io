---
layout: post
title:      "Class VS Instance Methods "
date:       2020-04-02 08:35:37 -0400
permalink:  class_vs_instance_methods
---


If you google the above the first thing that will come up is - 

"In Ruby, a method provides functionality to an Object.  A class method provides functionality to a class itself, while an instance method provides functionality to one Instance of a class."

While this is a very easy to understand explanation I would like to use my own object oriented code and an analogy to explain the difference between the two.

First lets analyze some of my code for my CLI project.

This is an art.rb file and creates and initializes a class with attributes to access art data from the MET API:

```
class CLIproject::Art

    attr_accessor :title, :primaryImage, :accessionYear, :department, :culture, :dimensions
    @@all = []

    def initialize(hash)
        #mass assignment. .send is running what is inside the block. ie. key = value. Here we are able to return a single object.
        hash.each {|key, value| self.send(("#{key}="), value)}
        save
    end

    def self.all
        @@all
    end

    def save
        @@all << self
    end

    # custom instance methods of needed - this allows people to give a critique 
    def create_note(input)
        self.note = input
    end

end
```

The first and most obvious way to identify class methods is when you see the keyword *self*.  This refers to the class *itself*.  So, method self.all would be a class method that essentially refers to class CLIProject::Art (which is associated to other files I have built).   This also means that any method defined with *self* is also a global variable meaning it can be accessed everywhere within the file. 

Now, our instance methods define one copy of our class. So, here we have **attributes** that we are **accessing** from the MET API of a title, primary image, year of accession, department, culture, and dimension of the art piece.  There is alot more data we could access in our API, but I chose to simplify the data into these 6 bits.  These attributes belong to an instance that we are grabbing from a key in a hash from our API. This is coded in the *initialize method*.  That makes initialize an instance method along with *save* and *create_note*.  *Save* is pushing the data we are grabbing into our @@all object and *create_note* is supposed to be way for people to leave a comment, but I didn't build this out.  

Essentially, our instance method grabs and defines data of an individual or *new* copy of our class. This is like having different modes of scales.  For instance major scales have the same increments of notes following the same framework of WWHWWH (W- whole note step H- half note step), but entirely different notes.  So, we could have a class following the scale framework and create different instances of the class defining specific individual scales. If we wanted to we could probably even change the predefined scale for an instance and move into another mode!

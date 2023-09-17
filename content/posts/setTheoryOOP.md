---
date: "2023-07-14"
tags:
- Technology
- Programming
- Ruby
- Philosophy
title: Object Oriented Programming is just Set theory
---

# Object Oriented Programming is just Set theory

So earlier today I just finished my first full course on the Ruby programming language, Head First Ruby by Jay Mcgavern. Ruby was written and created by Yukihiro Matsumoto in order to make programmers happier and to create a language that is more object-oriented than Python. And, honestly, I think he succeeded. 

About a century or two earlier, the mathemetician Georg Kantor came up with the idea of Set theory which appears to be the foundation for Object Oriented Programming. 

## What is Set Theory

So what exactly is Set Theory? Set theory is the idea that all objects and concepts are composed of a set of one or more smaller things. Think about a computer for example. The computer is a "set" of other components. It is made up of the software that allows it to run, the memory sticks, the motherboard, cpu, etc. In short, a computer is a set of parts, none of which is the computer on its own. 

Going up from the example of a computer, a network of connected computers is likewise comprised of the servers and clients it connects. This is what we can call a superset. Going further down, the cpu and other parts are made of transistors and other small machines. This is what we can refer to as a subset. 

## What is Object Oriented Programming

Object Oriented Programming takes this concept and applies it to the world of software. An object, also called a class, is composed of a set of definitions or characteristics. Lets look at an example from Ruby. 

```
class Dog 

  def bark
      puts "Woof!"
  end
  
  def loves_life
      puts "The dog is happy!"
  end

```

Here we have created an "object" or a set that we call "Dog." Since dogs are often defined by barking and loving life, we can define these as methods or characteristics of the dog. Using this class, we could also create a subclass or subset of dogs. Chihuahuas, for instance, act like they are bigger than they really are and are composed of trembling and hate. Nonetheless they are dogs. 

```
class Chihuahua < Dog
    
    def composition
        puts "70% hate, 30% tremble"
        
    end

```

The < symbol in the code above shows us that Chihuahuas are a sub-class of Dogs. In other words, they are a sub-set of the set of Dogs. 

## Ok, that's interesting, but why give a damn?

I think this is an interesting topic to explore because it seems to reflect something inherent in our reality. Furthermore, the idea paralells or intersects with the idea of forms, where the things of this world are shadows of a higher realm. Ultimately, everything if composed of a set of other elements. Humans are made of cells, cells of molecules, molecules of atoms, etc. 
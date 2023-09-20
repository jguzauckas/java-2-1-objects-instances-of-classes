# Objects: Instances of Classes

Java is an **object-oriented programming language**, which is a methodology of design in programming. This chapter starts to unveil what *object-oriented* means and how Java implements it.

--

## Classes

In order to understand objects, we have to first understand **classes**. A Class is often referred to by many analogies:
- A framework
- A blueprint
- A mold

Essentially, it is a set of instructions to define what it means to be what the class represents. For example, if a class represents a person, then it contains instructions that defines what it means to be any given person. This can include:

- Places to store information about them (**variables**)
- Initial instructions for how to set up a person (**constructors**)
- Instructions to perform actions as that person (**methods**)

While we won't worry about all the specifics in this chapter, here is the `Person.java` file with a basic example:

```java
public class Person {
    private int age;

    public Person(int a){
        age = a;
    }

    public void sayAge(){
        System.out.print(age);
    }
}
```

Again, don't worry about the specifics here, that will be covered by Chapter 5, but I want us to notice the important pieces that make up a class. Classes almost always have **variables**, which is a way to store information when we want to use the framework/blueprint/mold to create a thing based on the class. The variable in this example is:

```java
private int age;
```

**Constructors** are instructions on making a thing based on a class. The constructor in this example is:

```java
public Person(int a){
    age = a;
}
```

Constructors will always share their name with the class, so since the class was called `Person`, the constructor also has to be called `Person`. They will often ask for information to be input (in this example it was an `int` referred to as `a`), to save to relevant variables in the class (in this case the `age` variable we saw earlier).

Finally, they have instructions for actions, referred to as **methods**, which in this example was:

```java
public void sayAge(){
    System.out.print(age);
}
```

If a Person was ever asked to **sayAge**, this is the set of instructions they'd follow. Methods often allow us to simplify our coding by making these instructions once and using them on multiple different people.

With a class ready to go, we can now talk about what we do with them.

---

## Objects

An **object** is referred to as an **instance** of a class. When we say *instance*, we are referring to the idea of using the framework/blueprint/mold to create something to use. This has all of the information from the class, but it is fundamentally separate and won't shape future uses of the framework/blueprint/mold.

This object will have its own copy of any variables to store information in, so the variable `age` from above isn't shared by different people, each Person gets their own copy to store an age in.

Here is a sample from `ObjectNotes.java`, which goes back to our more traditional code organization:

```java
Person john = new Person(25);
john.sayAge();
```

We'll digest all of the specifics here at a later date, but look at a couple of commonalities from what you already know:

- Variable initialization (declaration and assignment)
- The dot operator `.`, like in `System.out.print()`.

---

## Relationship Between Classes and Objects

Putting the two pieces together, a class is the definition of attributes and behaviors that we can use to clearly define and use an object.

Oftentimes, a single class will get used many times. For example, think about a program where we define many students using the Person class; we save ourselves a lot of time by only writing the class once but using it many times to create different objects.
---
title: Clean Code
tags: [book, programming, cleancode]
---

Initially, I believe that all knowledge should help you whether you are prepared to understand it, use it or not. Additionally, I couldn't have arrived to this conclusion about the book without reading it. So I'm writing my opinion after having finished the book.

## About the book

![](/assets/img/galaxy.png){:height="300px" width="700px"}

As from the beginning of the book, there are enumerous passages of Robert Martin's vast knowledge. You can read how the authors thinks about how clean code can be used and also about his code philosophy. 
It's very gratifying to appretiate his knowhow through the pages.

Beyond the author's knowledge you can also see some code samples. Robert puts some interesting comments to make the reader think about them like "Is this the best approach ?", "Why do the lack of clean codes into these lines slow you down?".

There is a structure created by Martin that enumerates the good practices and helps you to see it all clear. I put a compiled version of themes bellow:

* Comments
* Environments
* Functions
* General points
    - Duplication
    - Overrides
    - Excess of information
    - Unacessary things
    - Switch statements
* Java
* Tests

It also adds some information about Domain Driven Design, Test Driven Development, DRY(Don't Repeat Yourself) and more. It doesn't go very deep into these subjects, but it has a good link between all of them including the Clean Code, the relationship between them and the delivery of business value.

## Applying clean code

After reading the book you can take some rules and apply into your code.
Like, in the code bellow, you can notice some bad practices.

{% highlight java %}

public String functionXpto(String x) {

    List<String> l = Arrays.asList("Batman", "Gandalf", "Wolverine");

    for(String i : l) {
        if(i == x) {
            // return value
            return i;
        }
    }

    return null;
}

{% endhighlight %}

As you can see, several good practices from the book are missing.
- Meaningful variables
- Do one thing
- Descritive names(from functions)
- Explain yourself in Code
- Bad comments

Refactoring this code. You can have something like this.

{% highlight java %}

public String findValueInList(String value, List<String> list) { 
    return list
    .stream()
    .filter(item -> item.equals(value))
    .findAny()
    .orElse(nul);
}

{% endhighlight %}

This is a short sample of code and it only cover the beginning of some bad practices. Of course, these are very simply ones but explains how even little funtions can be confuse. Imagine complex business rules over a project that you need to fix a bug.

## Why should you read it ?

![](/assets/img/morty-book.jpeg){:height="300px" width="700px"}

Developers are always looking for self-improvement inside the software engineering world and this isn't new. I know that there are a lot of concepts that developers should be concerned about, however code interpretation is one of them. 

Definitely, the best developers are the ones who care about how the code is delivering the purpose of the business. That interpretation, when done correctly, can help other developers to create new features or even execute a debugging.

This book is about how you can improve your code programming for better understanding. If you notice that you need to improve your understanding about programming codes or even review your thoughts about code style, you should probably add this book onto your list.

It's clear to me that this is a book that may be difficult for new developers. Experience gained in previous projects can help you visualize or understand how the author arrived to these solutions and how this really makes sense.

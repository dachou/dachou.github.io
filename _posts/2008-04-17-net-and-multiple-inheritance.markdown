---
layout: post
title:  ".NET and Multiple Inheritance"
date:   2008-04-17 12:00:00 -0700
---
(originally published at [https://blogs.msdn.microsoft.com/dachou/2008/04/17/net-and-multiple-inheritance/](https://blogs.msdn.microsoft.com/dachou/2008/04/17/net-and-multiple-inheritance/))

Occasionally I get questions on why does .NET not support multiple inheritance. It is actually a pretty interesting question to contemplate with, though I usually start the conversation by asking: "what issue requires multiple inheritance to solve?".

More often than not, the question surfaces when people are trying to "do the right thing" by correctly refactoring code in an object-oriented manner, and facilitate code reuse by using inheritance, but encounter challenges when trying to reuse methods and code behaviors defined in separate places of the class hierarchy. Thus the most "natural" question was, if I can just inherit the code from these classes...

Many decisions in language design, just like software projects, are balancing acts between various trade-offs. There are many very interesting conversations happening in the community, such as the debate on generics and closures on the Java side (for example: [How Does Language Impact Framework Design?](http://www.artima.com/weblogs/viewpost.jsp?thread=222388) and [Will Closures Make Java Less Verbose?](http://www.artima.com/weblogs/viewpost.jsp?thread=227728) and James Gosling's thoughts on [Closures](http://blogs.sun.com/jag/entry/closures)). Interesting to see how much thought goes into each seemingly small decision on adding specific language features, or not adding them.

There were many factors that influenced the .NET team to favor not implementing multiple inheritance. A few of the more prominent ones include:

- .NET was designed to support multiple languages, but not all languages can effectively support multiple inheritance. Or technically they could, but the complexities added in language semantics would make some of those languages more difficult to use (and less similar to their roots, like VB, and for backward compatibility reasons) and not worth the trade-off of being able to reuse code in the manner of multiple inheritance 
- It would also make cross-language library interoperability (via CLS compliance) less of a reality than it is today, which is one of the most compelling features of .NET. There are over 50 languages supported on .NET in over 70 implementations today 
- The most visible factor is language semantics complexity. In C++ we needed to add explicit language features in order to address ambiguities (such as the classic diamond problem) caused by multiple inheritance, such as the "virtual" keyword to support virtual inheritance to help the compiler resolve inheritance paths (and we had to use it correctly too) 
- As we know code is written 20% of the time, but read 80% of the time. Thus advocates on simplicity side prefer not to add language features for the sake of keeping semantics simple. In comparison C# code is significantly simpler to read than C++ code, and arguably easier to write 

Now Java doesn't support multiple inheritance as well, though probably for a different set of reasons. Thus it is not a case of simple oversight in design or lack of maturity, as it was a careful and deliberate decision to not support multiple inheritance in the .NET and Java platforms.

So what's the solution? Often people are directed to using interfaces, but interfaces don’t lend themselves very well to meet the requirements of reusing code and implementing separation of concern; as interfaces are really intended to support polymorphism and loosely-coupled/contractual design. But other than trying to tie behaviors into object inheritance hierarchies, there are many alternative approaches that can be evaluated to meet those requirements. For example, adopting relevant design patterns like Visitor, frameworks like MVC, delegates, mixins (interfaces combined with AOP), etc.

Bottom line is, there are considerably elegant alternatives to inheriting/deriving behavior in class hierarchies, when trying to facilitate code reuse with proper re-factoring. Plus trade-offs in code reuse vs. the costs incurred to manage the reuse is another full topic in itself. In some cases it may have been simpler to have multiple inheritance and access to sealed classes, but the trade-offs may have been greater costs in other areas.

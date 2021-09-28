---
title: Algorithms and data structures
author: Thinkful
team: grading
time: 80 minutes
uuid: 3f6099cc-5c2d-418e-9f9e-610841cf5e64
timeHours: 1.3333333333333333
---

## Basic data structures

There have been plenty of times in this program where you've used an algorithm or data structure. In fact, you've used them in the vast majority of the program so far. But you may have simply taken the algorithms and data structures for granted, assuming that someone else has optimized the algorithm or forced you to use the right kind of data structure for the job.

So why is it worth spending the time on the specifics?

Simply put, you won't always be able to use someone else's framework to solve your problems. Furthermore, some situations may need to be highly optimized, and you can't rely on others to do that for you. When you're dealing with a static dataset of a few hundred thousand rows, you may care about efficiency—but often, the stakes aren't very high. The difference can often be between waiting for half a second or two seconds, which isn't a difference that's worth spending hours trying to optimize.

But what if you're trying to run your model in production? And what if your model is handling hundreds of events per second? How do you store those events? How do you handle new entries and solved entries? Now you want to optimize that process as much as you can. A difference of milliseconds can hugely affect how well this process scales.

This process can be as simple as managing a queue, which is a classic example that will allow you to introduce both simple data structures and the basics of algorithms. Many things related to data science involve managing a queue, from support tickets to data requests.

For this example, just think of a simple queue.

![Waiting for doughnuts](Line_in_front_of_Voodoo_Doughnut.jpg)

For this purpose, your queue is a series of arrivals that need to be remembered, with each entry needing some process to be done to it. You have to manage a queue because sometimes your arrivals might come more quickly than you can process them, and you don't want new arrivals to get lost if you're busy. In other words, you'll have two separate stages: the _queue_ (the topic here) and the _processing_ (which you'll learn about in the next checkpoint).

What are the ways that you could handle this queue?

## The list

The first and likely most familiar data structure for handling this kind of data is a *list*. In formal computer science, a list is defined slightly differently than the particular implementation in Python. You want to think about data structures in the abstract, not how any particular language implements them. Once you have a good handle on the abstract data structures, you can dive into language specifics.

Now, back to the list.

Essentially, a *list* is an ordered sequence of items with an incrementing index. What does that actually mean? Well, it's a lot like the NumPy arrays and Python lists that you've worked with so frequently in this program. Your entries each have an index (starting at `0`), and that index increases for each item in the sequence.

This is convenient in several ways. You can call any element of the list as long as you know its index. If you want the third element, you just have to look for index `2`. You can also easily add new items to the list without changing anything in the preexisting list. You just need to add the new item at the next index.

However, this indexing also comes with some inconveniences that a queue does a particularly good job of revealing.

Imagine that you wanted to run a *first-in-first-out queue* (also called a *FIFO queue*). This means that you want to handle the person who's been around the longest first. They should be at the head of your list, in position `0`. So say that you want to remove them from the list. What happens to the list now? Do you see the problem?

Well, if you are using a list, you need to keep your first entry indexed with `0`. So when you remove an element, you have to go through the remaining entries and decrease their index values accordingly. This may not be that much of a problem if the list is small. But again, when you're looking for real efficiency, that is going to take some time that you don't want to sacrifice. Imagine if you removed the first book on this shelf:

![Books!](books.png)

To keep your indexes straight, you'd have to shift every book over by one. That's a lot of work.

As for implementing lists that you can actually use, Python has you covered. Python lists and NumPy arrays both work this way, so you'll rarely implement your own version lists from scratch. That's not the case with some data structures that you'll learn about later.

## Efficiency and fundamental steps

You've been learning about efficiency and how it can be important in some contexts, so it would be useful to have formal definitions of efficiency and inefficiency. [Big O](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/) is a way of quantifying the efficiency of a process in terms of the size of the data structure that you're dealing with as input.

Think about breaking a process into the smallest steps that you can imagine. In programming, these _steps_ (or *fundamental instructions* in computer science lingo) are things like assigning a value to a variable, reading a value, or comparing two values for equality. When you think about efficiency, try to think about how many steps it would take for you to complete a process. And consider how that number changes as the size of your input data increases. Big O is about asymptotic efficiency, which incorporates this approaching of a limit.

Can you see what the worst-case efficiency of removing an item from a list is?

The worst-case scenario is typified by the FIFO queue. If you want to remove an item from a list, you'd have to remove that first item and then adjust every following entry's index. This would be called O(n), where *n* represents the length of your list. The longer the list, the more time that it takes. And that time scales linearly.

## Linked list

Now, consider how you could get a bit more efficient with operations like that. This is where a type of structure called a *linked list* comes in handy. In a linked list, you maintain the order of your items but do not have an index. Instead, each entry is linked to the next item. Linked lists can be either singly or doubly linked, depending on whether the links only point forward or whether they also point backward.

What's the advantage of getting rid of indexes and pointing to the next item instead?

One advantage is deletion, which is O(n) for lists but only O(1) for linked lists. This is because you only update the pointer (or pointers, in a doubly linked list) that was pointing to the removed item, rather than updating the index of every item that follows.

But what about accessing? *Accessing* is the process of going to find a specific value. Here, linked lists are at a disadvantage to lists, where accessing values is O(1). For linked lists, the efficiency is O(n); you always have to start at the first item and move through the chain until you get to where you want. There is no fast way for you to go to a specific place because there is no index for you to reference.

Python doesn't include an implementation of a linked list. So to use one, you have to write it yourself. This is typically done using a `Node` class that stores the value of an item plus a pointer to the next node (and to the previous node, in a doubly linked list).

Here's an implementation of linked lists in Python. This includes methods for common operations like appending, removing, and inserting nodes. Review the code and the comments thoroughly before moving on.

<iframe src="https://trinket.io/embed/python3/17e1d1c231" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Queue

There's a version of the linked list that is a bit more specialized, and it's designed to solve exactly the queueing problem from the beginning of this checkpoint. Unsurprisingly, it's called a _queue_.

A queue is a single linked list, but with the special feature that items only come in at one end and leave at the other. In other words, it's a FIFO queue. Think of entering the queue as *enqueuing*, where items get linked to the last element of the list. You can then only remove items from the front of the line via a *dequeuing* process.

This is an optimal data structure for managing your queue because it lets you do exactly what you'd want to in O(1) efficiency.

Its drawbacks are in accessing and searching. To get an element from another part of the queue or search the queue to see if an element is present, you'd fall into O(n) efficiency. This isn't the end of the world, but it does illustrate that queues aren't perfect for everything.

## Stack

Lastly, you can make a *stack*. This could also be a last-in-first-out (LIFO) queue. In this case, it's a linked list where items are only added or removed from one end. This means that to access an element further down the queue, you'd have to first remove all preceding elements. It's not ideal for many circumstances, but it does have its uses.

![Full stack developer amirite?](stack.png)

As mentioned earlier, this is just scratching the surface of this topic. Luckily, there are plenty of other resources on algorithms and data structures in Python. If you want to dig deeper, check out [Interactive Python](http://interactivepython.org/runestone/static/pythonds/index.html) and [Python School](http://pythonschool.net/category/data-structures-algorithms.html). If you need a refresher on Big O notation, [this tutorial on complexity](http://discrete.gr/complexity/) may be useful. As you review these other sources and scour the internet for other implementations, keep in mind that these things can be done in many different ways. There is no single right way or right choice; don't be surprised to see variations.

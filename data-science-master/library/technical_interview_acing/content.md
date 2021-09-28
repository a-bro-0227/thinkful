---
title: Acing the technical interview
author: Thinkful
team: grading
time: 150 minutes
uuid: 3b83cfe7-8d23-4630-892c-fb15b66f8fe6
timeHours: 2.5
---

> "Give me six hours to chop down a tree and I will spend the first four sharpening the axe." —Abraham Lincoln


The objective of this checkpoint is to provide you with actionable tips on preparing for a technical interview, and to ensure that you know what to expect before, during, and after the technical interview. 


## Before the interview
### Simulate real conditions

Your muscle memory is so trained to type code at a computer that writing it at a whiteboard can feel jarring. By practicing ahead of the interview, you'll feel more comfortable in these conditions. 

That means finding a whiteboard—and the bigger, the better! This should ideally be a classroom-size whiteboard that you'll stand up at and write. Of course, you might not want to spend the money on a giant whiteboard to keep in your home, so try finding a whiteboard to practice on at your local public library, career center, or community college. If your results come up short, a mini-whiteboard will provide a reasonable approximation. 

In the following checkpoint, you'll receive a series of practice questions. *Do not look at a question until you're ready to conduct the interview!* The typical whiteboard interview assumes that you have *never* seen the question before. You take the question and get to work, without using the internet. 

Practice the interview just as if you were actually there. The next section offers a framework for tackling a technical interview question—use it to practice. 
 

### Find a friend

When preparing for the technical interview, consider trading interview roles in your pair or with another prospective data scientist. This way, you can practice asking questions and explaining your code, both of which are indispensable parts of the technical interview. You'll also see how others approach a technical interview question, and how to best present your questions and proposals to an interviewer.  


### Find a platform

Digital coding platforms won't prepare you to work on a whiteboard per se, but they do provide a way to practice coding challenges with others. Along with Kaggle for data science projects, consider outlets like Codewars, HackerRank, and LeetCode. 


### Review, review, review

A technical interview is like performing data science on a desert island—you need to break through a problem with none of the tools of modern living. That means that you'll need to be your own Stack Overflow. Take a look at the code you are writing—is it PEP-8 compliant? Explain aloud any issues you are seeing. Talk to yourself and ask yourself questions out loud while you work.

You aren't expected to be a human computer, but you should be conversant enough in technical topics to frame the basics of a whiteboard interview solution and to ask your interviewers useful questions. 


### Research the situation

Every company does things in its own way. Do some research on how technical interviews are conducted where you're interviewing. If you know someone who works there or can find someone through your network, ask. Take a look at who will be conducting the interview to get a sense of their favorite topics—it's likely that these topics will show up in the interview. 

### Relax!

Technical interviews are draining, so come well rested. You might feel the need to prepare all night for the interview, but cramming doesn't work. Relax; you've got this! 

## During the interview
### They don't call it a whiteboard interview for nothing

When working through a technical interview, err on the side of writing things down. Even if the question does not require code for a solution, consider using the whiteboard to jot down your thoughts and draw illustrations. For example, if you're asked about backpropagation, why not draw an example? 

This demonstrates your note-taking abilities and diligence. Of course, the more that you write on the board, the more you need to plan and organize. Take the time to write legibly and to anticipate how much room you'll need for later steps. 

### Follow the flowchart

A technical interview can be intimidating. You're coding and answering complex questions in an unnatural manner in front of your prospective boss and coworkers. This is your chance to stay calm, ask good questions, and come to a reasonable solution. 

Interview day is a rush of emotions, and it can be difficult to think straight. Use the below framework as a guide for working through problems. This is a modified version of the flowchart offered in the whiteboard interview classic [Cracking the Coding Interview](http://www.crackingthecodinginterview.com). The book was written with developers rather than data scientists in mind, but it might be worth a look, depending on the role that you're interviewing for. 

Like with most other data science workflows, this is an iterative process. Coming up short at one step does not signal failure—go back to another step and try again. 


1. **Listen.**

   Deeply listen to the question. Repeat it out loud. Even write it down on the board so you can refer to it constantly. If you've heard the question before, say something. It's usually assumed that this is brand-new material for you. Pretending to crack a problem that you know by heart won't look good. Listen "out loud" by asking lots of questions about the prompt. You are gathering as much information as you can before you get started. 

2. **Determine inputs and outputs.** 

   At its core, a computer program inputs information, performs some process on it, and outputs a result. Before you work on the process, determine the inputs and outputs. What kind of data do you need to test the problem? What shape does it take? What results are necessary for an answer? 

3. **Determine boundaries and assumptions.** 

   > There is a story that has been going around about a physicist, a chemist, and a data scientist who were stranded on a desert island with no implements and a can of food. The physicist and the chemist each devised an ingenious mechanism for getting the can open; the data scientist merely said, "Assume that we have a can opener!"

   The above quote is a long-standing joke that was initially designed for economists, but it can easily be repurposed for data scientists, as seen here. To meet their theoretical requirements, data scientists (and economists) can make quite a few assumptions. Do the same for your whiteboard interview: assume that the data is normally distributed or that there are no outliers. If you're working with lists, assume that they're one dimensional with no missing values. 

   The interviewer might push back at some of these attempts to "assume away" potential problems, but they're seeing that you can identify problems before they develop. 

4. **Pseudocode your solution.**

   So, you've identified the inputs, outputs, assumptions, and potential issues of your program. Time to start writing? Not so fast! One of the most common pieces of advice for coding interviews is not to start coding too quickly. Take time to chart out your objective and determine how you will get there. 

   Before writing the code, write the *pseudocode.*  Your pseudocode will be a part-English, part-Python outline of a computer program. This lets you and your interviewer agree at a high level what the code *should* do, before getting into the details about how to best implement the code in Python. 

5. **Code your baseline solution**

   Now, you can finally get coding. Convert the pseudocode into real code as literally as you can. This will be your baseline solution. This solution might be pretty ugly, but you can touch it up later. Don't think too hard about how to use the fewest number of variables, or whether you should write a function. Just get some fully implementable code out of your pseudocode. 

   Be sure to include great comments, just as you would in a real computer program. Keep an eye on strong variable names and PEP-8 compliance, but don't let doing so slow you down too much. You'll have time to clean things up later. 


6. **Test your solution.**

   Pretend to pass a simple input through your code. What values do your variables take at each step, and can you logically see them through to the desired result? If you are forecasting an issue in the code, jump back to another step in the process. 


7. **Optimize your baseline solution.**

   A "literal" translation of pseudocode, which you created in step five, is likely to be redundant and inefficient. Do you see things in the code that could be streamlined? Or perhaps you could make the code more robust with error handling? Maybe you could write a function for a more reusable solution? Rework the code with "being Pythonic" in mind. 


8. **Walk the interviewers through your solution.**

   By this point, you should have consensus with your interviewer on the program, but consider this to be a mini-demo of your code. Now, you can get a big picture look at the code. Consider even stepping away from the whiteboard for a second to refresh your thinking. 


## Whiteboard interview guided example

Next, you'll work through an example of writing a function in Python. The prompt is shown below:

> Write a function that takes a list of numbers and makes a new list of only the first and last elements of the given list. 

You should tackle the problem using the steps above. 

When you're ready to see the solution, you can look at [this Notebook](https://colab.research.google.com/drive/1YuoGTCmwp81uACl_7QjckAUG6-jIz4-P).

1. **Listen.**  Go ahead and restate the problem in your own words: "So, I want to write a function that makes a list of the first and last elements in a list of all numbers." Write the challenge on the board in whatever way that makes the most sense to you.

2. **Determine inputs and outputs.** "Sounds like the input will be a list of any length, and the output will be a list of length two."  Now you can see where the problem starts and ends. It's time to get to the tricky middle part! 

3. **Determine boundaries and assumptions.** Be as thorough as you desire here, asking questions like:  "I think you said this before, but I'm assuming this will be a list of all numbers, right? Can I assume that the input won't be a list of lists? Also, does it matter whether I assign the results of the output to a variable? Do we want the user to input the list, or should it be an existing variable?" You get the idea. 

4. **Pseudocode your solution.** Start by saying something like, "Given the assumptions and requirements of this project, the code should work like this," before launching into your solution, which would resemble the following steps:

   1. Input a list.
   2. Index the first element of the list.
   3. Index the last element of the list.
   4. Create a new list of length two with the results of steps two and three, respectively.
   5. Return the results of step four.

5. **Code your baseline solution.** Here is a first pass at coding the solution in Python. It's a very literal translation of the pseudocode, assigning new variables for both steps two and three, then appending them. There is an easier way to do it, but you can get there incrementally. However, don't wait to implement good coding practices, such as commenting, sensible variable names, and other best practices. The first pass should look something like the code below: 

   ```python
    # Input list
    list = [5, 10, 15, 20, 25]
    
    # Create an empty list to store the results
    new_list=[]
    
    def list_2():
      # Index by first and last element of the list
      first_num = list[0]
      last_num = list[-1]
      # Append each result to the empty list
      new_list.append(first_num),new_list.append(last_num)
      print(list)
      # Return results of list 
      print(new_list)
    
    list_2()
    ```


6. **Test your baseline solution.** Go through how this code will evaluate in Python in your head. It's helpful to imagine running this from your computer. Try breaking the execution down into smaller parts. What results are you left with at the end? "Okay, looks like `first_num` should evaluate to `5`, and `last_num` to `25`. Then the empty `new_list` will append them in that order and become `[5, 25]`. Seems to be working."

7. **Optimize your baseline solution.** The above solution works, but it could be greatly simplified. Go through any loose ends that you see with your interviewer: "Right now, I am assigning the first and last elements of the list to their separate variables, then appending them, but there's really no reason to create all these variables, right? I could simply index each of them as elements of a list of length two and be done with it." The final solution would look something like the code below:

   ```python
    # Call function to take a list
    def list_ends(a_list):
    # Return the first and last elements of that list
        return [a_list[0], a_list[-1]]
      
    list_ends([5, 10, 15, 20, 25])
    ```

   That's much cleaner—nice work! 


## What if my question isn't about coding?

The above workflow has you set to take apart Python coding questions, but what about more general questions about data science? Many of the same principles still apply—keep questions coming, pin down any assumptions, and imagine the input, calculation, and output process involved. 

As mentioned previously, don't hesitate to use the whiteboard for noncoding questions too: draw pictures, list assumptions, and so forth. When relevant, provide real-life examples to illustrate the concepts. Even better, use examples that are relevant to that particular company or industry to demonstrate your aptitude as a candidate. 

## After the interview

Congratulations! You finished your technical interview—or this one, at least! Some workplaces might include several of these interviews during your visit. Ideally, your excitement for data science and the prospect of working at that organization will power you through.

Asking questions is in itself part of the technical interview. Ideally, by the time you start a technical interview, you should have the answer to basic questions like what department the role falls under and what big initiatives the organization is undertaking. 

At the same time, you might be expected to have additional questions for the hiring manager or coworkers. This is your chance to go a little deeper with your questions—now you're speaking with people who you'll actually be working with and evaluated by. 

The following are some questions that you might want to ask:

- What is your story arc? What has happened from the start of your career to the role you're in now?
- What are your team's biggest goals this year, and how will this hire support your ability to meet them?
- What do you see as the most daunting challenge for this new hire?
- How will this new hire be trained in this new position? 
- What is a usual workday here? What are the expectations for taking work home or being available after hours?
- How do you communicate with your team? Do you prefer one-on-ones or staff meetings? Do you communicate primarily with phone, email, or Slack? 
- Where will this new hire be sitting?
- Would outside employment be allowed as long as it doesn't conflict with normal work hours?
- How do you recognize achievements?
- What advice would you give to a new hire trying to succeed on your team?

As always, follow up on your interview with thank-you notes, and remain courteous regardless of your interview's outcome. Again, if you've made it all the way through to a technical interview, you're a serious data scientist job contender! 


## Assignment

Some optional assignments are listed below: 

- Check out [Google's whiteboard interview demonstration video](https://youtu.be/XKu_SEDAykw). Although the interview is conducted in C++ and is more relevant to engineering than data science, you will get relevant tips on whiteboard interviews from real Googlers. 
- Watch this [Kaggle presentation](https://www.youtube.com/watch?v=aXUsrKPTBvY) on breaking down common data science interview questions. This interview is conducted in R, but the focus is on preparing for any data science interview.  

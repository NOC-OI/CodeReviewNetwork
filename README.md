# :mag: NOC code review network

[Code review guidelines](#guidelines) | [Getting started](#gettingstarted) | [Tools for remote code reviews](remote.md) | [Guidelines for reviewers](guidelines_for_reviewers.md) | [Events](#whatshappening) :mega:

Want to get feedback on your code? Could use a second pair of eyes to track down a bug?
Interested in reviewing other researchers' code?

This repository acts as a central place for organising **code reviews at the National Oceanography Centre**.
If you'd like your code to be reviewed by someone else, simply open an issue with a brief description of your code.
If you'd like to volunteer to review some research code, just leave a comment on the corresponding issue to let the author know that you're available to review their code.
If you'd like to participate but are not familiar with GitHub or/and its issue tracking system, see the [getting started section](#gettingstarted).

Code reviews are **short** and **informal** meetings in which a researcher or student (referred to as the *code author*, or *reviewee*) discuss their code with one or several other researchers or students (referred to as *reviewers*). 
Code reviews typically last an hour and focus on a very specific part of a project, whether it's a short script or a couple of functions/subroutines.
Particularly, code reviews are not meant as a formal quality control for an entire project, but rather as an excuse for both rewiewees and reviewers to have a conversation over a short piece of code.
It is an opportunity for both to exchange about their respective software practice and learn from one another.

You can find more information about code reviews by reading the [Code review guidelines](#guidelines) section.

Engaging in regular code reviews, both as reviewer and reviewee, can have a **tremendous impact on the quality of your research software**: it will be more readable, maintainable and extendable, both by yourself and your colleagues.
This means a more efficient, more reproducible and easier to disseminate research. To learn more about the benefit of code reviews for research software, see [Why code reviews?](#whatarecodereviews).

If you don't feel confident in your ability to review code, you might be surprised!
See the [guidelines for reviewers](guidelines_for_reviewers.md).

The NOC Code Review Network is supported by the Research Software Engineering Team in the Ocean Informatics Group.
Everyone is welcome to contribute to this repository, see [the contributing guidelines](CONTRIBUTING.md).

## Community

The Research Software Engineering Team aims at building an active and welcoming community through regular events. 
NOC members please see our [intranet page](https://nocacuk.sharepoint.com/sites/DigitalOcean/SitePages/Research-Software-Engineering.aspx) for more details. 

## <a name="guidelines"></a> Code review guidelines

**See [remote code reviews](remote.md) for advice about carrying out remote code reviews.**

### Typical code review scenario

*Both Priya and Sam are fictitious individuals. Any resemblance to real and actual names is purely coincidental.*

Priya is a researcher in the Marine Physics and Ocean Climate group, and she's currently writing a small python library to process her experimental data.
She would like to get in touch with other python programmers in NOC to have someone else look at her code, potentially highlighting unexpected issues and providing some feedback on her coding style.
Priya selects a small portion of her library (about 300 lines) that she thinks is representative.
She opens [an issue](https://github.com/OxfordCodeReviewNet/forum/issues/3#issue-636951537) on this repository.

Sam is a scientist in Ocean BioGeosciences. They primarily use R for their data analysis, but they have been learning python recently.
They find Priya's issue on this repo, and decide it's a good opportunity to have a close look a some real life python... as well as helping out a colleague!
Sam leaves [a comment](https://github.com/OxfordCodeReviewNet/forum/issues/3#issuecomment-642595092) on Priya's issue, and they both decide to meet on MS Teams next week.

Priya has a look at the [guidelines for remote code reviews](remote.md) and decides to use [tmate](https://tmate.io/) to live share her Vim session with Sam.
Both meet on MS Teams as planned, and Priya briefly describes the context of her research to Sam.
Priya walks Sam through the code snippet she selected, explaining her design choices, highlighting the parts that she's proud of, and the parts that she thinks could be improved.
Sam asks Priya as many questions as they want until they feel they have a good understanding of the code.

Sam has read the [guidelines for reviewers](guidelines_for_reviewers.md), and notices a few things:

- One of Priya's function takes a duration as an argument. Sam flags that the function would break if a user passed a negative number. Priya should perhaps make sure that a proper `ValueError` exception is raised if a user calls the function with a negative duration.
- Next, Sam notices that Priya's code is split into four very long functions. They advise Priya to break these down into smaller functions with descriptive names. This will make her code easier to read, reduce the amount of code that's duplicated, and facilitate future extension of her data analysis pipeline.
- Sam recently read about python's list comprehension syntax, and shares the tip with Priya, who's using a lot of `append()` to build lists.

At the same time, Sam notices that Priya is using something called a "python virtual environment" to develop her library, and they wonder what that is. Priya showcases [python venvs](https://realpython.com/python-virtual-environments-a-primer/) to Sam and explain why they're best practice for python developers.

### Format of code reviews

The code review can be carried out face to face with the developer and reviewer sitting together or it can be done remotely. 
See how to [do code reviews remotely](remote.md) for more details on remote code reviews.

Typically, a code review starts with the author of the code walking the reviewer trough the code, explaining the details of the implementation.
The reviewer(s) ask as many questions as they want until they feel they have a good understanding of the code.
Questions, comments and suggestions will naturally arise.

### Location

The location of the code review and whether it is online or in person is left to the author and reviewer to decide upon. It could be inyour lab/office, a meeting room, a local café or a Teams/Zoom meeting. Please have a look at the [list of options for remote code reviews](remote.md) for more on ways to run remote code reviews.

### Duration and scope of the review

- If you're submitting some code to review, it is best practice to keep it  **below 400 lines**.
  If the submitted piece of code is part of a larger project, it should ideally be representative of your general coding practices on that project.

- Code reviewing can be a tiring exercise! We recommend to keep the sessions short (one hour maximum), but you are welcome to meet more than once.

## <a name="whatarecodereviews"></a> Why code reviews

A code review is simply the action of having a deep and critical look at someone else's code.
This is common practice in the private sector, and more generally in the open source software development community, but still very rarely happen in academia.
Typically, the author of the code sits down with one or more colleagues and walks them through their code, explaining design choices and implementation details.
The role of reviewers is to try to identify potential issues, but also highlight and encourage the use of good practices.

### Software never comes out perfect

A common saying in the software world is that the average number of bugs introduced per 1000 lines of code is around 15.
Although such a metric probably isn't reliable, it illustrates the fact that software almost never comes out perfect, and that fixing bugs and issues is part of the software development process.
This is true in industry, and this is true in academia.

### A fresh pair of eyes

By allowing your code to be seen by a fresh pair of eyes, you will find potential flaws that you would not have spotted on your own.
Having someone external to the project is also a great way of fixing bugs or understanding errors, as it forces the author to explain the problem to someone who is unfamiliar with the code.
Furthermore, several people can often come up with different solutions to a given problem, and may have complementary knowledge of the same programming language

### A win-win practice

As a reviewer, you also have a lot to gain from this process, as it is likely that you will come across programming concepts and practices that are completely new to you.
Whether you are a seasoned programmer or a beginner, reviewing code is a great way of developing, sharpening and widening your programming skills.

## <a name="gettingstarted"></a> Getting started

Make sure you're logged into your GitHub account. If you don't have a GitHub account, you can [create one](https://github.com/join?source=login) for free.

### Propose a code review

1. If you want to propose a code review, you must first _open an issue_.
At the top of this page, under "**NOC-OI**/**CodeReviewNetwork**", click on _Issues_.
2. You can then create a new issue by clicking the green button _New issue_ on the top right of the screen.
The issue comes pre-filled with some place-holder content, feel free to replace it by a description that corresponds to your code.

> The term _issue_ comes from the word _issue tracker_ (the functionality that you are about to use), used by software developers to report and discuss bugs and problems. However, the issue tracker can be used for anything, such as proposing you code review.

### Find code to review

To see current review opportunities, simply browse the issues by clicking on the _Issues_ tab (see previous section).
If you're interested in reviewing a particular piece of code, simply click on the corresponding issue and write a comment.

## Inspiration

This code review network was inspired by the [Oxford Code Review network](https://github.com/OxfordCodeReviewNet/forum).


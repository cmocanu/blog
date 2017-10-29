---
title: Learning programming sucks
date: '2012-04-25'
slug: learning_programming_sucks
---


Current state of learning programming
------------
There has been a rising interest in learning to program all over the world, now that demand for programmers is at an all time high, salaries are rising, and lately it's been getting pretty crazy, with hundreds of available websites, courses, bootcamps, moocs, meetups promising to make you a "coder" in a few months and get you a very high-paying job. It's gotten so far that even presidents and sports superstars encourage people to learn to code. Still, it appears that their efforts are not going very well, some bootcamps have actually been closed and the large majority of people who start learning how to code quit quite early in the process.

I think we are going about this in the wrong way, and there are many bad things we tell beginners.

Skill vs knowledge
------------
I dislike the word coding. Because of very messed up incentives and an overfocus on jobs, coding is being framed as a body of **knowledge** that needs to be taught, that is composed of languages and technologies. This is caused by a number of reasons, among which are the way a lot of companies hire (looking for Java programmer with Spring with 4 years experience) and the unfortunate use of the word language, that makes it sound to a beginner that knowing Python and C is like knowing German and French, which is clearly wrong. 

In truth, programming is a **skill**, separate of any language or technology, and those are only incidental to learning the skill of prgramming. That's why a master C programmer can pick up Python in a matter of weeks and write better code than a beginner who took 20 Python courses. Because the fundamental skill of programming is about designing and implementing systems in a clean and logical fashion using the same building blocks: variables and functions. Yes, there are other things that we use, there are objects, classes, modules, transpilers, annotations, but they are not essential to programming, just nice to haves.

Leading beginners down the wrong path
------------
Learning to program should be an (almost) zero-decision experience for the complete beginner. They should not make any decisions, since they are completely unprepared for that (hence the word complete beginner), and should only be lead on a beaten path, a clear set of steps to follow to gain a basic proficiency in programming. If we teach a kid  mathematics, we start with basic arithmetic and geometry, if we teach music we teach scales first, but how do we teach programming?

Here's a common scenario: a guy wants to learn how to program and goes to reddit, HN or a forum to ask how to begin learning. He gets asked whether he's passionate about it (how could he even know?), whether he wants to do front-end, back-end or if he's more of a mobile guy. Others tell him to start with HTML and then move on to Javascript, which is like telling someone who wants to program video games to start with drawing the characters. But it's fine in this case, because it's still code, right? (hint: answer is no)

After that comes the eternal conundrum, do I learn Java, Javascript, Python, Ruby, Rails, Django, Android, Angular, React, should I get a mac, what editor should I use and all sorts of flame wars start that are **completely irrelevant to learning how to program** and only relevant to professional programmers.

Short rant on passion
------------
I really really hate the word passion, not because of the word itself, but because of the people who use it. Oh, we only want **passionate** people here. If you wanna be a great programmer you have to be **passionate**, it's only **passionate** people that make it, without **passion** you'll get discouraged and stop. 

Passion is bullshit. There are people who are passionate about music and completely suck at it (American Idol anyone?), and there are people who hate accounting but are **fucking amazing** at it. Passion is only useful as it somewhat correlates to the real deal-maker, the secret sauce: **effort**. Whether it's passion that keeps you going or wanting to provide for your family or wanting to make a lot of money to buy a private jet is irelevant as long as you put in the **effort**.

Of course learning is a very complex process and effort isn't directly propotional with skill, but until you show me a master programmer that only studied for 100 hours but is **passionate**, or someone who wrote 100,000 lines of code but is still a complete novice because of his lack of passion, I call bullshit on passion.


More bullshit people say
------------
After spending a few hours on learning the basics of programming and dozens of hours reading debates on whether Sublime Text is a real editor or whether it's ok to teach Python 2.6 to beginners (yes, it's fucking ok), the beginner is now (correctly) advised to build a more significant project, where he faces what I think are the **two most important things that stop people from becoming programmers** (no, you're not a programmer just because Codecademy said you were after you wrote your name inside quotes), or rather, moving up from beginner to intermediate:

- choosing what to build

- setting up the environment

What to build
------------
Choosing what to build is extremely important, since it then makes you actually program, which gives you experience. **Experience** is the mother of all teachers, it's the only way you'll ever learn a **skill** (as opposed to a fact), be it tennis, drawing, juggling or playing the guitar, no practice = no skill.

This is also an issue for competent programmers (at least for me, it is) who want to learn a new language or technology. They start off with a few tutorials, but then get stuck when having to build something a little more involved, either because they get into a state of analysis paralysis and end up doing nothing, or pick a project that is too simple, or, sometimes, too challenging. For me, this was especially hard when learning things that were less related to things I was familiar with (i.e. I was much closer to the skill lever of a complete beginner).

We should replace, or at least supplement, introductory tutorials with introductory projects that gently introduce the learner to new concepts, at the same time providing guidance and hands on experience. The focus should be on **doing**, not reading. Reading makes people **feel** like they understand, whereas doing provides much better feedback. I really liked the book Structure and Interpretation of Computer Programs because of its focus on exercises, we need more resources like that. I also really like the concept of xv6 (an OS made for teaching how an OS works) with associated programming challenges and the Eudyptula Challenge, which is supposed to take you from kernel noob to pushing code into Linux.

For more mainstream technologies, there are a huge number of resources that teach you the basics of writing very small programs (under 100 lines), such as Edabit, 4clojure, exercism, Leetcode, HackerRank, CodeKata, but very few that make you write code that actually resembles what most people working as programmers do. It is not clear how a programmer is supposed to go from beginner to intermediate in, say, Scala, React or Erlang. Yes, there are books, and they do help, but you can't be a competent Scala programmer without having written at least 10,000 lines of Scala code, and the onus shouldn't be on the learner to decide what to write.

The environment
------------
When learning something new, setting up the environment is the #1 most frustrating thing I have to do, by a very, very large margin. Usually I have a tolerance limit of about an hour for non-work related programming setup tasks. It's the reason why I wouldn't even think of touching things like Hadoop or Kafka in my free time, why I abandoned learning Ocaml (spent 2 days to fail to install the packages suggested by Jane Street into emacs, said fuck it and gave up). This is a significant but solvable problem for experienced programmers, who know that fiddling with IDE's, configs, homebrew, apt-get, PATH, environment variables, ports, packages, libraries and all that sort of bullshit is just a thing you have to do, kind of like a rite of passage. Obviously you get very good at this after a while, especially if you only work with 2-3 technologies, and you don't think it's such a big issue anymore. **It is**.

[Here's](https://en.sfml-dev.org/forums/index.php?topic=5065.msg33120#msg33120) me 7 years ago, in 10th grade, trying to make an animation of a backtracking algorithm I was learning at school. What did I get? Fuck you, if you want to write 100 lines of C++ code that calls a graphics library, you need to learn about static linking, dynamic linking, cmake, gcc, PATH etc., which are a pain to use on Windows even for experienced people. By some miracle, and a lot of wasted time, I managed to get SFML working, and I did manage to get a few projects done, the largest ones being a Tetris game and a Game of Life simulation. But it's not ok, and many others would have given up because of the frustration or lack of time.

We shouldn't make beginners deal with this sort of issues this early on, and we shouldn't tie learning something about programming with dealing with all sorts of environment setup bullshit. Yes, it's useful, yes, there are reasons why. it's there, but for learning projects 99% of configuration options don't make any difference whatsoever.


What learning should look like
------------
Say I wanted to learn Scala (I actually did do this about a year ago). I want to go to the "learn Scala page", download a list of exercises unde the form of a starting project or a codebase that needs improvement, with a list of tests failing. I start looking at the code and fix the tests one by one. Obviously, it would need to start very gently, with one-line fixes, there would be hints in the code and some tests would have links to some tutorials or explanations of the prerequisite concepts. But the point is that the feeling of achievement, the actual goal, the entire point of the course should be **doing the exercises**, not watching some boring lecture or reading for hours before you even touch code.

What is extremely important here is that the environment is one-click (or command) and comes (somehow) with a working reasonable dev environment. For compiling the code and running the tests a docker container should work quite well for most cases, and something like Sublime Text or VSC would probably do for most languages. For others (like Java, Scala), more involved environment are required and I'm not sure how that problem could be easily fixed. An online IDE would work well in this case, but that has other issues. Still, this would be a marked improvement over what I did have to do (set up IntelliJ with the Scala plugin, versions not matching, config files not working for the Scala Coursera mooc and a whole other list of issues).

I am not dissing books or lectures or tutorials, some of them are extremely useful and contain vital information. What I am suggesting is that learning programming should be a **code first** experience, with other materials being used as auxiliary information, whereas most programming learning right now is **lecture first**, with the lecture being mostly text or video.

You can find <a href={{< ref "url_shortener.md" >}}> here </a> an example of how I think a better type of tutorial should look like.
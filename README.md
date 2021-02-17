# C-Resources

#Purpose
To help me prepare for the CS 6200 class at Georgia Tech. Responses from Chat.

#Programming Guides

##Beej's Guides
Beef's Guide: It’s an excellent starting point for understanding both of the warmups. In fact, the introduction sounds like he’s speaking directly to you :)
“Hey! Socket programming got you down? Is this stuff just a little too difficult to figure out from the man pages? You want to do cool Internet programming, but you don’t have time to wade through a gob of structs trying to figure out if you have to call bind() before you connect(), etc., etc.” (page 4).
https://beej.us/guide/bgnet/pdf/bgnet_usl_c_1.pdf -Kyle N.

------

+1 on the Beej guide. I was also having a lot of trouble in the beginning, and I feel like this guide was almost like a compass heading. The project was still difficult, and involved a lot of debugging, but after referencing this guide I went from feeling lost, to feeling like I have a general sense of what to do.Also if you can carve out a couple continuous hours, I also think its helpful to actually read through the Beej guide like a book, and later come back and reference the code during your implementation. I initially tried to just "Ctrl F" whatever I needed on the fly, but after reading through the guide continuously for a couple hours, I had a much better general feel for what was going on. -Chris J.

##General Advice
As a CS self-learner myself, I would recommend taking **programming, data structure and algorithm class**(not necessarily in OMSCS) to ramp up basic CS knowledge. Best of luck to your endeavors -Yueqiu S

------

For your immediate problem: I'd like to second the suggestion of **Beej's network guide and the other resources in the project readme**. Make sure you read them if you haven't. He also has a **C programming guide**, which should help, though I haven't read it. When you go through the network guide, make sure you actually understand what all the code is doing. Read it carefully and ask questions if you get stuck. 

Some specific knowledge that will be crucial for surviving this project: **how memory management works in C (particularly use of malloc() and free()), pointers/references vs. values, strings vs. arrays (Google "null terminator" if you're not clear)**. Looks like most of these are covered in Beej's C guide. 

For more general CS knowledge: **CS50 (famous, easy to Google) from Harvard** has great lectures which cover a lot of the basics, and the first half of the programming exercises are all C-oriented (or were, a couple years ago when I did it). You can do the certificate version pretty cheaply; it just won't have college credit. This is probably a couple dozen hours of work, so it may not be viable for surviving the course. Watching the lectures probably will be, though. If you don't understand basic data structures like linked lists and arrays, this is probably a good place to look for more information. 

I really like the iOS app **"Algorithms: Explained and Animated"** by Moriteru Ishida. Really clear, simple animations showing the basic steps of most standard algorithms. Extremely useful for building an intuition about what they're doing. 

If you don't know anything about **data structures and algorithms, this Coursera specialization** might help.
https://www.coursera.org/specializations/data-structures-algorithms
I've done the first course, Algorithmic Toolbox, and thought it was decent. Plenty of challenging little programming exercises involved, too, and they accept a variety of different languages, including at least Java, C++, and Python. (Can't remember if they also do C.) If you want a quicker overview, the book **Grokking Algorithms by Bhargava** is super readable and has simple Python implementations. 

**Teach Yourself CS** https://teachyourselfcs.com/ could be useful as a rough long-term blueprint. A number of the materials they recommend come up over and over and over. 

Anyway, I don't know your situation but I've worked through several of these resources, took 8 community college CS classes before starting here, and I found project 1 doable but very challenging. So don't feel bad but recognize it may take awhile to get your feet under you. -Joseph M

------

In order to get more familiar with network programming I'd suggest getting yourself set up with a good development environment and going over Chapter 5 (System Calls or Bust) of the Beej resource previously linked by Kyle above https://beej.us/guide/bgnet/pdf/bgnet_usl_c_1.pdf.

1. Get yourself set up with a good development environment

For this project the first thing I did was set up the vagrant VM with a GUI. I chose Ubuntu Mate - it's fairly lightweight and intuitive. In the terminal do the following:

$ sudo apt install ubuntu-mate-core
$ sudo service display-manager start

If you've got enough memory resources on your host, it's worth increasing the memory available on the VM via the Vagrantfile. Modify the vb.memory field:

vb.memory = "4096"

This will make the VM more responsive.

I then installed CLion IDE. See https://www.jetbrains.com/clion/. You can get a student licence using your GA Tech email address. This is a development environment with a GUI, and has various debugging and code-completion features that assist with coding. Other IDEs are available, and if you're more familiar with something else then you're probably better off sticking with that.

There's some info on how to get CLion set up with Makefiles here: https://blog.jetbrains.com/clion/2020/06/makefile-projects-in-clion/.

2. Debug step through some network programming samples.

Pick some sample network code and build it using CLion (or other IDE of your choice). Being able to single-step through code and inspect the variables at runtime is incredibly valuable for understanding how things work. There are plenty of examples of networking code linked in the project readme and in Beej so pick whichever you like.

One thing that makes networking code a bit more complicated to debug for this project is that you often need a client and a server both running at the same time, so it can be tricky to get started. If you're stuck on this, you could run a simple listener to simulate a basic server. You could do this with netcat (nc), for example.

nc -nlvp 30605

This would simulate the server side and prints whatever the client sends it to the terminal. Netcat then takes stdin and will send that back to the client. This at least means you can test and debug your client first before you have a working version of the server.

In fairness, if you're not familiar with CLion it might be a bit late to do all this for this project, but it could still help for future projects (and coding in general). I'd say that it's time well invested, as being able to debug with a GUI can be much more illuminating than using a command-line debugger like gdb (CLion also allows you to drop down into gdb when you need to anyway).

Good luck, and I hope this helps someone!
-Robert P

------

I don't have a formal CS background, but I read the prerequisites for this class and prepared as much as I could ahead of time. I found as many examples of C programs on the internet that I could and typed them myself, compiling and running to understand how things worked. In particular, I knew working with strings, structs, and pointers would be areas I needed to try to work on ahead of time. Some useful tips were on omscentral.com. 

I also took a class that edged me toward C last semester, Software Analysis [and Testing], and I would recommend before taking that class before this class. SAT used C++ extensively, so it was a more gentle introduction to the use of pointers and memory management than C, in my opinion. Successfully working with C++ in that class gave me more confidence moving into this class. 

I definitely would not jump into this class without having prepped myself (unless I had a decent amount of experience programming with C). Experience with Python or Java just doesn't cut it, again, in my opinion. You need to learn the differences in C and how to work with them. 

Good luck and I hope you can make your way!

Also, by the way, I was stuck on part 1 for almost 2 weeks after starting right away. I thought for a while that I'd have to drop this class. My problem wasn't C, it was understanding what I was supposed to do. Once I got an understanding of the big picture of this project, I did the other parts in 4 days. 

Another very good preparatory site I almost forgot to mention is Operating Systems: 3 Easy Pieces. Not only are there some pretty well-written readings on OS topics, but there are also problems, projects, and lectures available. I found that invaluable. 

Beej's guide, in my opinion, is okay, but I found more valuable information from piecing things together using Google as I went along. Your results may, of course, differ. 
-Tom F

------

##Communities
Slack and Discord servers! There’s always a few of us in there just chatting or helping each other get unstuck. If you need any help with basic programming knowledge gaps, that’s the place to go.

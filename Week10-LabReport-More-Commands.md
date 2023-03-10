# Week 10 Lab Report: CSE 15L

**In this report, I will explain and provide examples of different command line arguments to use with the commands `find` and `grep`.**

## General Overview of `find` and `grep`
The `find` command, as the name suggests, is mainly used to find certain files and directories quickly. The `grep` command, which stands for 
“global regular expression print,” is used mainly to search for certain words or phrases in text files. Both these commands are helpful in terms of 
speeding up tasks. Like my Week 5 lab report, I used the data from the github repository found on [this](https://github.com/ucsd-cse15l-w23/skill-demo1-data) link. 
The sources I used to find uses of the `find` and `grep` commands were the following websites: [GeeksforGeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/), 
and [phoenizNAP](https://phoenixnap.com/kb/grep-command-linux-unix-examples#:~:text=To%20search%20multiple%20files%20with,separated%20with%20a%20space%20character.&text=The%20terminal%20prints%20the%20name,as%20many%20filenames%20as%20needed.).

---

## Using `find`

First, I tried to find a text file using find that was nested in the written_2 directory. First, I changed my directory to get into the written_2 by typing 
`cd Desktop/CSE15L/skill-demo1-data/written_2`, since that is where the written_2 directory is on my computer. Note that I have cloned the skill-demo1-data
from github previously. Then, I typed `find ./written_2 -name IntroItaly.txt`. By using the `-name` command, I was able to put the file name next to it and signal to my computer that the name of the file I wanted to find was IntroItaly.txt. As seen by the screenshot below, the `find` command printed out the full path to IntroItaly.txt. 

![Image](find1.1.png)

---

Next, I wanted to see how I could use `find` to print out multiple different paths, given a pattern. In this case, I wanted to find all text files in the written_2 directory. I typed `find ./written_2 *.txt`, and as seen by the screenshot below, it printed out all the paths that lead to a text file. 

![Image](find1.2.png)

---

Lastly, I wanted to expand the utility of the `find` command into a more concrete action: deleting a file. I had to type the full path to the file I wanted to delete, with some other commands. Specifically, I typed `find ./travel_guides/berlitz1/IntroDublin.txt -exec rm -i {} \;`. My terminal asked me to confirm if I wanted to delete, and I had to type yes for it to actually delete the file. In the screenshot, it shows this whole process, and I went into the berlitz1 directory to make sure that the file had actually been deleted.

![Image](find2.0.png)

---

## Using `grep`

I played around with the `grep` command in the berlitz1 directory. I used grep in four different ways using the word ocean. 

First, I just typed `grep ocean *`, and as seen by the screenshot, it printed out all instances of ocean in the directory. 

![Image](grep1.1.png)

Then, since I noticed that the HandRHawaii.txt file had a lot of instances of ocean, I typed `grep ocean HandRHawaii.txt`. As seen by the screenshot below, it printed out a paragraph chunk with all the sentences that have ocean in it. 

![Image](grep1.2.png)

After this, I wanted to see if I could count the instances of ocean in all of these files. So, I typed `grep -c ocean *`, and as seen by the screenshot below, it had a word count of all the times ocean appears in those files. 

![Image](grep1.3.png)

Lastly, I wanted more context surrounding each use of ocean. I typed the command `grep -A 3 ocean *`, and this time, it printed out three lines after (since I did -A) the occurence of ocean. This way, I was able to get more context on how the word ocean was used in the text.  

![Image](grep1.4.png)

---

Both `find` and `grep` (and `less`, which I discussed in my Week 5 lab report) are very useful commands. The uses above are nowhere near exhaustive, and 
I will continue trying to find different uses of these commands to help me in my future classes and projects.

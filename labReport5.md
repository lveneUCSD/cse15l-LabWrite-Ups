# CSE 15L, Lab Report 5: Researching Commands (Part 2)
## Lucas Venetoulias 
## Mar. 13th, 2023


<ins>Part 1: Researching Terminal Commands</ins>
<br> In Lab Report 3, I researched certain options that were useful for the ```find``` command in the terminal. In this lab, I will be doing something similar with the ```grep``` command. The first command-line option helps the user find the first ```NUM``` occurrences of a particular ```"pattern"```. To do this, we use the option ```-m NUM "pattern"```, where ```NUM``` references the number of occurrences found before which ```bash``` will stop running and ```"pattern"``` references the pattern to be looked for. Consider the terminal input
```
grep -m 2 "Persian Wars"  travel_guides/berlitz2/Athens-History.txt
```
and its produced output
```
The Persian Wars
At the end of the fifth century b.c., Greece entered the period of the Persian Wars, as recorded in Herodotus’ great narrative 
history of the ancient world (see page 33).
```
As we can see, the option in ```bash``` gave us the first two instances of the phrase "Persian Wars" before stoppping. We try the same option with a slightly different, more-common pattern:
```
grep -m 6 "century"  travel_guides/berlitz2/Athens-History.txt
```
and its produced output
<br><p align="center">
    <img width="850" alt="image" src="https://user-images.githubusercontent.com/122565720/224630703-215725ad-edc8-40fa-b650-4117f87948c0.png">
    </p>
There are more instances of the word "century" than there is of the phrase "Persian Wars", and ```bash``` stopped searching after it found the first six instances of the work. This command would be useful for those who might be unsure about a particular key phrase or definition in a long paper or file, and would like to see the first few times it comes up as a reference for the rest of the paper or file. (In this example, the output is too long and too involved for it to be efficient and sensible for me to write it out entirely.) I found this command-line option at [this webpage](https://linuxcommand.org/lc3_man_pages/grep1.html).

<br> Another terminal input would allow the user to find all instances of a particular ```"pattern"``` without worrying about lower- or upper-case sensitive letters. Using the option ```-i```, consider the following terminal input
```
grep -i "biology" non-fiction/OUP/Kauffman/ch1.txt
```
and its produced output
<br><p align="center">
    <img width="900" alt="image" src="https://user-images.githubusercontent.com/122565720/224622122-0cfb2286-81c1-407d-9bc7-c8353c0efab9.png">
    </p>
<br> (I had to cut the output short in the screenshot; the entier output would have simply been too long to include in this lab report.) The case-insensitivity, shall we call it that, is evident given that line 1 of the output reads "Prolegomenon to a General *Biology*" and then the next line reads "[L]ecturing in Dublin, one of the twentieth century’s most famous physicists set the stage of contemporary *biology* during..." Again, this command is useful for those who need to parse through large files and who are looking for particular words or phrases. A second such example for the option ```-i``` is
```
grep -i "age" travel_guides/berlitz2/Athens-History.txt
```
and one section of its resulting output is
<br><p align="center">
   <img width="850" alt="image" src="https://user-images.githubusercontent.com/122565720/224645713-09a10d4c-97d2-4a18-9276-d31020818e64.png">
    </p>
This terminal command finds all of the instances of "age"; the output included lines such as "The Golden Age" and "This age, in fact, ...", demonstrating that string was found on a non-case sensitive basis. (In both this example and the previous one, the outputs were too long and too involved for it to be efficient and sensible for me to write out the entire output. I specifically picked examples where the output was longer so that I could more easily show a wider range of results that might appear with the ```-i``` option.) The resource I used to find this option was [this webpage](https://www.geeksforgeeks.org/grep-command-in-unixlinux/).

<br> Another terminal command would allow us to search for and print certain lines from a file. To do this, we use a special set of options that are of the form ```-A/B/C[num] "pattern"```, where the option ```-A[num]``` tells ```bash``` to print out the ```num``` number of lines *after* the particular ```"pattern"``` is found in a given file, ```-B[num]``` tells bash to print ouf the ```num``` number of lines *before* the particular ```"pattern"``` is found, and ```-C[num]``` tells bash to print the ```num``` number of lines *before and after* the ```"pattern"``` is found. Consider the following terminal input
```
grep -A2 "my West Side of San Antonio" non-fiction/OUP/Castro/chB.txt
```
and its produced output
```
my West Side of San Antonio
my Quinto of Houston
my Jackson of San Jose
```
A second example with this option might be
``` 
grep -C2 "D’el cielo venimos" non-fiction/OUP/Castro/chO.txt
```
and its produced output is
```
Oremos, Oremos
Angelitos somos
D’el cielo venimos
A pedir Oremos
Si no nos dan,
```
In this example, we found the 2 lines preceeding and following our given pattern "D'el cielo venimos". This option might be relevant for people who want to review the context around a particular line or phrase in a larger file or document. I found information about this option [here](https://linuxcommand.org/lc3_man_pages/grep1.html). 

<br> Another helpful command-line option for the ```grep``` command is ```-n```, which allows users to identify all of the files and line numbers in which a particular ```"pattern"``` appears. For example, we consider the terminal input
```
grep -n "adaptable" non-fiction/OUP/Berk/*
``` 
which looks for the pattern ```"adaptable"``` in all of Berk's chapters. Its resulting output is
```
non-fiction/OUP/Berk/ch1.txt:133:During early childhood, the brain is highly plastic, or adaptable, in that many brain regions are not yet committed to speciﬁc functions. 
This means that if a part of the brain is damaged, other parts can usually take over the tasks that would have been handled by the damaged region, provided they are granted the necessary stimulation. 
In a study of preschool children with a wide variety of brain injuries sustained in the ﬁrst year of life, psychologist Joan Stiles found that cognitive deﬁcits were milder than those observed in brain-injured adults. 
And by age 5, virtually all impairments had disappeared!  As the children gained perceptual, cognitive, and motor experiences, stimulated intact areas of the cerebral cortex compensated for the early damage.59 
By age 8 to 10, most brain regions have taken on speciﬁc functions, so brain plasticity declines.  Because of rapid brain growth and gradual decline in brain plasticity, the ﬁrst 5 to 8 years of life are regarded 
as a sensitive phase of development in which appropriate stimulation is necessary for children to reach their full genetic potential.
```
which includes the file name, the line number, and the actual line itself (the line in which the pattern ```"adaptable"``` appears). (As was the case in the first example in the lab report, I have somewhat reformatted the output to make it easier to read and to follow on the webpage on which it will appear.) Now consider the following other example:
```
grep -n "dimensionality" non-fiction/OUP/Kauffman/ch9.txt
```
whose output is
<br><p align="center">
    <img width="850" alt="image" src="https://user-images.githubusercontent.com/122565720/224659209-8428c64a-d780-445b-baca-3c04ca321583.png">
    </p>
Unlike the previous example, here we have specified a file in which we search for the desired ```"pattern"```. Thus, the option ```-n``` simply tells us which line the ```"pattern"``` appears in and what the line actually is. This would certainly be useful because it provides some more detail and context as to where the particular ```"pattern"``` appears in a file or in a collection of files. If we compare the output of ```grep -n "dimensionality" non-fiction/OUP/Kauffman/ch9.txt``` with the output of ```grep "dimensionality" non-fiction/OUP/Kauffman/ch9.txt```, we see that the output of the latter just contains the lines of the file that contain "dimensionality" whereas the output of the former also tells the user where to find that line through line numbers. This would certainly be useful to parse through large files and have a record of where patterns appear in those files; the line numbers are obviously beneficial given that they give the user a marker or context as to where the desired ```"pattern"``` appears. I looked [here](https://linuxcommand.org/lc3_man_pages/grep1.html) for a general description of this option.  


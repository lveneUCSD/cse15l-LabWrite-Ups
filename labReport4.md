# CSE 15L, Lab Report 4: Live but Reproducible Competition
## Lucas Venetoulias 
## Feb. 27th, 2023


<ins>Part 1: Step-by-Step Instructions for Lab Competition</ins>
<br> In this lab report, I will be showcasing the exact commands I used to execute the competition assigned in lab. 

<br> **Step 1 (setup):** We were tasked with deleting any previous forks we had on our ```ieng6``` account. Having previously done the steps and having tried some optimization, I had a directory titled ```lab7``` in my ```ieng6``` account. Because I knew it was the only directory in my home directory on ```ieng6``` that began with the letter "l", I simply typed ```-rm rf l<tab> <enter>``` to remove the directory. Below shows the entire command in the Terminal:
![Step1 command]

<br> **Step 2 (setup):** We were tasked with forking [this repository](https://github.com/ucsd-cse15l-w23/lab7) to our own GitHub accounts. This step was fairly routine given all of the work we hve done with GitHub over the course of the quarter.

<br> **Step 3:** We were tasked with starting the timer. (This is as much as is needed for this step, as we were not responsible for keeping track of time during the competition.)

<br> **Step 4:** We were tasked with logging into ```ieng6```. Having only logged into my ```ieng6``` account once so far (in the previous run-through of the task), the ```ssh``` command I used to log in was too far back in my command history for the arrow keys to be efficient. Instead, what ran was:
![Step4 command - CtrlR search]
To execute this command, I typed ```<Ctrl-R> ssh <enter>```. The use of ```<Ctrl-R>``` allowed me to search through my command history, and I was looking for the ```ssh``` command I last used to log into my account. I had not logged into any other account (other than my own) in this Terminal window, meaning that the ```ssh``` command my search found included the appropriate account to login.

<br> **Step 5:** We were tasked with cloning the forked repository into our ```ieng6``` accounts. What I ran was:
![Step5 command - git clone]
To execute this command, I typed ```git clone <Command-V> <enter>```. I was able to do this because the last thing I did before the competition began was to copy the protected SSH key for my forked repository. This way, typing ```<Command-V>``` allowed me to paste the copied SSH key. Unfortunately, I did not find a way of simplifying having to type ```git clone``` in order to properly execute this command. Almost immediately after having cloned the repository, I typed ```cd l<tab> <enter>``` because the ```lab7``` directory was created in my ```ieng6``` account and, as in **Step 1**, I knew this directory was the only directory in my ```ieng6``` home directory that began with the letter "l". Using ```<tab>``` allowed me to autocomplete the command without having to type out the directory name. The full command was:
![Step5 command - ls]

<br> **Step 6:** We were tasked with running the JUnit tests in the ```lab7``` directory. After some experimentation and some trial-and-error, I produced a one-lined command that allowed me to compile and run the tests in one line. However, using the arrow keys would have been largely ineffective because there were many commands that I ran since the previous call to the compile-and-run line. I solved the problem by inputting:
![Step6 command - CtrlR search]
To execute this command, I typed ```<Ctrl-R> javac <enter>```. The use of ```<Ctrl-R>``` allowed me to search through my command history, and I was looking for the ```javac``` command I used to compile and run the tests. The advantage of running one line to compile and run everything meant that the last command from my command history that utilized ```javac``` was one line and executed both desired tasks. This helped improve my efficiency during the competition.

<br> **Step 7:** We were tasked with modifying the code file to fix the given issue. In my first run through, I was relatively slow in fixing the bug in ```ListExamples.java``` because I was typing ```nano L<tab> j<tab>``` and then manually finding the bug. But after a lot (and I emphasize, *a lot*) of trial and error and some discussions with other members in my group and aisle on techniques to improve efficiency, I ended up running:
![Step7 command - CtrlR search]
Again, to execute this command, I typed ```<Ctrl-R> vim <enter>```. The use of ```<Ctrl-R>``` allowed me to search through my command history, and I was looking for a ```vim``` command I had previously run to edit the file. The ```vim``` command was extremely useful because it looks in the file given (in this case, ```ListExamples.java```), finds the line where the error is, and replaces the faulty code with correct code. Utilizing ```<Ctrl-R> vim``` was important for a couple of reasons: firstly, I did not have to look at the file (I did, obviously, need to look at the file the first time I was permforming this step to properly identify what the error was) and, secondly, I was sure I would not have a typo anywhere. (The ```vim``` command is long and difficult to type, meaning the chance of making a spelling mistake is higher.)

<br> **Step 8:** We were tasked with running the JUnit tests again and showing that they passed. To do this, I ran:
![Step8 command - command]
To execute this command, I typed ```<up><up> <enter>```. Having just run the compile-and-run line, I knew it was two commands up in my command history. In this case, using the arrow keys was more efficient way of accessing the command than using ```<Ctrl-R>```, as I had done in **Step 6**. 

<br> **Step 9:** We were tasked with committing the changes and pushing them to GitHub. To do this, I ran the following (I have included the Terminal output here to show the results as well):
![Step9 command - commandS (all 3)]
To execute the first command, I typed ```git add *```. This command added every modified file to ```git```'s staging area, from where they will be committed and pushed to GitHub. To execute the second command, I typed ```git commit -m "Update L<tab>.j<tab>"```. This was probably the most I typed during the entire competition. I did as such because I wanted to include a relatively descriptive commit message, as this is good practice. Using ```<tab>``` ensured that I did not spell the file I updated incorrectly (having a typo might be costly for anyone else who might have had access to my forked repository and who might have wanted to access or use the code). And to execute the third command, I typed ```git push origin main```. Again, I did not think there was quicker way to run this command and so I resorted to simply typing it out fully. 


some examples of how we can use the ```find``` command in the terminal. The first command-line option helps showcase all the empty files or subdirectories in a particular directory. As an example, we consider the terminal input
```
find .written_2/travel_guides/berlitz1/ -empty
```
and the produced output, which, in this case, happens to be nothing. This is because there are no empty files in the ```berlitz1``` directory. The way the ```find <path> -empty``` command works is it goes through the specified ```<path>``` and looks for any files or directories that are empty, or have no content in them. Then, the empty files or directories are printed in the terminal. Below is a photo of this output:
<br><p align="center">
    <img width="800" alt="image" src="https://user-images.githubusercontent.com/122565720/218635583-70d7c309-bb5e-47fa-a041-89f31277a8b3.png">
    </p>
<br> Another terminal input might be
```
find .written_2/ -empty
```
to find all of the empty files or subdirectories in the ```.written_2/``` directory, which, like the example above, produces no files as the output. (See the output below:)
<br><p align="center">
    <img width="750" alt="image" src="https://user-images.githubusercontent.com/122565720/218635742-0ab2e3ad-081b-4982-aa31-e59a1fbddd50.png">
    </p>
This option is useful because we could clean up large directories by throwing out empty files or directories. Having a simple and quick way of finding all of those empty elements makes it easy to know which elements we might want to remove from a particular path or directory and which we might want to keep. I used the following link for this command-line option: [this webpage](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/).

<br> Another command-line option will help determine what kind of files exist in particular directories. To do this, we use the ```type``` command. Consider the terminal input 
```
find .written_2/travel_guides -type f
```
and the produced output includes all of the files in that particular directory. (Because the output is very long and contains very many files, the output below contains only the first few files that are printed.)
```
./travel_guides/berlitz1/HandRLasVegas.txt
./travel_guides/berlitz1/HistoryJapan.txt
./travel_guides/berlitz1/IntroMalaysia.txt
./travel_guides/berlitz1/HandRIstanbul.txt
./travel_guides/berlitz1/HistoryJamaica.txt
./travel_guides/berlitz1/HandRJamaica.txt
./travel_guides/berlitz1/HandRHongKong.txt
./travel_guides/berlitz1/HistoryEgypt.txt
./travel_guides/berlitz1/IntroEdinburgh.txt 
...
```
A second example is applying the command on the ```written_2``` directory; the input is
```
find .written_2 -type d
```
and the output is 
```
./
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Berk
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Rybczynski
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Castro
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
```
The command ```find <path> -type f``` looks for all of the elements in a specified ```<path>``` and the ```f``` part of the command tells ```bash``` to look for elements that are files. Hence, in the first example, we did not see the subdirectories ```non-fiction``` and ```travel_guides``` appear, as they are directories and not files. In the second example, when we did specify ```d```, ```bash``` looked for all elements that were directories. This option would be useful if we were dealing with large directories and we wanted to identify all of the particular elements that were files, let's say, in order to better understand the larger directory we were searching within. As with ```find <path> -empty```, I used [this webpage](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/) as a source for this command-line option. 

<br> Another interesting and useful command-line option allows the user to see which elements have been in a particular directory for more than a certain period of time. To find these elements, we use the option ```-mtime +/-n```, where ```n``` is a particular number of days. Consider the input
```
find ./non-fiction/OUP/Abernathy -mtime +10
```
and the produced output 
```
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Abernathy/ch2.txt
./non-fiction/OUP/Abernathy/ch3.txt
./non-fiction/OUP/Abernathy/ch1.txt
./non-fiction/OUP/Abernathy/ch7.txt
./non-fiction/OUP/Abernathy/ch6.txt
./non-fiction/OUP/Abernathy/ch8.txt
./non-fiction/OUP/Abernathy/ch9.txt
./non-fiction/OUP/Abernathy/ch15.txt
./non-fiction/OUP/Abernathy/ch14.txt
```
Now consider the input 
```
find ./non-fiction/OUP/Abernathy -mtime -10
```
and the produced output, which happens to be nothing. (Below is a photo that shows this result, alongside the result from the first example, which provides some context for what the option might be doing .)
<p align="center">
    <img width="750" alt="image" src="https://user-images.githubusercontent.com/122565720/218635854-4dcc623f-7d7d-490b-91d7-33014d2bc32a.png">
    </p>

These two, nearly identical examples beg the question of what change the sign makes before the ```n``` term in the option. The command ```find <path> -mtime +n``` looks for all elements in the specified ```<path>``` that *have not* been modified in the last ```n``` days. Then, it would make sense that ```find <path> -mtime -n``` looks for all elements in the specified ```<path>``` that *have* been modified in the last ```n``` days. And, indeed, this is the case. In the two examples above, the number of days happened to be 10, but this was an arbitrary number. This option is particularly useful because it gives the user a timeframe for all of the elements in a particular directory without having to explicitly look at the file structure or specific file/directory information. I used the following link for this command-line option: [this webpage](https://www.redhat.com/sysadmin/linux-find-command).

<br> Another helpful command-line option for the ```find``` command allows the user to see files or directories that are of a particular size using the option ```-size +/-n```, where ```n``` is the particular size. The option ```size``` comes with a couple of suffixes for ```n```: ```c``` refers to bytes, ```k``` refers to kilobytes, ```M``` refers to megabytes, and ```G``` refers to gigabytes. Consider the input
```
find ./non-fiction/OUP/Fletcher -size -1M
```
and the produced output
```
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Fletcher/ch2.txt
./non-fiction/OUP/Fletcher/ch1.txt
./non-fiction/OUP/Fletcher/ch5.txt
./non-fiction/OUP/Fletcher/ch6.txt
./non-fiction/OUP/Fletcher/ch9.txt
./non-fiction/OUP/Fletcher/ch10.txt
```
In this example, ```bash``` is looking for all of the files in the ```Fletcher``` directory that are less than one megabyte in size. It happens to be the case that all of the text files in the particular directory are less than one megabyte. Consider the following input
```
find . -size +80k
```
and the produced output
```
./non-fiction/OUP/Berk/ch2.txt
./non-fiction/OUP/Berk/ch1.txt
./non-fiction/OUP/Berk/CH4.txt
./non-fiction/OUP/Kauffman/ch8.txt
./non-fiction/OUP/Kauffman/ch9.txt
./travel_guides/berlitz1/WhereToLakeDistrict.txt
./travel_guides/berlitz1/WhereToIndia.txt
./travel_guides/berlitz1/WhereToItaly.txt
./travel_guides/berlitz1/WhereToMalaysia.txt
./travel_guides/berlitz1/WhereToJapan.txt
./travel_guides/berlitz1/WhereToEgypt.txt
./travel_guides/berlitz1/WhereToIsrael.txt
./travel_guides/berlitz1/WhereToFrance.txt
./travel_guides/berlitz1/WhereToDublin.txt
./travel_guides/berlitz1/WhatToJamaica.txt
./travel_guides/berlitz1/WhereToIstanbul.txt
./travel_guides/berlitz2/Portugal-WhereToGo.txt
./travel_guides/berlitz2/Canada-WhereToGo.txt
./travel_guides/berlitz2/China-WhereToGo.txt
```
This input told ```bash``` to find all of the files in the ```written_2``` directory that were greater than 80 kilobytes in size. The ```-``` sign before the size in the first example told ```bash``` to look for files that were smaller than the specified size. In the previous example, the ```+``` sign told ```bash``` to look for files that were larger than the specified size. The ```find <path> -size +/-n``` can be useful for cleaning up directories because it gives the user a way of identifying larger, more storage-costly files without knowing many of the structural details of a particular ```<path>``` (and its sub-paths). If the user wants to create some storage space, using this option would allow them to easily find which files happen to be taking up more space in particular directories. I used the following link for this command-line option: [this webpage](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/).

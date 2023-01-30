# CSE 15L, Lab Report 2: Servers and Bugs
## Lucas Venetoulias 
## Jan. 30th, 2023


<ins>Part 1: Developing Servers</ins>
<br> Before continuing with VScode, find your course-specific account (you can find this by going to the Account Lookup form and entering your username and PID). The course-specific account you are provided should be of the form *cs15lwi23abc*, where *abc* are specific letters that only correspond to your account. Once you have identified your course-specific account, open a new Terminal in VScode and enter the command ```ssh cs15lwi23abc@ieng6.ucsd.edu```, where the address before the ‘@’ symbol is your course-specific account (the one you found earlier in this part). When prompted, enter your password (it might be the same as your PID password). Once the password has been entered successfully, something like the following should appear in the terminal:
<br> <img align="center" width = "468" alt="image" src="https://user-images.githubusercontent.com/122565720/212590595-d868d108-6bd1-4461-9b16-0ac66a7c595b.png">


<ins>Part 2: Bugs and More Bugs</ins>
<br> My lab report will include a write-up for the bug in the reverseInPlace() method. The test method 
```
public void testReverseInPlaceFail() {
    int[] input1 = new int{1, 2, 3};
    ArrayList.reverseInPlace(input1);
    assertEquals(new int[] { 3, 2, 1 }, input1);
}
```
includes a failure-inducing input (```input1```), whereas the test method
```
public void testReverseInPlacePass() {
    int[] input2 = new int{3};
    ArrayList.reverseInPlace(input2);
    assertEquals(new int[] { 3 }, input2);
}
```
does *not* include a failure-inducing input. 




<ins>Part 3: Self-Reflection</ins>
<br> I really liked Lab 2 because although I felt I was familiar with servers and how servers worked. In truth, I was not as familiar as I thought. I appreciated walking through a simple web server algorithm because it introduced the different components of the web server (hosts and domains, queries, "search requests," etc.) and how those different components interact with each other. I recognize that the web server we were looking at and modified was a simple web server, yet it was welcoming to learn about the process of constructing a simple web server. 






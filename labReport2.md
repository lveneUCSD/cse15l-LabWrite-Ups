# CSE 15L, Lab Report 2: Servers and Bugs
## Lucas Venetoulias 
## Jan. 30th, 2023


<ins>Part 1: Developing Servers</ins>
<br> Below is a screenshot of my code for the ```StringServer``` server:
<br><p align="center">
    <img width="800" alt="image" src="https://user-images.githubusercontent.com/122565720/215646768-923b384b-465f-4148-b605-e465cfcfd10d.png">
    </p>
<br> I tested my ```StringServer.java``` with a few input messages, shown in progression below:

<p align="center">
    <img width="700" alt="image" src="https://user-images.githubusercontent.com/122565720/215647951-e16d1f7c-72f1-491c-bcca-77ed3a954a36.png">
    </p>
<p align="center">
    <img width="700" alt="image" src="https://user-images.githubusercontent.com/122565720/215647996-525c371f-f3fd-4561-bda8-a002cc86523b.png">
    </p>
<p align="center">
    <img width="700" alt="image" src="https://user-images.githubusercontent.com/122565720/215648010-c0dbb5ca-75e1-4281-bb17-66fd5d49a993.png">
    </p>

What seems interesting to point out is that URLs do not include spaces, and to address this issue, URLs contain the string ```%20``` to indicate spaces. That said, for each of the screenshots above, the ```handleRequest``` method was called. In the first screenshot, because there was no previously searched string, ```stringToBePrinted``` was simply the string queried (in this case, the string ```"grandma"```) and a new line. For the second and third screenshots, the code runs similarly: the ```handleRequest``` method is called, and given that the URL contains ```add-message```, the ```stringToBePrinted``` is modified to also include the newly queried string and a newline. The newly queried string in the second screenshot is ```"cse15L is my first lab course at UCSD"```, whereas the newly queried string in the final screenshot is ```"this will appear in my Lab Report 2 Write-Up"```.  
<br>


<ins>Part 2: Bugs and More Bugs</ins>
<br> My lab report includes a write-up for the bug in the ```reverseInPlace()``` method. The test method 
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
does *not* include a failure-inducing input (```input2```). The code, before any modifications, is:
```
static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length; i++) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
With this code, symptom for the failure-inducing input is
 ![image](https://user-images.githubusercontent.com/122565720/215650752-bdc24107-9534-41ee-8581-e9ea06ee2622.png),
<br> whereas the symptom for the non-failure-inducing input is
<br><img width="702" height="112.5" alt="image" src="https://user-images.githubusercontent.com/122565720/215639077-1398cf71-5b29-49e7-a7b1-93efe0ba9dc5.png">.
<br> Given these symptoms, we can modify the code for the ```reverseInPlace()``` method to become:
```
static void reverseInPlaceModified(int[] arr) {
    int temp;
    for (int i = 0; i < arr.length / 2; i++) {
        temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
}
```
These modifications fix the bugs that the program had because the new code properly "switches" the two elements in the corresponding positions of the array instead of simply creating an array that is symmetric with respect to the middle element. 


<br>
<ins>Part 3: Self-Reflection</ins>
<br> I really liked Lab 2 because although I felt I was familiar with servers and how servers worked, the lab showcased that, in truth, I was not nearly as familiar with servers as I had originally thought. I appreciated walking through a simple web server algorithm because it introduced the different components of the web server (hosts and domains, queries, paths, and more) and how those different components interact with each other. I recognize that the web server we were looking at and modified was a simple web server, yet it was welcoming to learn about the process of constructing a simple web server. 






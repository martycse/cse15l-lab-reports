# Lab Report 5 - Putting it All Together (Week 9)
## Part 1 - Debugging Scenario

### 1. Student:
#### Title: Can't find the bug in my code!
`Hello, I am encountering an issue where while merging two lists I am getting repeated elements like the apple element shown in my screenshot. I believe that it is being caused
by some bug within my merge method that is not correctly comparing the elements. Could it be something to do with how the indices advance or is it something to do with the handling of equal elements?
I would appreciate any help!`

Screenshot Below:

<img width="1252" alt="Screenshot 2024-06-04 at 5 17 38 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/970d3b6c-c586-4fc2-a398-0d7fe1977448">


### 2. TA (me):
`Hello, thanks for posting your issue, I see your concerns and your screenshot. From what I see in your code you have analysed the problem pretty well so far. I also believe the merge method is incorrectly handling
indices or handling equal elements. My suggestion is that you implement some print statements throughout the merge method. More specifically I suggest you add print statements to view values after
adding elements or incrementing indices. You can do this by simply adding the System.out.println() statement with the addition of the proper values within them. I highly recommend to try this and please
feel free to reach back out to me with any results, discoveries, or any more concerns you may have.`


### 3. Student:
`Hey, thank you so much for the reply, I followed your suggestion and I was able to get the following to first see the issue:`
<img width="1482" alt="Screenshot 2024-06-04 at 5 59 26 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/ac5bbf54-66ac-4722-be64-86c5a7a7d985">

##### Description of the bug:
`I realized that I was accidentally adding the wrong indexes within the first while loop. The indexes in lines 24 and 28 should actually be swapped in order to add to the correct index.
After trying this, the issue was resolved. Below I have also provided the fully fixed code with the print statments to also add a little more to my output:`

<img width="1482" alt="Screenshot 2024-06-04 at 6 07 22 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/ea526cd3-ddec-4d1c-b023-ae1b33b1aa9d">

### 4.

#### File and Directory Structure:
(Note: script is an empty folder and I accidentally left it there)

Lab Report 5/

  -ListExamples.class

  -ListExamplesTest.java

   -run_test.sh

  -script
    
#### File contents before fix:
1. ListExamples.class:
   - None
2. ListExamplesTest.java:
<img width="1252" alt="Screenshot 2024-06-04 at 5 17 38 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/d28414d7-8735-4539-94a3-cf050e7693a5">

3. run_test.sh:
<img width="509" alt="Screenshot 2024-06-04 at 6 28 06 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/9b0fb912-d11f-46c4-9c12-15b394cdabe0">

4. script (is empty, accidentally left it there)

#### Command Line Ran:
* `bash run_test.sh`

#### Bug Edit Description:
* Swap lines 24 and 28 to create a proper indices addition

## Part 2 - Reflection
Something that really stood out to me during the second half of the quarter was scripts and writing them. I found it interesting because I feel like they are very important to learn about
as they can cut down time consumption and can be used for cool projects like an autograder. Although I am not familiar just yet with the whole scope of bash scripts, I believe they will be essential and a useful tool for me in the future. Additionally,
something we have done throughout the entire quarter that I learned was how directories and even how an operating system works in a way. Throughout the quarter I began to notice more things when working on my computer and
browsing through files that I remember seeing during class. I thought that it was very interesting to see how a system works through the command line. Through this I also found interesting
that I was able to know little shortcuts now when working on my computer with URLs or even files daily. Overall this class changed my perspective on how coding and computers work and what they can be used for.


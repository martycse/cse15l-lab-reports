# <ins>Lab Report 3 - Bugs and Commands (Week 5)</ins>
## <ins>Part 1 - Bugs</ins>

#### **1 & 2). Below is the `associated code` for both the succesful test and the failed test**

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
**1). A `failure-inducing input` for the buggy program, as a JUnit test.** *(Below is the code for the **FAILED** test)*

<img width="664" alt="Screenshot 2024-05-08 at 3 30 27 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/3be8bf1b-b9d0-4f75-b746-197b9362c36d">

**2). A `pass-inducing input`, as a JUnit test.** *(Below is the code for the **SUCCESFUL** test)*

<img width="467" alt="Screenshot 2024-05-08 at 3 33 03 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/d317317f-ac2b-4a77-9e66-4cb6c814d173">

**3). The `symptom`, as the output of running the two tests above.** *(Below is the output of the failed test along with the success of the succesful test)*

```
r.JUnitCore ArrayTests
JUnit version 4.13.2
.E..
Time: 0.006
There was 1 failure:
1) testReverseInPlace2(ArrayTests)
arrays first differed at element [4]; expected:<3> but was:<5>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReverseInPlace2(ArrayTests.java:16)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<5>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 3,  Failures: 1
```

**4). The bug, as the before-and-after code change required to fix it**

***Before code change:***

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

***After code change:***

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      temp[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1)
      arr[i] = temp[arr.length - i - 1];
  }
```

**5). Brief description why the fix addresses the issue.** 

*"The fix of the code this way addresses and fixes the issue because the original code did not make a new array. This is a problem because it keeps overwriting the original array elements with different elements within it. By fixing the code in this way, creating a new temporary array, it feeds this temp array with the elements of the old array and avoids replacing the original array entirely and allows the array to properly reverse."*

## <ins>Part 2 - Researching Commands: `grep`</ins>

### <ins>Command Line Options for `grep`</ins>

`grep`: searches for patterns within a file
1. `-i` - this command ignores cases therefore it allows the command to find patters and not be case sensitive.
2. `-r` - can search patterns in subdirectories over and over.
3. `-c` - counts how many lines the specified pattern appears in a file.
4. `-l` - prints the filenames provided that contain the pattern provided.

***(Command Line Options descriptions provided by ChatGPT)***

*ChatGPT Prompt: "what are some command line options for grep in bash"*

*ChatGPT Output: "Grep is a powerful command-line tool used for searching text patterns in files or streams. Here are some common options and flags you can use with grep in Bash: Basic Usage:
grep pattern file: Search for a pattern in a file.
grep pattern file1 file2 ...: Search for a pattern in multiple files.
Options for Output Control:
-i: Ignore case distinctions in patterns and data.
-v: Invert the match, i.e., display non-matching lines.
-l: Display only the names of files that contain the match.
-L: Display only the names of files that do not contain the match.
-n: Display line numbers along with matching lines.
-c: Display count of matching lines for each input file.
--color=auto: Highlight matching text in color (if your terminal supports it).
Options for Pattern Matching:
-E or --extended-regexp: Interpret the pattern as an extended regular expression (ERE).
-F or --fixed-strings: Interpret the pattern as a list of fixed strings (no regex).
-w: Match whole words only.
-x: Match whole lines only.
Options for Recursive Search:
-r or -R: Recursively search subdirectories.
-l (lowercase L): List only file names that contain matches (useful with -r).
Miscellaneous Options:
-q or --quiet or --silent: Quiet mode; suppress all output.
-A num or -B num or -C num: Show num lines of context after, before, or around the match."*

### <ins>8 Command Line Examples:</ins>

#### 1. `-i` Examples:

***Ex.1):***

***Command:***
```
marty@Martins-MacBook-Air docsearch % grep -i "SECURITY" technical/911report/chapter-1.txt
```
***Output:***
```
When he checked in for his flight to Boston, Atta was selected by a computerized prescreening
system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers
 who should be subject to special security measures. Under security rules in place at the time, the only
consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was
confirmed that he had boarded the aircraft. This did not hinder Atta's plans.
In another Logan terminal, Shehhi, joined by Fayez Banihammad, Mohand al Shehri, Ahmed al Ghamdi, and Hamza
al Ghamdi, checked in for United Airlines Flight 175, also bound for Los Angeles. A couple of Shehhi's colleagues
were obviously unused to travel; according to the United ticket agent, they had trouble understanding the standard
security questions, and she had to go over them slowly until they gave the routine, reassuring answers..............
```
***Explanation:***

This command is looking for the word "Security" within the chapter-1.txt in 911report file within the technical file. The reason why this is useful
is because it doesn't care about the case sensitivity of the word security. As shown, I used "SECURITY" and still received the word no matter what.

***Ex.2):***

***Command:***
```
marty@Martins-MacBook-Air docsearch % grep -i "faa" technical/911report/chapter-1.txt 
```
***Output:***
```
When the local civil aviation security office of the Federal Aviation Administration (FAA) later investigated these security screening operations,
the screeners recalled nothing out of the ordinary. They could not recall that any of the passengers they screened were CAPPS selectees. We asked a
screening expert to review the videotape of the hand-wanding, and he found the quality of the screener's work to have been "marginal at best." The
screener should have "resolved" what set off the alarm; and in the case of both Moqed and Hazmi, it was clear that he did not.
The four men passed through the security checkpoint, owned by United Airlines and operated under contract by Argenbright Security. Like the checkpoints
in Boston, it lacked closed-circuit television surveillance so there is no documentary evidence to indicate when the hijackers passed through the
checkpoint, what alarms may have been triggered, or what security procedures were administered. The FAA interviewed the screeners later; none recalled
anything unusual or suspicious...........
```
***Explanation:***

Now the command is looking for the word "FAA". The reason this is useful is because the text writes "FAA" in all caps like this and by searching for it as "faa"
it still allows the search to go through. It can be useful in cases where people may want to find a certain word in a test but are unsure of the case or its usage.

#### 2. `-r` Examples:
***Ex.1):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***

***Ex.2):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***

#### 3. `-c` Examples:
***Ex.1):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***

***Ex.2):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***

#### 4. `-l` Examples:
***Ex.1):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***

***Ex.2):***

***Command:***
```

```
***Output:***
```

```
***Explanation:***


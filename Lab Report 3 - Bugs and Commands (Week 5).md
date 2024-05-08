# Lab Report 3 - Bugs and Commands (Week 5)
## Part 1 - Bugs

**1 and 2). Below is the `associated code` for both the succesful test and the failed test**
**(1 & 2).**
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

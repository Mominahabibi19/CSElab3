## **Lab Report 3 - Bugs and Commands**
*By Momina Habibi*
# Part 1 - Bugs
- The failure-inducing input
```
@Test
  public void testReverseInPlace1() {
    int[] input1 = { 1, 2, 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
	}
```
- The input that doesn't induce a failure
  ```
  @Test 
	public void testReverseInPlace2() {
    int[] input1 = { 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5 }, input1);
	}
  ```
- The symptom as the output of running the tests

  This is the screenshot for the failure-inducing input
  ![Image](sym1.png)
  
  This is the screenshot for the input that doesn't induce a failure 
  ![Image](sym3.png)
  
- The code with the bug 

```
 static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

- The code without the bug  

  ```
   static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
       arr[arr.length-i-1] = temp;
    }
  }
  ```
- The fix addresses the issue because


# Part 2 - Researching Commands
I choose grep command (4 alternate ways to use it then for each 4 give 2 examples of using it in on files and directories form ./techhnical
show the each example as code block the command and its output then
write senenteces about what is doing and why its useful. total 8 examples.

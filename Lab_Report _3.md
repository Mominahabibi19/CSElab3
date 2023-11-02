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
	public void testReverseInPlace() {
    int[] input1 = { 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5 }, input1);
	}
  ```
- The symptom ...
  ![Image]
  ![Image]
- the bug as the before and after code change

# Part 2 - Researching Commands
I choose grep command (4 alternate ways to use it then for each 4 give 2 examples of using it in on files and directories form ./techhnical
show the each example as code block the command and its output then
write senenteces about what is doing and why its useful. total 8 examples.

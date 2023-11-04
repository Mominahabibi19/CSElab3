# **Lab Report 3 - Bugs and Commands**
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
- The fix addresses the issue by correctly reversing the elements in the input array through a swapping. first, I changed the parameter in the for loop to i < arr.length/2 then I created a temp variable to save the original value of the element at index `i` then  I swapped the current element at index `i` with the element at the corresponding position from the end of the array then I assign the element from the end of the array with the value stored in the temp variable which contains the original value of the element at index `i`. By doing this approach, the fix ensures that the input array is reversed in place and does correctly for arrays of any length.


# Part 2 - Researching Commands
I chose the command `grep` because it is a very useful command for searching text patterns within files. 

- First alternate way of using the command `grep` with `-iw`
- - Example 1:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -iw war ./technical/911report/chapter-1.txt
    The threat of Soviet bombers diminished significantly as the Cold War ended, and the number of NORAD alert sites was reduced from its Cold War high of 26. Some within the Pentagon argued in the 1990s that the alert sites should be eliminated entirely. In an effort to preserve their mission, members of the air defense community advocated the importance of air sovereignty against emerging "asymmetric threats" to the United States: drug smuggling, "non-state and state-sponsored terrorists," and the proliferation of weapons of mass destruction and ballistic missile technology.
    The President's motorcade departed at 9:35, and arrived at the airport between 9:42 and 9:45. During the ride the President learned about the attack on the Pentagon. He boarded the aircraft, asked the Secret Service about the safety of his family, and called the Vice President. According to notes of the call, at about 9:45 the President told the Vice President:"Sounds like we have a minor war going on here, I heard about the Pentagon. We're at war . . . somebody's going to pay."
    At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war."
(base) mominahabibi@Mominas-MBP docsearch % 
```
- - Example 2:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -iw niaaa ./technical/government/*/*2-PDF.txt
Institute on Alcohol Abuse and Alcoholism (NIAAA) defines at-risk
In addition to these questionnaires, NIAAA suggests that all
recommended using the NIAAA approach in the ED.10
recommended by NIAAA for primary care should be compared with other
sequences. Several trials of variations of the NIAAA approach are
be evaluated by studying the NIAAA approach and several
(base) mominahabibi@Mominas-MBP docsearch % 

```
Using the command `grep` with `-iw ` so the `-i` (ignore case) makes grep case insensitive and `-w` (word-regexp) ensures that grep matches only whole words. It is so useful for the time that we want to find the whole word regardless of whether the characters are in uppercase or lowercase.  

- Second alternate way of using the command `grep` with `[-A num]`
- - Example 1:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -A 3 BACKGROUND ./technical/*/*/*annual.txt 
BACKGROUND
Legal Services Corporation
The Legal Services Corporation is a private, non-profit
corporation established in the District of Columbia by the Legal
(base) mominahabibi@Mominas-MBP docsearch %

```
Example 2:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -A 5 Diversity ./technical/*/*/*annual.txt
Diversity
To better serve clients and strengthen program staff and
leadership sensitivity to client communities, LSC has convened a
series of conferences on diversity. These conferences will enable
program staff to examine the degree to which gender, race,
ethnicity and age have adversely affected the ability of some
(base) mominahabibi@Mominas-MBP docsearch % 
```
When you use the command line `-A num`(after context = num) tells `grep` command to display the lines that match the pattern followed by the specified number of lines after each match, and the num represents the number of lines you want to display after the match. so it is useful because it provides context around the matching lines for example, if I want to look for a word and its description so when I `grep` that word using the command line `-A num` it will show the world followed by a few line of its description.   

- Third alternate way of using the command `grep` with `-H`
- - Example 1:
```
(base) mominahabibi@Mominas-MBP About_LSC % grep -H -i supreme *Opinion.txt *Syllabus.txt
LegalServCorp_v_VelazquezOpinion.txt:SUPREME COURT OF THE UNITED STATES
LegalServCorp_v_VelazquezSyllabus.txt:SUPREME COURT OF THE UNITED STATES
(base) mominahabibi@Mominas-MBP About_LSC % 
```
- - Example 2:
```
(base) mominahabibi@Mominas-MBP About_LSC % grep -H -i organizations *port.txt           
Progress_report.txt:that emphasizes strengthening quality at individual organizations
Progress_report.txt:in other nonprofit organizations that work as partners with our
Progress_report.txt:associations and community organizations. Meetings are also
State_Planning_Report.txt:Organizations are like elephants -- slow to change
State_Planning_Report.txt:organizations, or, in some instances, took their skills and talents
State_Planning_Report.txt:organizations to a deeper involvement in state planning and higher
State_Planning_Report.txt:increase the capacities of three community-based organizations.
State_Planning_Report.txt:twelve LSC organizations. Recommendations that programs improve
State_Planning_Report.txt:serve clients whom LSC-funded organizations could not
State_Planning_Report.txt:community education site for immigrant advocacy organizations.
State_Planning_Report.txt:the state's 33 nonprofit civil legal services organizations, has
State_Planning_Report.txt:legal services organizations, religious communities, the judiciary,
State_Planning_Report.txt:lawyers and cultural organizations to address the need for
State_Planning_Report.txt:The organizations and institutions, which comprise our
State_Planning_Report.txt:to decisions to consolidate the five organizations. In 2001, final
State_Planning_Report.txt:individuals and organizations involved in the support and delivery
State_Planning_Report.txt:organizations that target very specific populations or legal
State_Planning_Report.txt:problems. Others are part of larger organizations that focus on
State_Planning_Report.txt:including other client-centered non-profit organizations, and a
State_Planning_Report.txt:county bars, law schools, public interest legal organizations, and
State_Planning_Report.txt:communitybased organizations, and the organized bar. A consultant
State_Planning_Report.txt:whether maintenance of three separate organizations continues to
State_Planning_Report.txt:organizations adopt new structures and approaches that can cope
State_Planning_Special_Report.txt:LSC understands that organizations can be reluctant to embrace
Strategic_report.txt:organizations - the combined Conference of State Court Judges and
Strategic_report.txt:organizations to obtain distance learning opportunities, allowing
Strategic_report.txt:individuals and organizations with special knowledge or experience
Strategic_report.txt:pro bono and legal services organizations and the support and
Strategic_report.txt:area. Organizations are able to use the site's extensive resources
Strategic_report.txt:host organizations to revise content without a webmaster or
Strategic_report.txt:endeavors with a host of national organizations - NLADA, AARP Legal
Strategic_report.txt:LSC works cooperatively with several national organizations that
Strategic_report.txt:reason poverty organizations have not "more completely answered the
Strategic_report.txt:awards, LRI resources, our partnerships with national organizations
commission_report.txt:unemployment. Farmworker community organizations have found that
commission_report.txt:Organizations
commission_report.txt:funded, non-profit organizations is limited. See March Comments at
commission_report.txt:(testimony of Jack Londen, Attorney at Law). These organizations
commission_report.txt:nonprofit organizations, such as the Mexican American Legal Defense
commission_report.txt:Consequently, these non-profit legal organizations are not a
commission_report.txt:H-2A workers from non-LSC funded nonprofit organizations and
(base) mominahabibi@Mominas-MBP About_LSC % 
```
`-H` command line is used to force `grep` to print the file name along with the output lines. for sure, this is a useful command especially the time that we are searching multiple files with similar content and we just want to quickly identify which file contains the matching lines. Also, when troubleshooting or debugging it will be so useful because it will show which file contains problematice lines making it easier to address the issue. 

- Fourth alternate way of using the command grep with 
Example 1:
```
code
```
Example 2:
```
code
```

https://www.youtube.com/watch?v=N05sWPgj-44

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
- - Example 2:
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
`-H` command line is used to force `grep` to print the file name along with the output lines. Definitely, this is a useful command especially the time that we are searching multiple files with similar content and we just want to quickly identify which file contains the matching lines. Also, when troubleshooting or debugging it will be so useful because it will show which file contains problematice lines making it easier to address the issue. 

- Fourth alternate way of using the command `grep` with `-C` 
Example 1:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -C 7 "The Price of Life" ./technical/*/*12.txt
./technical/plos/journal.pbio.0020012.txt-        another two areas of investigation. Her laboratory reported in December 2002 that
./technical/plos/journal.pbio.0020012.txt-        inhibiting the respiration of mitochondria in developing worms increased longevity, but
./technical/plos/journal.pbio.0020012.txt-        that it had no effect in adult worms, for reasons still unexplained, she says. Further
./technical/plos/journal.pbio.0020012.txt-        microarray analysis is underway to pinpoint whether the cause simply lies downstream of the
./technical/plos/journal.pbio.0020012.txt-        insulin/IGF-1 pathway or whether it is something different altogether.
./technical/plos/journal.pbio.0020012.txt-      
./technical/plos/journal.pbio.0020012.txt-      
./technical/plos/journal.pbio.0020012.txt:        The Price of Life
./technical/plos/journal.pbio.0020012.txt-        Then there's research looking at the effects on lifespan of changes to an organism's
./technical/plos/journal.pbio.0020012.txt-        reproductive system. For Kenyon, such work often involves a battle to convince sceptics
./technical/plos/journal.pbio.0020012.txt-        that longevity is not a trade-off with fertility. Four years ago, her laboratory reported
./technical/plos/journal.pbio.0020012.txt-        that killing germ cells increases the lifespan of worms by 60%, but only because, she
./technical/plos/journal.pbio.0020012.txt-        stresses, it affects endocrine signalling and not because it prevents reproduction. Further
./technical/plos/journal.pbio.0020012.txt-        research, published last year, showed quite clearly, she says, that ageing and reproduction
./technical/plos/journal.pbio.0020012.txt-        are controlled independently of one another. And as for her recent work on infertile worms,

```
Example 2:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -C 5 "The incidence" ./technical/*/*46.txt
./technical/plos/journal.pbio.0020046.txt-        Winston Churchill had to rehearse all his public speeches to perfection and even practiced
./technical/plos/journal.pbio.0020046.txt-        answers to possible questions and criticisms to avoid stuttering. Charles Darwin also
./technical/plos/journal.pbio.0020046.txt-        stuttered; interestingly, his grandfather Erasmus Darwin suffered from the same condition,
./technical/plos/journal.pbio.0020046.txt-        highlighting the fact that stuttering runs in families and is likely to have a genetic
./technical/plos/journal.pbio.0020046.txt-        basis.
./technical/plos/journal.pbio.0020046.txt:        The incidence of PDS is about 5%, and its recovery rate is up to about 80%, resulting in
./technical/plos/journal.pbio.0020046.txt-        a prevalence of PDS in about 1% of the adult population. As recovery is considerably more
./technical/plos/journal.pbio.0020046.txt-        frequent in girls than in boys, the male-to-female ratio increases during childhood and
./technical/plos/journal.pbio.0020046.txt-        adolescence to reach three or four males to every one female in adulthood. It is not clear
./technical/plos/journal.pbio.0020046.txt-        to what extent this recovery is spontaneous or induced by early speech therapy. Also, there
./technical/plos/journal.pbio.0020046.txt-        is no good way of predicting whether an affected child will recover (Yairi and Ambrose
(base) mominahabibi@Mominas-MBP docsearch % 
```
Sometimes you really want to see some additional context that contains before and after the match, so we use `-C num` (context) with `grep` command to specify the number of lines of context to display around the match line. It will be useful for searching some text in the computer program you wrote so if you want to see the sounding code that matches.

I learned all of these commands by watching a YouTube video. I typed in the search box "use of grep with different commands" and then I opened [this video]
(https://www.youtube.com/watch?v=N05sWPgj-44) and took notes. In addition, I learned about grep and the command line that I can use with it by typing `man grep` in my terminal. Then, I applied in the VS Code using the files and directories form `./technical`

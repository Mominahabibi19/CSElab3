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
I chose the command grep because it is a very useful command for searching text patterns within files. 

- First alternate way of using command grep with -iw
Example 1:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -iw war ./technical/911report/chapter-1.txt
    The threat of Soviet bombers diminished significantly as the Cold War ended, and the number of NORAD alert sites was reduced from its Cold War high of 26. Some within the Pentagon argued in the 1990s that the alert sites should be eliminated entirely. In an effort to preserve their mission, members of the air defense community advocated the importance of air sovereignty against emerging "asymmetric threats" to the United States: drug smuggling, "non-state and state-sponsored terrorists," and the proliferation of weapons of mass destruction and ballistic missile technology.
    The President's motorcade departed at 9:35, and arrived at the airport between 9:42 and 9:45. During the ride the President learned about the attack on the Pentagon. He boarded the aircraft, asked the Secret Service about the safety of his family, and called the Vice President. According to notes of the call, at about 9:45 the President told the Vice President:"Sounds like we have a minor war going on here, I heard about the Pentagon. We're at war . . . somebody's going to pay."
    At 10:02 that morning, an assistant to the mission crew commander at NORAD's Northeast Air Defense Sector in Rome, New York, was working with his colleagues on the floor of the command center. In a brief moment of reflection, he was recorded remarking that "This is a new type of war."
(base) mominahabibi@Mominas-MBP docsearch % 
```
Example 2:
```
(base) mominahabibi@Mominas-MBP docsearch % grep -iw Alcohol ./technical/government/*/*2-PDF.txt
Identifying ED Patients with Alcohol Problems
Many patients in the emergency department (ED) have alcohol
further examine and refine alcohol-screening questionnaires in the
Alcohol problems defined
Alcohol problems designate a spectrum from risk behavior to
illness, and from problematic consumption to alcohol use disorder.
screening for several alcohol endpoints. Acute intoxication is of
certainly be considered an "alcohol problem." The blood or breath
alcohol concentration (BAC), coupled with our clinical
observations, may help us identify intoxication. Most alcohol
screening tests identify patients with alcohol use disorders or
problematic consumption of alcohol. The American Psychiatric
(ICD-9, -10) have rigorously defined alcohol abuse and alcohol
cases of alcohol abuse meet the ICD-10 definition. In general, an
alcohol use disorder is present when an aspect of the patient's
by alcohol. Before function is compromised, problematic
toward identifying patients with high alcohol consumption before
Institute on Alcohol Abuse and Alcoholism (NIAAA) defines at-risk
the alcohol use spectrum. However, real tests don't perform
would address both current and lifetime alcohol problems. Current
identifying alcohol use disorders or problematic consumption.7 Of
course, BAC can help identify acute intoxication. The alcohol
diagnosis, but clinical impressions concerning alcohol problems can
patients with alcohol problems. Unfortunately, the majority of
reported that in a trauma center ED, staff suspected alcohol-ism in
a sensitivity of 29% for alcohol problems in the ED.7
Self-report may be enhanced when specific alcohol questions are
to detect alcohol use disorders. The CAGE was developed in 1968 as
a brief screening tool for primary care providers to detect alcohol
The MAST (Michigan Alcohol-Screening Test), developed in 1971 as
a screen for alcohol abuse and dependence, has 24 yes/no questions.
developed in 1972 to screen for alcohol abuse and dependence. It
drinkers. WHO developed the AUDIT (Alcohol Use Disorder
at-risk drinking in addition to alcohol abuse and dependence. AUDIT
about even lower levels of alcohol consumption in this group has
screens for alcohol abuse and dependence. It has five questions,
minutes to administer.33 T-ACE also screens for alcohol abuse and
at-risk drinking, alcohol abuse, and dependence. It is a
Rapid Alcohol Assessment Screen (RAPS4). Cherpitel screened an ED
alcohol?"- followed by three questions about alcohol consumption
an ICD-10 diagnosis of alcohol dependence.7 In the second study,
with an ICD-10 or DSM-IV diagnosis of alcohol dependence, harmful
84%, for a DSM-IV diagnosis of alcohol dependence.37 Fiellin
reviewed 38 studies of screening for alcohol use disorder in the
For alcohol abuse or dependence, CAGE was found most effective with
best within the spectrum of alcohol use they were developed to
were the best tests for alcohol dependence among women. Their
sensitivities (59% and 48% respectively) for alcohol dependence
Alcohol concentration
identify intoxication. The presence of alcohol may not always
indicate an alcohol problem. While a very high BAC in an unimpaired
insensitive screen for an alcohol use disorder. One study found
that only one-third of intoxicated drivers had an alcohol use
disorder.43 In an ED study, BAC was a poor screen for alcohol abuse
self-reported drinking.7 In another ED study, a saliva alcohol
center, BAC had a sensitivity of 63% for an alcohol disorder.5
with sensitivities of 13% to 67% for alcohol use disorders or
and confronting patients with their blood alcohol levels may
reveal the negative consequences or link alcohol to current
staff does not use structured questionnaires for alcohol screening.
ED staff has no systematic approach to alcohol screening. Staff
rates. EDs have reported high case rates of alcohol problems,
trauma, injuries, assaults,72 depression, and alcohol-related
ED patient care should be improved by implementing alcohol
the lack of counseling available to address patients' alcohol
Most EDs provide very limited alcohol services. When care is
volume of alcohol-involved patients, and the capacity to undertake
4. National Institute on Alcohol Abuse and Alcoholism. The
Physician's Guide to Helping Patients with Alcohol Problems.
Alcohol Use Disorders Identification Test in screening trauma
6. Gale T, Ja W, Welty T. Differences in detection of alcohol
7. Cherpitel C. Screening for alcohol problems in the emergency
8. Cherpitel C. Comparison of screening instruments for alcohol
regions of the country. Alcohol Clin Exp Res 1997;21:1391-7.
alcohol intoxication and chronic alcohol abuse on outcome from
alcohol problems in the emergency department, part 1: improving
the breath alcohol analyzer. Ann Emerg Med 1984;13:516-20.
12. Gibb K. Serum alcohol levels, toxicology screens, and use
of the breath alcohol analyzer. Ann Emerg Med 1986;15:349-53.
Clifford P. Alcohol use among subcritically injured emergency
alcohol-related problems in general practice. J Stud Alcohol
with the Alcohol Use Disorders Identification Test (AUDIT) in an
acute alcohol intoxication and chronic alcohol dependence by trauma
screening in an ambulatory care setting. J Stud Alcohol
20. Fleming M, Barry K. A three-sample test of a masked alcohol
screening questionnaire. Alcohol 1991;26:81-91.
validation of a new alcohol screening instrument. Am J Psychiatry
Short Michigan Alcoholism Screening Test (SMAST). J Stud Alcohol
Alcohol Clin Exp Res 1987;11:269-73.
computer-administered formats. Alcohol Clin Exp Res
31. Saunders J, Aasland O, Amundsen A, Grant M. Alcohol
With Harmful Alcohol Consumption, I. Addiction 1993;88:349-62.
Development of the Alcohol Use Disorders Identification Test
pregnancy risk-drinking. Alcohol Clin Exp Res 1994;18:1156-61.
drinking in the emergency room: the RAPS4. Rapid Alcohol Problems
Screen. J Stud Alcohol 2000;61:447-9.
in an emergency room population. J Stud Alcohol 1998;59:420-6.
the CAGE, the Brief Michigan Alcohol Screening Test, and the
Alcohol Use Disorders Identification Test in screening trauma
38. Fiellin DA, Reid MC, O'Connor PG. Screening for alcohol
screening instruments for identifying harmful drinking and alcohol
dependence in the emergency room. Alcohol Clin Exp Res
instruments for alcohol problems in the emergency room. J Stud
Alcohol 1995;56:695-700.
41. Bradley KA, Boyd-Wickizer J, Powell SH, Burman ML. Alcohol
43. Gijbers A, Raymond A, Whelan G, et al. Does a blood alcohol
M. Prevalence and recognition of alcohol abuse in a primary care
instruments. Drug Alcohol Depend 1995;40:151-8.
Objective diagnosis of alcohol abuse: compared values of
transferase (GGT), and mean corpuscular volume (MCV). Alcohol Clin
clinic: is this test useful in assessing alcohol consumption?
Alcohol. 1998;33:304-9.
transferrin and conventional alcohol markers as indicators for
Alcohol Clin Exp Res 1998;22:892-6.
A. Screening for excessive alcohol drinking: comparative value of
Cigarette, alcohol, and other drug use by school-age pregnant
brief intervention for adolescent alcohol use. Arch Pediatr Adolesc
and the risk of alcohol dependence. Addiction 1993;88:1209-18.
62. Bercsi S, Brickner P, Saha D. Alcohol use and abuse in the
Alcohol Depend 1993;33:139-49.
64. Fink A, Hays RD, Moore AA, Beck JC. Alcohol-related
encountered with opportunistic screening for alcohol-related
68. Burke T. The economic impact of alcohol abuse a
(base) mominahabibi@Mominas-MBP docsearch % 
```
using command grep with -iw `-i` (ignore case) so it makes grep case insensitive and `-w` (word-regexp) ensures that grep matches only those words, not the words containing those characters. It is so useful the time that we want to find the word regardless of whether the characters are in uppercase or lowercase.  

- Second alternate way of using the command grep with 
Example 1:
```
code
```
Example 2:
```
code
```

- Third alternate way of using the command grep with 
Example 1:
```
code
```
Example 2:
```
code
```

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

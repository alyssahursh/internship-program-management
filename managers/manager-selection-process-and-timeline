# Manager Selection Timeline and Process


Competitive manager selection is critical to the success of all Ada interns. Managers who *want* to host interns are more likely to provide high-quality internships. In order to have a competitive application process, we aim to get at least 3x the number of applications as we have internships.

## Selection Timeline

The manager selection process takes two months. Ada asks that we have managers selected four months before internships start. To meet Ada’s timeline, this is the required schedule for manager selection:

|Task	|H1 - February Start	|H2 - August Start	|Working backwards	|
|---	|---	|---	|---	|
|Update application	|August 15th	|February 15th	|-57 days	|
|Send out application	|September 1st	|March 1st	|-40 days	|
|Application due date	|September 15th	|March 15th	|-26 days	|
|Score applications	|Sept 16th - 30th	|March 16th - 30th	|-25 days	|
|Notify applicants	|October 1st	|April 1st	|-10 days	|
|Confirmation deadline	|October 11th	|April 11th	|0 days	|

## NEW APPLICATION QUESTIONS FOR C17:

**New race and equity questions:**
Ada sent us an email with their application questions some time in the past six months. Please find it, review it and add questions to our application to meet the bar for these topics.

**New gender affirming questions:**
You are introducing yourself to someone you don’t know. How do you do it?

* I’m <your name>, as in “I’m Priya”
* I’m <your name>, I use <your pronouns> pronouns, as in “I’m Priya, I use she/her pronouns”


You’re interviewing a candidate and you haven’t been told their pronouns. What do you do? (Select all)

* Assume pronouns based on their name and appearance
* Politely ask for their pronouns
* Use their name in place of pronouns until you know what their pronouns are


Please write a sentence using the singular “they” to reference an individual. If you don’t know how to do this, write “I don’t know how to do this”
<short form text box answer>

I affirm that gender is a spectrum and that there are more than two genders. I understand that Ada serves women and gender expansive adults. I will not use the word “females” to talk about Ada interns in aggregate. I will not assume the gender identity or pronouns of anyone that I interview or supervise through the Ada program. I will proactively apologize for my mistakes if I make them. I will teach my team the same.

* Confirm that you agree




## Selection Process

1. **Update the application form**. C16 application form: https://survey.fieldsense.whs.amazon.dev/survey/6b0a6880-66aa-45c9-8431-e662605cb1f1
    1. Update dates and costs
    2. Consult with manager selection committee to update wording/LP questions based on past cohort success and challenges
    3. **FOR C17 INCORPORATE ADA’S QUESTIONS:**
        
    4. [Image: Ada scoring rubric1.jpg]
    5. [Image: Ada scoring rubric.jpg]
2. **Send out the application** **announcement** via email and Slack. Before sending, ask a reviewer to verify all dates and links. The goal is to get 3x the number of applications that we need. Don’t be afraid to send many reminders!
    1. [Manager Application Solicitation - Email](https://quip-amazon.com/8NXhACze36BU)
    2. [Manager Application Solicitation - Slack Messages](https://quip-amazon.com/5Z9FAbz86zJt)
3. **Score applications**
    1. **Validate manager eligibility** — Ask an engineer to run this command against a list of applicant aliases
        `for user in $(cat managers.txt) ; do echo -n $user", "; /usr/bin/ldapsearch -x -h ldap.amazon.com -p 389 -b "o=amazon.com" -s sub uid=$user amznjobcode description | grep 'description:\|amznjobcode:' done`
    2. **Static scores** — **** Short-form questions are scored accordingly (this needs to be re-evaluated for C16; not all attributes apply in the same way anymore):
        1. L5 or L6 manager: 1 point (we no longer accept applications from L7 managers)
        2. Team size between 5 and 9 engineers: 1 point
        3. Has had an Ada intern in the past: 1 point per successful intern
        4. Has an Ada alum on their team now: 1 point
        5. Has volunteered with Ada in any capacity: 1 point
    3. **Qualitative scores** — Long-form questions are graded by a panel of Ada alumni. 
        1. Ask the alum representative to assemble a team of 8 to 12 volunteers
        2. Assign each application a unique identifier (integers incrementing from 1 is sufficient). Using unique identifiers instead of applicant names helps remove bias.
        3. For each long-form question, create separate spreadsheets
            1. Column A: Application identifier
            2. Column B: Long-form answer
            3. Column C: Blank column for score
        4. Alphabetize the spreadsheet by column B (this helps randomize the order of applications from one question to the next)
        5. Provide spreadsheets to the alum representative to send to volunteers using the [Manager Application Long-Form Question Scoring Instruction Email](https://quip-amazon.com/2sAwAOdVuq19). Each question should be sent to 2 to 3 readers.
        6. Collate and average scores from all spreadsheets, add qualitative scores to static scores 
    4. **Stack rank** — Total static and qualitative scores. Sort from high to low in two groups: Seattle-based and fully remote. Select managers in order. Wait list length should be 20% of total accepted managers.
4. **Notify** applications using the selected, wait list, and not selected email templates
    1. [Manager Selection Email - Selected](https://quip-amazon.com/tcWLAvKd4JG9)
    2. [Manager Selection Email - Wait List](https://quip-amazon.com/Z6DzAnbWGDos)
    3. [Manager Selection Email - Not Selected](https://quip-amazon.com/2mx4A1rxX6wQ)
5. Request **confirmation** from all selected managers. If managers do not confirm within the allotted time frame, or if they respond saying that they are no longer able to host an intern, work through the wait list in ranked order.





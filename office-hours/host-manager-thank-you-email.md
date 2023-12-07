# Intern Office Hours - Manager Thank You

**Recipients:** Office hour hosts, managers

**Subject:** Thank you to our Ada C17 Intern Technical Office Hours hosts!

**Body:**

Hello, managers of [Intern Office Hour](https://w.amazon.com/bin/view/Ada_Developers_Academy/Intern_Office_Hours/) hosts!
 
With the help of your engineers, we were able to provide more than 150 hours of hands-on technical mentorship and answer more than 750 technical questions for Cohort 17 Interns from [Ada Developers Academy](https://adadevelopersacademy.org/) (H2 2022). Our interns regularly gave me feedback that attending office hours was one of the highlights of their day, and many of them cited the program as one of the reasons that they were able to meet the SDE1 bar by the end of their internships. 
 
Thank you, office hours hosts (and managers!), for your commitment to Hire and Develop the Best, Learn and Be Curious, and Strive to be Earth’s Best Employer. I couldn’t do this without you!
 
Cheers,



```
for user in $(cat mentors.txt) ; do echo -n $user:" "; /usr/bin/ldapsearch -x -h ldap.amazon.com -p 389 -b "o=amazon.com" -s sub uid=$user manager | grep manager:
done
```




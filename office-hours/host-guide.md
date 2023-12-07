# Intern Office Hours - Host Guide



### Chime bridge

https://chime.aws/intern-office-hours

### Time management

Office hours is first-come-first-served. Ask your attendees to use the Chime hand raise feature so that you can see you has questions (versus who is just there to listen in). Use that list to determine how long you can linger on any given question. Typically, we see 2 to 5 interns asking questions in a given session.

### Common topics

* Getting rid of red squiggles in IntelliJ (Lombok, Workspace sync, code they started writing and then abandoned mid-thought)
* Every flavor of git pickle imaginable (squash/fixup, rebasing, very occasionally reflog)
* Learning good git practices
* Writing unit tests, mocking (often JUnit, Mockito)
* Deploying to a test account (CDKBuild, SAMToolkit)
* Opening CRs (especially when multiple packages are involved)
* Responding to CR comments
* BONES services (typically Lambda or ECS)
* CDK (typically TypeScript)
* Common AWS services: Lambda, ECS, DynamoDB, SQS, IAM
* Learning how to read error messages
* Learning how to search Code Browser effectively



### Start by getting the lay of the land

To be as useful and efficient as possible, it helps to get a picture of what the intern is starting with. 

* **Check git.** I always begin with (and regularly return to) some quick git basics (`git status`, `git log --oneline`, `git show`) I’m looking for the following: What branch are we on? What commit is `origin/HEAD` pointing to? What local changes do we have? When is the last time the intern rebased against origin/mainline?
* **Check the brazil workspace** with `brazil ws show`. What other packages do we have? What version set are we using, and what revision number are we on? When is the last time the intern synced their version set metadata?
* **Get good at spotting edits in the IDE.** IntelliJ gives us lots of hints about what has changed if we look at the line numbers. New lines get a green block, edited lines get a blue block, deleted lines get a tiny little triangle arrow. 



### Be on the lookout for things to stop and fix

There are a handful of things that can make development extremely painful. Rather than ignoring those pain points, stop and fix what you can. Here are somethings that I’m constantly looking out for:

* **Persistent untracked files in git** (things like `.iml` or `.idea` files, build directories, etc). Stop and fix by adding the things we know we don’t want to track to a global .gitignore
* **Red squiggly lines in the IDE.** This can be a lot of different things, but whatever it is, it *has* to be fixed. Here are some common problems that cause red squiggly lines:
    * **Red squiggles in the Config file:** something is wrong with the version set. Maybe the intern has added a dependency that doesn’t exist in the version set (fix by doing a [brazil workspace merge](https://builderhub.corp.amazon.com/docs/brazil/cli-guide/brazil-commands-workspace.html#brazil-workspace-merge) to add the dependency locally without impacting the production version set), or maybe someone else has added a dependency that the intern got in a `git pull --rebase` and they haven’t synced their metadata (run `brazil ws sync -md`)
    * **Red squiggles related to Lombok annotations** (@Builder, @RequiredArgsConstructor, etc): Make sure that the Lombok plugin is installed and that annotation processing is enabled: https://sage.amazon.com/posts/764293
    * **Red squiggles for other imports:** Does another package in this workspace need to be built? Do you need to sync the IDE from the brazil workspace?
    * **Red squiggles that seem random:** Did the intern make incomplete changes somewhere and then leave them? We can’t do that! Either complete, revert, or stash the changes.
* **Unable to run unit tests in the IDE.** Sometimes interns are unaware that they *can* or *should* run unit tests in their IDE. Show them how! If the tests fail in the IDE but `brazil-build` succeeds, review the test failure output to figure out why, and try to resolve the issue.
* **Unable to brazil-build (or whatever build command is appropriate for the package).** Investigate. When was the last time that the intern *could* successfully build the package? What has changed since then? Often this stems from having multiple packages in a brazil workspace and having only pulled changes for one of them. If the package has ever built, start with resetting to mainline and building from scratch (meaning pull every package, clean the workspace, sync metadata, recursive build). If the intern has never been able to successfully build the package locally, that’s a huge red flag. Does this package only build on a dev desktop (typical for Python), but the intern doesn’t know that? Is something even weirder going on? Even if the intern is coming to office hours with an unrelated question, focus on the build issue. We can’t complete tasks if we can’t build our code. 



### Show how you know

You aren’t a savant! You’re just an engineer who has learned some strategies that work for you. Teach interns your strategies. Here are some of mine:

* **Find examples of similar code** in other packages by using the [advanced Code Browser search](https://builderhub.corp.amazon.com/docs/code-browser/user-guide/code-search.html) options. Some things I reach for regularly include:
    * **Searching for code inside a specific set of repositories** with the `rp:` flag. My team’s packages mostly start with CAP, so if I want to search only in my own team’s packages, I can do that with `rp:CAP*`. Maybe you only want examples from Lambda packages: `rp:*Lambdax`
    * **Searching for code in certain file types** **or paths** with the `fp:` flag. Maybe you only want java files: `fp:*java`. Maybe you only want Config files: `fp:*Config`.
* **Use Sage** and I mean *use* Sage. Yes, you can search for questions that have already been asked and answered, but you can also *ask questions*. I know that asking questions publicly is scary, but also *we are at work and everyone has to use their real work name on Sage*. People have to be nice. And in my experience, they are! Encourage interns to ask questions on Sage. You can help them word their questions so that they’ll be most likely to get responses. 
* **Point them to interest groups.** Does the framework or language they’re using have a dedicated Slack channel? A major-domo list? Can we ask a question there?
* **Read documentation together**. Often, interns are handed documentation that no one has vetted for them. Ask the intern to read their documentation to you. What do they understand? What don’t they understand? Is there better documentation available for that subject?



### It’s okay to say you don’t know the answer

We can’t all be experts in every topic. Sometimes the best you can do is help someone think through their problem, or help give them more confidence in asking a subject matter expert for help. If you’re stumped it’s okay to say so!


### When to ask for intervention

Part of hosting office hours is keeping an eye out for bad situations that indicate the need for intervention or escalation. Here are some reasons I have intervened in the past:

* Intern has not been assigned or is not regularly meeting with an on-team mentor
* Manager regularly cancels intern’s 1:1s on short notice or without rescheduling
* Intern is working on a project on a long-lived branch with no code review
* Intern is assigned a project that previously belonged to another intern
* Intern has not been assigned a project by end of week 7
* Intern has been exposed to mean lies, like “I’m not sure anyone from this program could be successful at Amazon” or “It took me three tries to land this job, so it’s probably going to take you at least that long”
* Intern indicates that they are working unsustainable hours
* Obviously any sexism, genderism, racism, ableism, etc etc etc

You don’t have to do the actual escalation; Alyssa is happy to get the right people involved. All you have to do is raise the concern. 


### Additional resources

* Need help explaining Brazil? I wrote a doc: [What is Brazil?](https://quip-amazon.com/974bAxjJCXvl)
* Need help explaining $PATH? I wrote a doc: [What the $PATH](https://quip-amazon.com/lvOxAkw3PtOF)
* Questions about changing teams after internship? I wrote a doc: [How to Change Teams After Internship](https://quip-amazon.com/Z5dgAPOIic2n)
* Looking for great trainings on specific topics? Always check Engineering Excellence: 
    * Official catalog: https://w.amazon.com/bin/view/EE/Learn
    * Community catalog: https://w.amazon.com/bin/view/EE/Learn_Community



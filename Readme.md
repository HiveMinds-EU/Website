# Hiveminds website.



0. A very basic textbox, where people can select their university>Bachelor/Master>Course>year. (And add a new <whatever>= University, bachelor, master, course and/or year if it does not exist yet).

1. A capcha is put on the input of a new <whatever>.

2. Next the input gets filtered to determine if it matches the criteria to store in the MongoDB.

3. The data from the MongoDB gets passed to the Java backend which controls the sub-repository: https://github.com/a-t-0/CoursePlanningTemplate

4. A copy/new instance of the `PlanningData-Form.ods` is made.

5. This is hosted on the Collabora Online environment which is hosted on Nextcloud with Let's Encrypt SSL, which is hosted in a Docker Container.

6. If the course (year) is already filled by some user, the user can:
	6.1 (inspect filled ods if the user wants)
	6.2 Immediately get the google calendar link (or caldav if its implemented)
	6.3 Immediately chose an old exam that the user wants to solve for access to the other exam solutions.
	6.4 Immediately get an overleaf link to the old exam solution template to start editing directly.
	6.5 Get a unique hashcode, so that we don't need to store private data with an (pseudo)-anonymous user.
	6.6 Immediately get the taskwarrior commands for their own taskwarrior instance.
	
7. If the course is not yet filled in, the user is requested to fill in the data.
	7.1 If some data is not yet available, the user should be able to click a button to get a polite template outlook mail to send daily from their university to their teacher automatically asking the data untill it is provided. (User should set emails to stop).
	7.2 After the data is filled in, the user should click "done" so that the backend can start generating the data specified in points 6.2-6.5.
	
8. A separate box should be provided where users can enter their unique hash, to say "I'm done with the exam, please let some (other anonymous person check it) (and a second random anonymous checker to prevent too much gaming the system for access). Once submitted and approved by at least 1 checker *Chicken and egg, this is not possible for the first 2 users* , the user will be asked to check two other submissions before being granted access. 

9. Once the solutions are verified, the user is able to view the solutions in the browser (github pdfs) (such that the user can also improve other solutions via "Issues".)

Basic Rules
===========

1. Review the questions in this file. Reply back via email with an estimated delivery date.

2. Answer each of the questions below.

3. Add your answer to each question to this file, in-line.

4. Send the final file back for review.

5. Bonus points if you add this initial file to your public git repo and share that repo with us so we can see how your answers progressed.

6. You may use external sources to help answer the questions (i.e. Google, etc), but you should always cite your sources in your comments. Learning from others is good. Plagiarism is bad.


Developer Test
==============

1.  What editor will you use to edit this file, and why?

	* I will use sublime text because it has support to develop in many languages making easy view code and do some tasks.

2.  Some of the questions will ask for a solution in the language of your choice.  What language(s) will you choose, and why?
	
	* As first option i will use Java because is the languaje that i currently use to make backend developments and secondly JavaScript because I have used it in previous jobs to backend and frontend development

3.  Explain the difference between testing and debugging.

	* The main diference is the stage when you apply those ideas, 'testing' is to know if something is working as you expected, generally in the development phase and can be done by the development team or specifically by the testing team. In the other hand, 'debuggin' is done to fix bugs raised in the previous phase and is totally done for the development team.

4.  Consider a user querying a search engine.  Describe, in as much detail as you like, what happens between the user clicking the "submit" button and the display of the results.

	* when the user click the submit button, the html form information is collected to be send to the backend engine
	* the backend engine takes that information and apply its algorithms to find the best coincidences
	* when the information is ready to be send back to the browser, depending the used approach, the backend send the data purely or in html markup previously built in the backend
	* if the browser received only data, the client is responsible to format that information to build the html markup
	* the information is shown to the customer as html page

The two tables below describe relationships between employees, managers, and departments (the columns employee.mgr_id and department.head both refer to employee.id).  Use these definitions to answer questions 5-10.  If you need to use any nonstandard functions or syntax, be sure to name the DBMS that implements them.


employee                              / department

 id |        name        | mgr_id |   |     name      | head
----|--------------------|--------|---|---------------|------
  1 | Jonathan Archer    |     11 |   | Operations    |   11
  2 | Christopher Pike   |     12 |   | Marketing     |   12
  3 | James Kirk         |     13 |   | IT            |   13
  4 | Jean-Luc Picard    |     14 |   | HR            |   14
  5 | Kathryn Janeway    |     15 |   | Sales         |   15
  6 | Ralph Wiggum       |     11
  7 | Troy McClure       |     12
  8 | Waylon Smithers    |     17
  9 | Edna Krabappel     |     16
 10 | Ned Flanders       |     15
 11 | Buffy Summers      |
 12 | Xander Harris      |
 13 | Willow Rosenberg   |
 14 | Rupert Giles       |
 15 | Oz Selbie          |
 16 | Dade Murphy        |     11
 17 | Kate Libby         |     13
 18 | Paul Cook          |     17
 19 | Emmanuel Goldstein |     16
 20 | Winston Smith      |     15
 21 | Thomas Anderson    |     15
 22 | Agent Smith        |     14
 23 | Malcolm Reynolds   |     14
 24 | River Tam          |     18
 25 | Jason Nesmith      |     18


5.  Write an SQL query to list the full name of every employee, alphabetized by first name.

6.  Write an SQL query to list the full name of every employee, alphabetized by last name.

7.  Write an SQL query to list the full name of every employee along with the full name of his/her manager.

8.  Write an SQL query to list the full name of every employee in the Sales department.

9.  Write an SQL query to list the full name of every employee along with name of his/her department.

10. Is there a better design for a database that supports the queries described in questions 5-9?  If so, describe it.  If not, why not?

11. Write a function in the language of your choice that implements quicksort on an array of integers.

12. Write a function in the language of your choice that performs binary search on a sorted array of integers.

13. Write a function in the language of your choice performs the query you wrote for question 7, and outputs the results as an HTML table.

14. Write a program in the language of your choice that takes a filename and a number N as arguments and retrieves and outputs the Nth line from the file.

15. Write the function from question 12 in a different language.

16. Write the program from question 14 in a different language (it can be the same language you used for #15, but it doesn't have to be).

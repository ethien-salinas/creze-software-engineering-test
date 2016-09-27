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

5.  Write an SQL query to list the full name of every employee, alphabetized by first name.

	```SQL
	select name from employee order by name;
	```

6.  Write an SQL query to list the full name of every employee, alphabetized by last name.

	```SQL
	select
	  SUBSTRING(name, 1, CHARINDEX(' ', name ) - 1) AS FirstName,
	  SUBSTRING(name, CHARINDEX(' ', name) + 1, 8000) AS LastName
	from
	 employee
	order by LastName;
	```
	Resources:
	* [Informix SUBSTRB function]
	* [Informix CHARINDEX function]
	* [Stackoverflow substring-in-informix]

7.  Write an SQL query to list the full name of every employee along with the full name of his/her manager.

	```SQL
	select e1.name as employee, e2.name as manager
	from employee e1, employee e2
	where e1.mgr_id = e2.id;
	```
	Resources:
	* [Stackoverflow same table twice]

8.  Write an SQL query to list the full name of every employee in the Sales department.

	```SQL
	select employee.name
	from employee, department
	where head = mgr_id
	and department.name = 'Sales';
	```

9.  Write an SQL query to list the full name of every employee along with name of his/her department.

	```SQL
	select employee.name, department.name
	from employee, department
	where head = mgr_id;
	```

10. Is there a better design for a database that supports the queries described in questions 5-9?  If so, describe it.  If not, why not?
	* In order to link the two tables easily, department should have an id and the employee table a foreign key to that id

11. Write a function in the language of your choice that implements quicksort on an array of integers.

	```Java
	public class Quicksort  {
	  private int[] numbers;
	  private int number;

	  public void sort(int[] values) {
	    // check for empty or null array
	    if (values ==null || values.length==0){
	      return;
	    }
	    this.numbers = values;
	    number = values.length;
	    quicksort(0, number - 1);
	  }

	  private void quicksort(int low, int high) {
	    int i = low, j = high;
	    // Get the pivot element from the middle of the list
	    int pivot = numbers[low + (high-low)/2];

	    // Divide into two lists
	    while (i <= j) {
	      // If the current value from the left list is smaller then the pivot
	      // element then get the next element from the left list
	      while (numbers[i] < pivot) {
	        i++;
	      }
	      // If the current value from the right list is larger then the pivot
	      // element then get the next element from the right list
	      while (numbers[j] > pivot) {
	        j--;
	      }

	      // If we have found a values in the left list which is larger then
	      // the pivot element and if we have found a value in the right list
	      // which is smaller then the pivot element then we exchange the
	      // values.
	      // As we are done we can increase i and j
	      if (i <= j) {
	        exchange(i, j);
	        i++;
	        j--;
	      }
	    }
	    // Recursion
	    if (low < j)
	      quicksort(low, j);
	    if (i < high)
	      quicksort(i, high);
	  }

	  private void exchange(int i, int j) {
	    int temp = numbers[i];
	    numbers[i] = numbers[j];
	    numbers[j] = temp;
	  }
	}
	```
	Resources:
	* [vogella - Quicksort in Java]

12. Write a function in the language of your choice that performs binary search on a sorted array of integers.

	```Java
	public class BinarySearch {
	  public static boolean contains(int[] a, int b) {
	    if (a.length == 0) {
	      return false;
	    }
	    int low = 0;
	    int high = a.length-1;

	    while(low <= high) {
	      int middle = (low+high) /2; 
	      if (b> a[middle]){
	        low = middle +1;
	      } else if (b< a[middle]){
	        high = middle -1;
	      } else { // The element has been found
	        return true; 
	      }
	    }
	    return false;
	  }
	}
	```
	Resources:
	* [vogella - Binary Search]

13. Write a function in the language of your choice performs the query you wrote for question 7, and outputs the results as an HTML table.

	```Java
	// in the backend we make the call to the database
	public List<Element> getElements(RecordSearchRequest request){
		return elementRepository.findAll(ElementSpecifications.elementByGeneral(request));
	}
	```

	```Java
	// in the frontend we make a call to the backend to get the elements
	RecordSearchResponse responses = restClient.getElements(recordSearchRequest);
	List<Element> elementsFound = responses.getElementsFound();
	model.addAttribute("responses", elementsFound);
	```

	```html
	<table class="table table-striped">
		<thead>
			<tr>
				<th>employee</th>
				<th>manager</th>
			</tr>
		</thead>
		<tbody>
			<tr th:each="response : ${responses}">
				<td th:text="${response.employee}">employee</td>
				<td th:text="${response.manager}">manager</td>
			</tr>
		</tbody>
	</table>
	```
	Resources:
	* [Tutorial: Thymeleaf + Spring]

14. Write a program in the language of your choice that takes a filename and a number N as arguments and retrieves and outputs the Nth line from the file.

	```Java
	import java.io.BufferedReader;
	import java.io.FileNotFoundException;
	import java.io.FileReader;
	import java.io.IOException;

	public class ReadNthLineOfFile {

		private static String path = "C:/Users/salinased/Documents/LoremIpsum.txt";
		private static int line = 7;
		
		public static void main(String[] args) {
			ReadNthLineOfFile readNthLineOfFile = new ReadNthLineOfFile();
			readNthLineOfFile.readFile(path, line);

		}
		
		private void readFile(String path, int lineToRead){
			try(BufferedReader br = new BufferedReader(new FileReader(path))) {
			    String line = "";
			    while (line != null) {
			        for(int i=0; i<lineToRead; i++){		        	
			        	line = br.readLine();
			        }
			        System.out.println(line);
			    }
			} catch (FileNotFoundException e) {
				e.printStackTrace();
			} catch (IOException e) {
				e.printStackTrace();
			}
		}

	}
	```
	Resources:
	* [Stackoverflow reading-a-plain-text-file-in-java]

15. Write the function from question 12 in a different language.

16. Write the program from question 14 in a different language (it can be the same language you used for #15, but it doesn't have to be).

[Informix SUBSTRB function]: <https://www.ibm.com/support/knowledgecenter/SSGU8G_11.70.0/com.ibm.sqls.doc/ids_sqs_1985.htm#ids_sqs_1985>
[Informix CHARINDEX function]: <http://www.ibm.com/support/knowledgecenter/SSGU8G_12.1.0/com.ibm.sqls.doc/ids_sqs_0294.htm#ids_sqs_0294>
[Stackoverflow substring-in-informix]: <http://stackoverflow.com/questions/20792045/substring-in-informix>
[Stackoverflow same table twice]: <http://stackoverflow.com/questions/7383753/is-it-possible-to-use-the-same-table-twice-in-a-select-query>
[vogella - Quicksort in Java]: <http://www.vogella.com/tutorials/JavaAlgorithmsQuicksort/article.html>
[vogella - Binary Search]: <http://www.vogella.com/tutorials/JavaAlgorithmsSearch/article.html#binarysearch>
[Tutorial: Thymeleaf + Spring]: <http://www.thymeleaf.org/doc/tutorials/2.1/thymeleafspring.html>
[Stackoverflow reading-a-plain-text-file-in-java]: <http://stackoverflow.com/questions/4716503/reading-a-plain-text-file-in-java>
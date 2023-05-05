Download Link: https://assignmentchef.com/product/solved-dbs211-lab5-sql-ddl
<br>
The purpose of this lab is to introduce you to the DDL set of statements in SQL.  By writing SQL to create tables, constraints, and views, you will have the tools needed to implement database designs that you will create later in the course.  By finishing this lab, the student will be able to:

<ul>

 <li>create, modify, and drop tables based on design specifications provided,</li>

 <li>inserting new data into tables, update data in tables, and delete data from tables while considering referential integrity,</li>

 <li>enforce constraints on tables to ensure data integrity and consistency, create a table using the structure and data from an existing table,</li>

 <li>import data into a table from other tables.</li>

</ul>

Submission:

<strong><em>Your submission will be a single text-based .</em></strong><strong><em>SQL</em></strong><strong><em> file with the solutions provided. </em></strong>

Your submission needs to include a comment header block and be commented to include the question and the solutions. Make sure every SQL statement terminates with a semicolon.

Tasks:

Add

<h1>SET AUTOCOMMIT ON;</h1>

under the comment header and execute it Consider the following table specifications:

Part A (DDL) :

<ol>

 <li>Create table the following tables and their given constraints:</li>

</ol>

<strong>L5_MOVIES</strong> (movieid:int, title:varchar(35), year:int, director:int,score:decimal(3,2))

<table width="650">

 <tbody>

  <tr>

   <td width="84"><strong>Column Name </strong></td>

   <td width="92"><strong>Column DataType </strong></td>

   <td width="73"><strong>PK </strong></td>

   <td width="74"><strong>Not  Null </strong></td>

   <td width="78"><strong>Unique </strong></td>

   <td width="72"><strong>FK </strong></td>

   <td width="78"><strong>Default Value </strong></td>

   <td width="98"><strong>Validation </strong></td>

  </tr>

  <tr>

   <td width="84">mid</td>

   <td width="92">Int</td>

   <td width="73">✓</td>

   <td width="74"> </td>

   <td width="78"> </td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="84">title</td>

   <td width="92">varchar(35)</td>

   <td width="73"> </td>

   <td width="74">✓</td>

   <td width="78"> </td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="84">releaseYear</td>

   <td width="92">Int</td>

   <td width="73"> </td>

   <td width="74">✓</td>

   <td width="78"> </td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="84">director</td>

   <td width="92">Int</td>

   <td width="73"> </td>

   <td width="74">✓</td>

   <td width="78"> </td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="84">score</td>

   <td width="92">decimal(3,2)</td>

   <td width="73"> </td>

   <td width="74"> </td>

   <td width="78"> </td>

   <td width="72"> </td>

   <td width="78"> </td>

   <td width="98">&lt; 5 and &gt; 0</td>

  </tr>

 </tbody>

</table>










<strong>L5_ACTORS</strong> (actorid:int, name:varchar(20), lastname:varchar(30))

<table width="650">

 <tbody>

  <tr>

   <td width="79"><strong>Column Name </strong></td>

   <td width="93"><strong>Column DataType </strong></td>

   <td width="74"><strong>PK </strong></td>

   <td width="75"><strong>Not  Null </strong></td>

   <td width="79"><strong>Unique </strong></td>

   <td width="74"><strong>FK </strong></td>

   <td width="79"><strong>Default Value </strong></td>

   <td width="98"><strong>Validation </strong></td>

  </tr>

  <tr>

   <td width="79">aid</td>

   <td width="93">Int</td>

   <td width="74">✓</td>

   <td width="75"> </td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="79">firstName</td>

   <td width="93">varchar(20)</td>

   <td width="74"> </td>

   <td width="75">✓</td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="79">lastName</td>

   <td width="93">Varchar(30)</td>

   <td width="74"> </td>

   <td width="75">✓</td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

 </tbody>

</table>




<strong>L5_CASTINGS</strong> (movieid:int, actorid:int)

<table width="650">

 <tbody>

  <tr>

   <td width="79"><strong>Column Name </strong></td>

   <td width="93"><strong>Column DataType </strong></td>

   <td width="74"><strong>PK </strong></td>

   <td width="75"><strong>Not  Null </strong></td>

   <td width="79"><strong>Unique </strong></td>

   <td width="74"><strong>FK </strong></td>

   <td width="79"><strong>Default Value </strong></td>

   <td width="98"><strong>Validation </strong></td>

  </tr>

  <tr>

   <td width="79">movieid</td>

   <td width="93">Int</td>

   <td width="74">✓</td>

   <td width="75"> </td>

   <td width="79"> </td>

   <td width="74">✓ (movies)</td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="79">actorid</td>

   <td width="93">int</td>

   <td width="74">✓</td>

   <td width="75"> </td>

   <td width="79"> </td>

   <td width="74">✓(actors)</td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

 </tbody>

</table>




<strong>L5_DIRECTORS</strong>(id:int, name:varchar(20), lastname:varchar(30))

<table width="650">

 <tbody>

  <tr>

   <td width="79"><strong>Column Name </strong></td>

   <td width="93"><strong>Column DataType </strong></td>

   <td width="74"><strong>PK </strong></td>

   <td width="75"><strong>Not  Null </strong></td>

   <td width="79"><strong>Unique </strong></td>

   <td width="74"><strong>FK </strong></td>

   <td width="79"><strong>Default Value </strong></td>

   <td width="98"><strong>Validation </strong></td>

  </tr>

  <tr>

   <td width="79">directorid</td>

   <td width="93">Int</td>

   <td width="74">✓</td>

   <td width="75"> </td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="79">firstname</td>

   <td width="93">varchar(20)</td>

   <td width="74"> </td>

   <td width="75">✓</td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

  <tr>

   <td width="79">lastname</td>

   <td width="93">varchar(30)</td>

   <td width="74"> </td>

   <td width="75">✓</td>

   <td width="79"> </td>

   <td width="74"> </td>

   <td width="79"> </td>

   <td width="98"> </td>

  </tr>

 </tbody>

</table>




<ol start="2">

 <li>Modify the <strong><em>movies</em></strong> table to create a foreign key constraint that refers to table <strong><em>directors</em></strong>.</li>

 <li>Modify the <strong><em>movies</em></strong> table to create a new constraint so the uniqueness of the movie title is guaranteed.</li>

 <li>Write insert statements to add the following data to table <strong><em>directors</em></strong> and <strong><em>movies</em></strong>.</li>

</ol>

<strong>Director </strong>

<table width="390">

 <tbody>

  <tr>

   <td width="126"><strong>directorid </strong></td>

   <td width="147"><strong>First name </strong></td>

   <td width="117"><strong>Last name </strong></td>

  </tr>

  <tr>

   <td width="126"><strong>1010 </strong></td>

   <td width="147">Rob</td>

   <td width="117">Minkoff</td>

  </tr>

  <tr>

   <td width="126"><strong>1020 </strong></td>

   <td width="147">Bill</td>

   <td width="117">Condon</td>

  </tr>

  <tr>

   <td width="126"><strong>1050 </strong></td>

   <td width="147">Josh</td>

   <td width="117">Cooley</td>

  </tr>

  <tr>

   <td width="126"><strong>2010 </strong></td>

   <td width="147">Brad</td>

   <td width="117">Bird</td>

  </tr>

  <tr>

   <td width="126"><strong>3020 </strong></td>

   <td width="147">Lake</td>

   <td width="117">Bell</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>             </strong>

<strong>Movies </strong>

<table width="635">

 <tbody>

  <tr>

   <td width="126"><strong>id </strong></td>

   <td width="147"><strong>title </strong></td>

   <td width="117"><strong>year </strong></td>

   <td width="120"><strong>director </strong></td>

   <td width="125"><strong>score </strong></td>

  </tr>

  <tr>

   <td width="126"><strong>100 </strong></td>

   <td width="147">The Lion King</td>

   <td width="117">2019</td>

   <td width="120">3020</td>

   <td width="125">3.50</td>

  </tr>

  <tr>

   <td width="126"><strong>200 </strong></td>

   <td width="147">Beauty and the Beast</td>

   <td width="117">2017</td>

   <td width="120">1050</td>

   <td width="125">4.20</td>

  </tr>

  <tr>

   <td width="126"><strong>300 </strong></td>

   <td width="147">Toy Story 4</td>

   <td width="117">2019</td>

   <td width="120">1020</td>

   <td width="125">4.50</td>

  </tr>

  <tr>

   <td width="126"><strong>400 </strong></td>

   <td width="147">Mission Impossible</td>

   <td width="117">2018</td>

   <td width="120">2010</td>

   <td width="125">5.00</td>

  </tr>

  <tr>

   <td width="126"><strong>500 </strong></td>

   <td width="147">The Secret Life of Pets</td>

   <td width="117">2016</td>

   <td width="120">1010</td>

   <td width="125">3.90</td>

  </tr>

 </tbody>

</table>




<ol start="5">

 <li>Write SQL statements to remove all above tables.</li>

</ol>

Is the order of tables important when removing? Why?

Part B (More DML):

<ol start="6">

 <li>Create a new empty table <strong><em>employee2</em></strong> the same as table <strong><em>employees</em></strong>. Use a single statement to create the table and insert the data at the same time.</li>

 <li>Modify table <strong><em>employee2</em></strong> and add a new column <strong><em>username</em></strong> to this table. The value of this column is not required and does not have to be unique.</li>

 <li>Delete all the data in the <strong><em>employee2</em></strong> table</li>

 <li>Re-insert all data from the <strong><em>employees</em></strong> table into your new table <strong><em>employee2 </em></strong>using a single statement.</li>

 <li>In table <strong><em>employee2</em></strong>, write a SQL statement to change the first name and the last name of employee with ID <strong><em>1002</em></strong> to your name.</li>

 <li>In table <strong><em>employee2</em></strong>, generate the email address for column <strong><em>username</em></strong> for each student by concatenating the first character of employee’s first name and the employee’s last name. For instance, the username of employee Peter Stone will be <strong><em>pstone</em></strong>. NOTE: the username is in all lower case letters.</li>

 <li>In table <strong><em>employee2</em></strong>, remove all employees with office code 4.</li>

 <li>Drop table <strong><em>employee2</em></strong>.</li>

</ol>
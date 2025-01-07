
<hr style="height:3px; border:none; background-color:grey ;">

# `6. Practice Assignments`

## Task 1: Create a "CodingGita Students" database

#### Create a new MongoDB database called CodingGita. Add two collections:


* students: Name, roll number, department, year, courses enrolled.



**Insert sample data into both collections.**



Step 1: Insert sample data into the students collection


```
db.students.insertMany([
  { 
    "name": "Ashwani kumar",
    "rollNumber": 111,
    "department": "Computer Science",
    "year": 1,
    "coursesEnrolled": ["CS111", "CS111"]
  },
  {
    "name": "Mayur",
    "rollNumber": 1002,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS10011", "CS10033"]
  },
  { 
    "name": "Jagtap",
    "rollNumber": 1003,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  },
  { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS102"]
  },
  { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS103"]
  },
  { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  }

]);
```
***

* courses: Course code, name, credits, instructor.




Step 2: Insert sample data into the courses collection


```
db.courses.insertMany([
  { 
    "courseCode": "CS101", 
    "courseName": "Introduction to Computer Science", 
    "credits": 4, 
    "instructor": "Dr. jane Doe" 
  },
  { 
    "courseCode": "MATH201", 
    "courseName": "Calculus ", 
    "credits": 3, 
    "instructor": "Dr.John Smith" 
  },
  { 
    "courseCode": "PHY301", 
    "courseName": "Physics for Engineers", 
    "credits": 4, 
    "instructor": "Dr. Emily Clark" 
  },
  { 
    "courseCode": "EE01", 
    "courseName": "Basic Electrical Engineering", 
    "credits": 4, 
    "instructor": "Prof. Verma" 
  },
  { 
    "courseCode": "EE02", 
    "courseName": "Circuit Theory", 
    "credits": 4, 
    "instructor": "Prof. Yadav" 
  },


]);

```
At this point, you have successfully inserted data into the students and courses collections.

<hr style="height:3px; border:none; background-color:grey">

## Task 2: Perform CRUD operations

* Add a few more ` students` and `courses` to the database.



```
db.students.insertOne([{"name":"ak", }])
```
```
db.stuents.insertMany([
  {
    "name":"Jeevan",
    "rollNumber" : 105,
    "department" : "ComputerScience",
    "year" : 1,
    "coursesEnrolled":["CS101"]

  },
  {
    "name":"Krishna",
    "rollNumber" : 1006,
    "department" : "ComputerScience",
    "year" : 1,
    "coursesEnrolled": ["CS101"]

  }

])

```

At this point, you have successfully inserted data into the ` students ` collections.

<hr style="height:3px; border:none; background-color:grey">

 Add a few more ` courses` to the database.

 ```
 db.courses.insertOne([{courseCode: 'CS109',courseName: 'Ethical Hacking', credits: 4, instructor: 'Hacker'}])
 ```

 ```
 db.courses.insertMany([
  {
    "courseCode": "CS001",
    "courseName": "Full Stack Development",
    "credits": 5,
    "instructor": "Coding Gita" ,
  },
  {
    "courseCode": "CS201",
    "courseName":" Database",
    "credits" :5,
    "instructor" :" Ramesh Kumar", 
  
  }])

```
## ` Querying Data`

### Now, let's perform some queries to fetch data based on different conditions.

**Step 1: Query students based on department If we want to find all students in the Computer Science department, we can use the find method with a query filter.**
```
 db.students.find({ "department": "Computer Science" });
```

This query will return all students who belong to the Computer Science department.

<hr style="height:3px; border:none; background-color:grey;">

**Step 2: Query students based on year If we want to find students who are in year 2, we can query the students collection like this:**

```
db.students.find({ "year": 2 });
```
This will return all students who are in the second year.

**Step 3: Query students by course enrollment Let’s say you want to find all students who are enrolled in CS101. You can perform the following query:**

```
db.students.find({ "coursesEnrolled": "CS101" });
```
This query will return all students who are enrolled in the CS101 course.

<hr style="height:3px; border:none; background-color:grey">

## `Updating  Data`



* Updating data in MongoDB is easy with the ` updateOne` and `updateMany` methods. Let’s go through some examples of how to update data.



Step 1: Update a student’s courses Let’s say Ashwani Kumar wants to update his courses and add the CS102 course to his list of enrolled courses.
```
db.students.updateOne(
  { "name": "Ashwani kumar " },
  { $push: { "coursesEnrolled": "CS102" } }
);
```
This command will update Ashwani kumar  document by pushing CS102 into his coursesEnrolled array.



**Step 2: Update a student’s rollNumber Let’s say Ashwani Kumar  wants to update his rollNumber and add the roll number 112 rollNumber to his list of students.

```
db.students.updateOne(
  { _id: ObjectId("677cade6eeb22330e4cbd8fa") },  
  { $set: { rollNumber: 112 } } 
);
```
This command will update the rollNumber 


**Step 3: Update a course instructor If Prof. Gupta is no longer teaching Data Structures (CS102), we can update the instructor for that course.**

```
db.courses.updateOne(
  { "courseCode": "CS102" },
  { $set: { "instructor": "Prof. Mehta" } }
);
```
This query updates the instructor field for the course CS102 to Prof. Mehta.

## `Deleting  Data`

Deleting data in MongoDB is straightforward. You can use the deleteOne or deleteMany methods to remove documents.


**Step 1: Delete a student record If we want to delete Mayur’s student record from the database, we can do so with the following command:**

```
db.students.deleteOne({ "name": "Mayur" });
``` 
This will delete the document where the `name` field is Mayur.

**Step 2: Delete all students from a specific department Let’s say we want to remove all students from the Electrical Engineering department:**
```
db.students.deleteMany({ "department": "Electrical Engineering" });
```
This will delete all students in the Electrical Engineering department.




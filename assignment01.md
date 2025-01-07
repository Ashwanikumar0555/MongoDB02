
# More Practice Tasks

## Task 1: Add multiple students

Insert at least 5 `students` into the students collection with unique roll numbers, names, departments, years, and subjects enrolled.

```
db.students.insertMany([
    {
        "name" :"Ankit",
        "rollNumber":1230,
        "department" : "Computer Science",
        "year" : 1,
        "subjectEnrolled" : ["React","NodeJS","MongoDB"]
    },

    {
        "name":"shubham",
        "rollNumber":"1231",
        "department" : "Computer Science",
        "year" :2,
        "subjectEnrolled" :["React","NodeJS","MongoDB","Express.JS"]
    },

    {
        "name":"Kapil",
        "rollNumber":1232,
        "department":"Iit",
        "year":1,
        "subjectEnrolled" : ["React","NodeJS","Math"]
    },
    {
    "name":"Kashyap",
    "rollNumber":1233,
    "department" :"Computer Science",
    "year": 3,
    "subjectEnrolled" :["React","NodeJS","MongoDB"]
    },
     {
        "name":"Aditya",
        "rollNumber":1234,
        "department":"Computer Science",
        "year":1,
        "subjectEnrolled" : ["React","NodeJS","Math"]
    },

]);
```
<hr style="height:3px; border-none; background-color:grey">

## Task 2: Add multiple subjects
 Insert sample data into the subjects collection

```
db.students.insertMany([
    {
        "subjectName" :"React",
        "topics":[
            "JSX","Components","Vite","Classbased Component"
        ]
    },

    {
        "subjectName" :"React",
        "topics":[
            "React","Virtual Dom","State","Hooks"]
    },
    {
        "subjectName" :"NodeJS",
        "topics":[
            "File System","Modules","Express"]
    },

{
        "subjectName" :"MongoDB",
        "topics":[
            "Database Design","CRUD Operations","Indexes"]
    },

{
        "subjectName" :"React",
        "topics":[
            "Get","Post","Put","Delete"]
    },

{
        "subjectName" :"React",
        "topics":[
            "React","Life Cycle","Props","Functional Component"]
    }




    ]);
```




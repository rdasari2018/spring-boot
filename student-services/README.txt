Get Project
===========
git clone https://github.com/rdasari2018/spring-boot.git

Import Project into Eclipse
===========================
File > Import > Maven > Import existing Maven projects > Root directory - C:\Users\ramesh\git_projects\spring-boot\student-services > Check pom.xml

Build Project in Eclipse
========================
Right click student-services > Run as > Maven install

Run Project
===========
Right click StudentServicesApplication.java > Run as > Java application

Integration Test controller methods using Postman
=================================================
Start Application and Tomcat Server by Right clicking StudentServicesApplication.java > Run as > Java application

Test retrieveCoursesForStudent method in StudentController.java
---------------------------------------------------------------
http://localhost:8080/students/Student1 Set Accept header with value application/json

Test retrieveDetailsForCourse method in StudentController.java
--------------------------------------------------------------
http://localhost:8080/students/Student1/courses/Course1 Set Accept header with value application/json

Test registerStudentForCourse method in StudentController.java
--------------------------------------------------------------
http://localhost:8080/students/Student1/courses 
Request type is POST.
Set Content-Type header with value application/json.
Set following in the body of the message.
{
  "name": "Microservices",
  "description": "10 Steps",
  "steps": [
    "Learn How to Break Things Up",
    "Automate the hell out of everything",
    "Have fun"
  ]
}
Above POST request returns Status of 201 Created and also returns Location response header with value http://localhost:8080/students/Student1/courses/gig5flr370m4gp2sjgplv37rt0

Integration Test controller methods using TestRestTemplate
==========================================================
No need to start Application or Tomcat server.
Following action automatically starts Tomcat server at a random port.
Right click StudentControllerIT.java > Run As > JUnit Test

Unit Test controller methods using MockMvc and Mockito
======================================================
Right click StudentControllerTest.java > Run As > JUnit Test
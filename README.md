# Part 1.1 - Create `Person` Class
* Create a `Person` class.
	* `Person` constructor should have a parameter of type `String` which sets the `name` instance-variable to the respective value.
	* `Person` should have a `getName()` method which returns the `Person` object's `name` variable.
	* `Person` should have a `setName()` method which sets the `Person` object's `name` variable.

-
# Part 1.0 - Test `Person`
* Create a `TestPerson` class.
	* Create a `testSetName` method which ensures that a `Person` object's `name` variable is being set by invoking the `.setName` method.
	* Create a `testConstructor` method which ensures that a `Person` object's `name` variable is being set by invoking the `Person` constructor.

-
# Part 2.0 - Create `Learner` Interface
* Create a `Learner` interface.
	* `Learner` should declare one method signature:
		* Method name: `learn`
		* Method parameters: `double numberOfHours`
		* Method return-type: `void`

-
# Part 3.1 - Create `Student` Class
* Create a `Student` class such that:
	* `Student` is a subclass of `Person`
	* `Student` implements the `Learner` interface
	* `Student` should have an instance variable `totalStudyTime` of type `double`
	* `Student` should have a concrete implementation of the `learn` method which increments the `totalStudyTime` variable by the specified `numberOfHours` argument.
	* `Student` should have a `getTotalStudyTime()` method which returns the `totalStudyTime` instance variable.


-
# Part 3.0 - Test `Student`
* Create a `TestStudent` class.
	* Create a `testImplementation` method that asserts that a `Student` is an `instanceof` a `Learner`.
	* Create a `testInheritance` method that asserts that a `Student` is an `instanceof` a `Person`.
	* Create a `testLearn` method that ensures a `Student`'s `totalStudyTime` instance variable is incremented by the specified `numberOfHours` by invoking the `.learn` method.

-
# Part 4.0 - Create `Teacher` Interface
* Create a `Teacher` interface.
	* `Teacher` should declare a `teach` method signature:
		* Method name: `teach`
		* Method parameters:
			* `Student student`
			* `double numberOfHours`
		* Method return-type: `void` 

	* `Teacher` should declare a `lecture` method signature:
		* Method name: `lecture`
		* Method parameters:
			* `Student[] student, double numberOfHours`
		* Method return-type: `void`

		
-
# Part 5.1 - Create `Instructor` Class
* Create an `Instructor` class such that:
	* `Instructor` is a subclass of `Person`
	* `Instructor` implements the `Teacher` interface
	* `Instructor` should have a concrete implementation of the `teach` method which invokes the `learn` method on the specified `Student` object.
	* `Instructor` should have a concrete implementation of the `lecture` method which invokes the `learn` method on the specified array of `Student` objects.
		* `numberOfHours` should be evenly split amongst the students.
			* `double numberOfHoursPerStudent = numberOfHours / students.length;`

-
# Part 5.0 - Test `Instructor`
* Create an `TestInstructor` class.
	* Create a `testImplementation` method that asserts that an `Instructor` is an `instanceof` a `Teacher`.
	* Create a `testInheritance` method that asserts that a `Instructor` is an `instanceof` a `Person`.
	* Create a `testTeach` method that ensures when an `Instructor` invokes the `.teach` method, a respective student's `totalStudyTime` instance variable is incremented.
	* Create a `testLecture` method that ensures when an `Instructor` invokes the `.teach` method, a respective student's `totalStudyTime` instance variable is incremented.

	
-
# Part 6.1 - Create `DelTech` Class
* Create a `DelTech` class.
	* _Statically_ instantiate a `private` `ArrayList` of `Instructor` objects called `instructorList`.
	* Create a `public static` method called `hire` which adds an `Instructor` to the `instructorList` and returns `void`.
	* Create a `public static` method called `getInstructors` which returns the `instructorList`.
	* Create a `public static` method called `fireStaff` which clears our `instructorList`.
	* Copy and paste this `static initialization block` immediately below your `instructorList` declaration.

```java
static { // static initializer
	String[] instructorNames = { "Brian", "Kaleb", "Zan"};
	for (String instructorName : instructorNames) {
		Instructor instructor = new Instructor(instructorName);
		hire(instructor);
	}
}
```


-
# Part 6.0 - Test `DelTech`
* Create a `TestDelTech` class.
	* Create a method named `setup` which is annotated with `@Before`, takes has no parameters, and returns `void`.
		* Ensure this method invokes the `.fireStaff` method on `DelTech`
	
	* Create a `testFireStaff` method which ensures that our `instructorList` in our `DelTech` class `isEmpty` upon invokation.
	* Create a `testHireStaff` method which ensures that our `instructorList` is populated with respective `Instructor` objects.

-
# Part 7.1 - Create `JavaAcademy` Class
* Create a `JavaAcademy` class.
	* _Statically_ instantiate a `private` `ArrayList` of `Student` objects called `studentList`.
	* Create a `public static` method called `recruitStudent` which adds a `Student` to the `studentList` and returns `void`.
	* Create a `public static` method called `getStudents` which returns the `studentList`.
	* Create a `public static` method called `removeStudents` which clears our `studentList`.
	* Copy and paste this `static initialization block` immediately below your `studentList` declaration.

```java
static { // static initializer
	String[] studentNames = { "Jessica", "Emad", "Cedric", "Lolu", "Apoorva", "Vara", "Craig", "Robert",
			"Stephen", "Ferdinand", "Charu" };
	for (String studentName : studentNames) {
		Student student = new Student(studentName);
		studentList.add(student);
	}
}
```


-
# Part 7.0 - Test `JavaAcademy`
* Create a `TestJavaAcademy` class.
	* Create a method named `setup` which is annotated with `@Before`, takes has no parameters, and returns `void`.
		* Ensure this method invokes the `.removeStudents` method on `JavaAcademy`
	
	* Create a `testRemoveStudents` method which ensures that our `studentList` in our `JavaAcademy` class `isEmpty` upon invokation.
	* Create a `testRecruitStudent` method which ensures that our `studentList` is populated with respective `Student` objects.

-
# Part 8.1 - Create `ClassRoom` Class
* Create a `ClassRoom` class.
	* _Statically_ instantiate a `private` `ArrayList` of `Student` objects called `students` by invoking the `getStudents` method on the `JavaAcademy` class.
	* _Statically_ instantiate a `private` `ArrayList` of `Instructor` objects called `instructors` by invoking the `getInstructor` method on the `DelTech` class.
	* Create a method named `getRoster` which returns a `HashMapping` of `String` to `Person` objects such that our `DelTech` instructors and `JavaAcademy` students' names map to their respective `Person` object.

-
# Part 8.0 - Test `ClassRoom`
* Create a `TestClassRoom` class.
	* Assert that the `HashMapping` returned by `getRoster`, returns a `valueSet` containing each of the `Person` objects in `DelTech`'s `instructorList` and `JavaAcademy`'s `studentList`.# Classroom-OOP

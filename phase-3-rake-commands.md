made by chett!

# in your regular terminal

```$ rake db:create``` 
--> creates the db

```$ rake db:create_migration NAME=create_students```

```$ rake db:create_migration NAME=add_grade_and_birthdate_to_students```

```$ rake db:create_migration NAME=change_datatype_for_birthdate```
-->( at this point you'll go to the generated files and build them out )

```$ rake db:migrate```
( check the schema file to see if everything looks right )

```$ rake console```
--> opens up the pry console to play with our models

# now we are inside pry console

```pry> Student.all``` 
--> returns an empty array

```pry> greg = Student.new(name: "greg")```

```pry> greg.save```

```pry> Student.all```
--> we can now see greg is saved

```pry> Student.create(name: "greg")``` 
--> combines .new and .save

```pry> Student.find(2)``` 
--> returns the second greg since he has an id of 2
```pry> Student.find_by(name: "greg")``` --> returns only the first greg

```pry> Student.where(name: "greg")``` 
--> returns an array with both gregs

```pry> greg = Student.second``` 
--> gets the second student

```pry> greg.name = "Second Greg"```
```pry> greg.save``` 
--> the second student will now be named "Second Greg" in the db

```pry> greg.update(name: "the second greg")``` 
--> immediately updates the db 

```pry> greg.destroy``` 
--> greg gets deleted

```pry> Student.destroy_all``` 
--> deletes all the students

```pry> exit``` 
--> exits the console and we're back in the normal terminal

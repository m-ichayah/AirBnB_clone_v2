<center> <h1>HBNB - The Console</h1> </center>

This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

---

<center><h3>Repository Contents by Project Task</h3> </center>

| Tasks | Files | Description |
| ----- | ----- | ------ |
| 0: Authors/README File | [AUTHORS](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/AUTHORS) | Project authors |
| 1: Pep8 | N/A | All code is pep8 compliant|
| 2: Unit Testing | [/tests](https://github.com/m-ichayah/AirBnB_clone_v2/tree/dev/tests) | All class-defining modules are unittested |
| 3. Make BaseModel | [/models/base_model.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/base_model.py) | Defines a parent class to be inherited by all model classes|
| 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/base_model.py) | Add functionality to recreate an instance of a class from a dictionary representation|
| 5. Create FileStorage class | [/models/engine/file_storage.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/base_model.py) | Defines a class to manage persistent file storage system|
| 6. Console 0.0.1 | [console.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
| 7. Console 0.1 | [console.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
| 8. Create User class | [console.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/user.py) | Dynamically implements a user class |
| 9. More Classes | [/models/user.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/user.py) [/models/place.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/place.py) [/models/city.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/city.py) [/models/amenity.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/amenity.py) [/models/state.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/state.py) [/models/review.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/review.py) | Dynamically implements more classes |
| 10. Console 1.0 | [console.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/m-ichayah/AirBnB_clone_v2/blob/dev/models/engine/file_storage.py) | Update the console and file storage system to work dynamically with all  classes update file storage |
<br>
<br>
<center> <h2>General Use</h2> </center>

1. First clone this repository.

3. Once the repository is cloned locate the "console.py" file and run it as follows:
```
/AirBnB_clone$ ./console.py
```
4. When this command is run the following prompt should appear:
```
(hbnb)
```
5. This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

##### Commands
    * create - Creates an instance based on given class

    * destroy - Destroys an object based on class and UUID

    * show - Shows an object based on class and UUID

    * all - Shows all objects the program has access to, or all objects of a given class

    * update - Updates existing attributes an object based on class name and UUID

    * quit - Exits the program (EOF will as well)


##### Alternative Syntax
Users are able to issue a number of console command using an alternative syntax:

	Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
Advanced syntax is implemented for the following commands: 

    * all - Shows all objects the program has access to, or all objects of a given class

	* count - Return number of object instances by class

    * show - Shows an object based on class and UUID

	* destroy - Destroys an object based on class and UUID

    * update - Updates existing attributes an object based on class name and UUID

<br>
<br>
<center> <h2>Examples</h2> </center>
<h3>Primary Command Syntax</h3>

###### Example 0: Create an object
Usage: create <class_name>
```
(hbnb) create BaseModel
```
```
(hbnb) create BaseModel
58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa
(hbnb)                   
```
###### Example 1: Show an object
Usage: show <class_name> <_id>

```
(hbnb) show BaseModel 58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa
[BaseModel] (58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa) {'id': '58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa', 'created_at': datetime.datetime(2023, 3, 18, 12, 50, 26, 723532), 'updated_at': datetime.datetime(2023, 3, 18, 12, 50, 26, 723538)}
(hbnb)  
```
###### Example 2: Destroy an object
Usage: destroy <class_name> <_id>
```
(hbnb) destroy BaseModel 58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa
(hbnb) show BaseModel 58d6e9e8-69e0-4c5b-a9a5-ddaa71b60cfa
** no instance found **
(hbnb)   
```
###### Example 3: Update an object
Usage: update <class_name> <_id>
```
(hbnb) update BaseModel 0d0e9e86-7c37-4201-baa0-0984334193e3 first_name "person"
(hbnb) show BaseModel 0d0e9e86-7c37-4201-baa0-0984334193e3
[BaseModel] (0d0e9e86-7c37-4201-baa0-0984334193e3) {'id': '0d0e9e86-7c37-4201-baa0-0984334193e3', 'created_at': datetime.datetime(2023, 3, 18, 12, 54, 43, 753877), 'updated_at': datetime.datetime(2023, 3, 18, 12, 55, 38, 760855), 'first_name': 'person'}
(hbnb)
```
<h3>Alternative Syntax</h3>

###### Example 0: Show all User objects
Usage: <class_name>.all()
```
(hbnb) User.all()
["[User] (a7fac951-fd73-4012-80bc-cc76baaff483) {'id': 'a7fac951-fd73-4012-80bc-cc76baaff483', 'created_at': datetime.datetime(2023, 3, 18, 12, 58, 0, 602393), 'updated_at': datetime.datetime(2023, 3, 18, 12, 58, 0, 602399)}", "[User] (07b53722-01a7-46e0-b29c-acbe1b5542ae) {'id': '07b53722-01a7-46e0-b29c-acbe1b5542ae', 'created_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431370), 'updated_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431395)}"]
```

###### Example 1: Destroy a User
Usage: <class_name>.destroy(<_id>)
```
(hbnb) User.destroy("a7fac951-fd73-4012-80bc-cc76baaff483")
(hbnb)
(hbnb) User.all()
["[User] (07b53722-01a7-46e0-b29c-acbe1b5542ae) {'id': '07b53722-01a7-46e0-b29c-acbe1b5542ae', 'created_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431370), 'updated_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431395)}"]
```
###### Example 2: Update User (by attribute)
Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
```
(hbnb) User.update("07b53722-01a7-46e0-b29c-acbe1b5542ae", name "Michayah the Developer")
(hbnb)
(hbnb) User.all()
["[User] (07b53722-01a7-46e0-b29c-acbe1b5542ae) {'id': '07b53722-01a7-46e0-b29c-acbe1b5542ae', 'created_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431370), 'updated_at': datetime.datetime(2023, 3, 18, 13, 0, 15, 261324), 'name': 'Michayah the Developer'}"]
```
###### Example 3: Update User (by dictionary)
Usage: <class_name>.update(<_id>, <dictionary>)
```
(hbnb) User.update("07b53722-01a7-46e0-b29c-acbe1b5542ae", {'name': 'Iniovosa the King', 'age': 18})
(hbnb)
(hbnb) User.all()
["[User] (07b53722-01a7-46e0-b29c-acbe1b5542ae) {'id': '07b53722-01a7-46e0-b29c-acbe1b5542ae', 'created_at': datetime.datetime(2023, 3, 18, 12, 58, 17, 431370), 'updated_at': datetime.datetime(2023, 3, 18, 13, 2, 37, 141170), 'name': 'Iniovosa the King', 'age': 18}"]
```
<br>

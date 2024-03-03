# <img src="https://camo.githubusercontent.com/f44314db051c0cdabdd42c8c2372f4ebadb17dc9d4137004e8acf524ccf3ca9d/68747470733a2f2f692e696d6775722e636f6d2f656c72346168392e706e67" width="30"> AirBnB Clone V.4 - Web dynamic

## Description
This repository hosts the fourth iteration of a project aimed at constructing a replica of the AirBnB website. Version 4 introduces a console and an API for managing program data. Through console commands and the API, users can create, update, and delete objects, as well as oversee file storage, utilizing either a JSON serialization system or MySQL as the database. Additionally, Flask was integrated into this version.

<p><img src="https://s3.amazonaws.com/intranet-projects-files/concepts/74/hbnb_step5.png" alt="step2"></p>

## Environment
This project is interpreted/tested on Ubuntu 14.04 LTS using python3 (version 3.4.3), jQuery (version 3.x), MySQL (version 5.7), Flask, and Chrome (version 57.0)

## Installation
* Clone this repository: `git clone "https://github.com/MedAmezzane/AirBnB_clone_v4.git"`
* Access AirBnb directory: `cd AirBnB_clone`
* Run hbnb(interactively): `./console` and enter command
* Run hbnb(non-interactively): `echo "<command>" | ./console.py`

[console.py](console.py) - the console contains the entry point of the command interpreter. 
List of commands this console current supports:
* `EOF` - exits console 
* `quit` - exits console
* `<emptyline>` - overwrites default emptyline method and does nothing
* `create` - Creates a new instance of`BaseModel`, saves it (to the JSON file) and prints the id
* `destroy` - Deletes an instance based on the class name and id (save the change into the JSON file). 
* `show` - Prints the string representation of an instance based on the class name and id.
* `all` - Prints all string representation of all instances based or not on the class name. 
* `update` - Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file). 

## File Structure
- **[api](api)** directory contains Flask web applications for a RESTful API
- **[models](models)** directory contains all classes used for this project:
- **[tests](tests)** directory contains all unit test cases for this project.
- **[web_dynamic](web_dynamic)** directory contains all files necessary to start a dynamic Flask web application.
- **[web_flask](web_flask)** directory contains all files necessary to start a Flask web application.
- **[web_static](web_static)** directory contains all html, css and images used for the static website.
- [0-setup_web_static.sh](0-setup_web_static.sh) - bash script that sets up web servers for the deployment of `web_static`
- [1-pack_web_static.py](1-pack_web_static.py) - Fabric script that generates a .tgz archive from the contents of `web_static`, using the function `do_pack`
- [2-do_deploy_web_static.py](2-do_deploy_web_static.py) - Fabric script (based on [1-pack_web_static.py](1-pack_web_static.py)) that distributes an archive to web servers, using the function `do_deploy`
- [3-deploy_web_static.py](3-deploy_web_static.py) - Fabric script (based on [2-do_deploy_web_static.py](2-do_deploy_web_static.py)) that creates and distributes an archive to web servers, using the function `deploy`
- [AUTHORS](AUTHORS) - list of Authors who have worked on this project.
- [console.py](console.py) - the console is a command line used to interact with the storage engines. 
- [setup_mysql_dev.sql](setup_mysql_dev.sql) - MySQL script to set-up the hbnb_dev_db database.
- [setup_mysql_test.sql](setup_mysql_test.sql) - MySQL script to set-up the hbnb_test_db database.

### Console Example:
```
vagrantAirBnB_clone$./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
daa82102-ef67-4863-b7f4-7a45d8923514
(hbnb) all BaseModel
[[BaseModel] (daa82102-ef67-4863-b7f4-7a45d8923514) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': 'daa82102-ef67-4863-b7f4-7a45d8923514', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel daa82102-ef67-4863-b7f4-7a45d8923514
[BaseModel] (daa82102-ef67-4863-b7f4-7a45d8923514) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': 'daa82102-ef67-4863-b7f4-7a45d8923514', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel daa82102-ef67-4863-b7f4-7a45d8923514
(hbnb) show BaseModel daa82102-ef67-4863-b7f4-7a45d8923514
** no instance found **
(hbnb) quit
```

### Acknowledgements
Thanks to all the peers who contributed their knowledge.

### Authors
* Mohamed AMEZZANE <[MedAmezzane](https://github.com/MedAmezzane)>
* Abdelouahed OUARRAR <[ouarrar](https://github.com/ouarrar)>

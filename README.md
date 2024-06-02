AirBnB Clone V4
This project is a comprehensive full-stack web application, integrating a MySQL database and a Flask RESTful API with a dynamic HTML5/CSS3/jQuery front-end. It is inspired by the core features of the Airbnb platform.

Iterations
The project was developed over several iterations, with V4 being the final version. Each iteration added new concepts and integrations, detailed below.

The Console
The first iteration focused on building an interactive console for development testing.

Features
The Console operates with a temporary storage engine based on JSON and includes the following features:

Create a new object (e.g., a new User or a new Place)
Retrieve an object from a file or a database
Perform operations on objects (count, compute stats, etc.)
Update attributes of an object
Destroy an object
Modes
The Console has two modes:

Interactive Mode:

bash
Copy code
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
Non-Interactive Mode:

bash
Copy code
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
Web Static
This phase involved building the basic CSS and HTML source code for the application.

MySQL
This phase focused on data modeling for the relational database using MySQL.

Web Framework
This iteration introduced dynamic content generation using Flask and Jinja, implementing Server-Side Rendering (SSR).

The MySQL database served content to the client, providing backend-based features. All HTML and CSS source code was hosted on the server and generated dynamically, rather than being hard-coded.

RESTful API
To enhance dynamic content generation, a RESTful API was developed using Flask and SQLAlchemy to interact with MySQL and respond to HTTP requests.

Endpoints
GET /api/v1/status: Returns the status of the API

GET /api/v1/stats: Retrieves the number of each object type

GET /api/v1/states: Retrieves the list of all State objects

GET /api/v1/states/<state_id>: Retrieves a State object

DELETE /api/v1/states/<state_id>: Deletes a State object

POST /api/v1/states: Creates a State

PUT /api/v1/states/<state_id>: Updates a State object

GET /api/v1/states/<state_id>/cities: Retrieves the list of all City objects of a State

GET /api/v1/cities/<city_id>: Retrieves a City object

DELETE /api/v1/cities/<city_id>: Deletes a City object

POST /api/v1/states/<state_id>/cities: Creates a City

PUT /api/v1/cities/<city_id>: Updates a City object

GET /api/v1/amenities: Retrieves the list of all Amenity objects

GET /api/v1/amenities/<amenity_id>: Retrieves an Amenity object

DELETE /api/v1/amenities/<amenity_id>: Deletes an Amenity object

POST /api/v1/amenities: Creates an Amenity

PUT /api/v1/amenities/<amenity_id>: Updates an Amenity object

GET /api/v1/users: Retrieves the list of all User objects

GET /api/v1/users/<user_id>: Retrieves a User object

DELETE /api/v1/users/<user_id>: Deletes a User object

POST /api/v1/users: Creates a User

PUT /api/v1/users/<user_id>: Updates a User object

GET /api/v1/cities/<city_id>/places: Retrieves the list of all Place objects of a City

GET /api/v1/places/<place_id>: Retrieves a Place object

DELETE /api/v1/places/<place_id>: Deletes a Place object

POST /api/v1/cities/<city_id>/places: Creates a Place

PUT /api/v1/places/<place_id>: Updates a Place object

GET /api/v1/places/<place_id>/reviews: Retrieves the list of all Review objects of a Place

GET /api/v1/reviews/<review_id>: Retrieves a Review object

DELETE /api/v1/reviews/<review_id>: Deletes a Review object

POST /api/v1/places/<place_id>/reviews: Creates a Review

PUT /api/v1/reviews/<review_id>: Updates a Review object

GET /api/v1/places/<place_id>/amenities: Retrieves the list of all Amenity objects of a Place

DELETE /api/v1/places/<place_id>/amenities/<amenity_id>: Deletes an Amenity object from a Place

POST /api/v1/places/<place_id>/amenities/<amenity_id>: Links an Amenity object to a Place

POST /api/v1/places_search: Retrieves all Place objects based on the JSON in the request body

GET /apidocs: Retrieves the API documentation built with Flasgger

Web Dynamic
The final iteration involved switching from Server-Side Rendering to Client-Side Rendering using JavaScript with jQuery, leveraging the previously developed RESTful API.

Challenges and Future Features
This project was a significant undertaking that enhanced understanding of full-stack application development. Some of the most challenging aspects were the Object-Relational Mapping (ORM) for the API and the implementation of Client-Side Rendering.

Future projects can build upon this foundation to explore other technologies such as React, Node.js, and MongoDB, among others.

Getting Started
Prerequisites
Python 3.x
MySQL
Flask
SQLAlchemy
jQuery
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/AirBnB_clone_v4.git
cd AirBnB_clone_v4
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Set up the MySQL database:

sql
Copy code
CREATE DATABASE hbnb_dev_db;
Configure environment variables:

bash
Copy code
export HBNB_ENV=dev
export HBNB_MYSQL_USER=<your_mysql_user>
export HBNB_MYSQL_PWD=<your_mysql_password>
export HBNB_MYSQL_HOST=localhost
export HBNB_MYSQL_DB=hbnb_dev_db
export HBNB_TYPE_STORAGE=db
Usage
Start the console:

bash
Copy code
./console.py
Run the Flask app:

bash
Copy code
python3 -m web_dynamic.app
Access the application in your web browser:

arduino
Copy code
http://0.0.0.0:5000
Running Tests
To run tests, use the following command:

bash
Copy code
python3 -m unittest discover tests
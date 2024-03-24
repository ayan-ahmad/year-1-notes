## Course Stack
### Backend
- Python
- Django
### Frontend
- HTML
- CSS
- JS
- jQuery
- AJAX
## Web App Definition
- Web apps are Distributed Information Management system (DIM)
- Enables the management, sharing, finding, modification and presentation of information
- Does do over a network, in a distributed fashion
- Typically has many users, often geographically separated
- Ideally DIMs enable users to access timely, relevant and useful information in a seamless manner
## Types of Architecture
- System Architecture
	- To build the infrastructure for the distributed information management system
- Information Architecture
	- Provide information relevant to the sure effectively and efficiently
### Information Architecture
This is a user focused architecture, we must identify and cater to:
- What kind of users we expect
- What the users require
- What they should see and how efficient it is
- How it looks
### System Architecture
This is a system focused architecture, we must identify and cater to:
- What we need to make and gather the relevant requirements
- What systems we need to achieve this
- What is the order of execution
- How the data is interlinked (ERD Diagrams)
## Users
A user is a human or a machine which initiates contact with a client and interacts with it.
The user will have a different range of skills and capabilities and has a number of stuff they want to be satisfied.
## Clients
The client is a program sitting on a client device which:
- Accepts response messages
- Acts on the message by:
	- Communicating with the user
	- Affecting the environment
- Sends request messages
## How webpages work
- HTML
- CSS
- Javascript
- jQuery
- AJAX
## Messaging Protocols
- The request message protocol
	- It is usually HTTP(s) request
	- Any data sent can be any type
- The response message protocol
	- Is usually a HTTP(s) response
	- Content-type is usually HTML, JSON, XML
## Middleware
The middleware or application server is the bridge between the client and the server
## Backend/Database
The backend or database is typically on a separate node, and
- Stores the data for the application.
- Provides the data when needed.
- Needs to be scalable and reliable.
- Could be a database, an index, a flat file.
## Complexities
- Collision of Languages
	- Mark-up languages do not throw errors
	- Programming languages do throw errors and have things such as linters
	- Query languages are susceptible to logical errors but throw errors
- Shifting Standards
	- Data is being sent in different ways XML, JSON, YAML, etc.
- Web Browser Compatibility
	- Some browsers have different compatibilities especially in CSS and IE
- HTTP is a Stateless Protocol
	- It is not aware of persistent states
## DJango setup
1. [Download Python](https://www.python.org/downloads/)
2. [Set up the environment](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/)
3. Install Django 2.1.5 `pip install django==2.1.5`
4. Install Pillow `pip install pillow==5.4.1`
5. Run `python django-admin.py startproject [PROJECT_NAME]`
6. Then run `python manage.py migrate`
7. To run the server `python manage.py runserver`


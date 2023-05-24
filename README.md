## 1. A description of the scenario your project is operating in.
In the current economy of growing rents and as hybrid working culture still continues, a real-estate firm needs to reevaluate their rented office spaces in multiple buildings across Seattle for digital nomads. <br>

## 2. A description of what problem your project seeks to solve.
The firm seek to stop renting in at atleast one of their buildings to cut down budgets and therefore need to track how many conference rooms are actively in use across multiple building locations. <br>
To track all the spaces and who is working where, the startup needs to build a REST API. The API allows users to CREATE, DELETE and MODIFY buildings and rooms. <br>
The company also creates a front-end app that allows you to schedule a meeting in different rooms across buildings. This front-end is beyond the scope of this project.


## 3. A description of what the technical components of your project will be, including: the routes, the data models, any external data sources you'll use, etc.


### Models:
#### User Model:
Fields: email, password, role
#### Room model: 
Fields: id, name, number, building, reserve-start, reserve-end (duration)
#### Building model:
Fields: name, number


### DAOS:
Typical userDAO, roomDAO and buildingDAO to create, update, find and delete


## 4. Clear and direct call-outs of how you will meet the various project requirements.
#### Authentication and authorization:
Authentication: User needs to sign-up and login to access API routes. <br>
Authorization: Admins can GET, POST, PUT and DELETE all building and room data. User can only POST room data <br>


### 2 sets of CRUD routes:
#### User/Login: Signup, login. Password and logout routes
#### Rooms: get route, get/:id route, post route, put route
#### Building: post route, get route and get/:id route

### Indexes for performance:
Indexed at BuildingId to find all rooms and occupancy for a particular building. <br>
Indexed at roomId to find all users using a single room. <br>

### Aggregations/text search/lookups
#### Aggregate and lookup: 
Use lookup and aggregate to find building room statistics. Find buildings with maximum usage, find room in buildings with maximum usage and least values as well. <br>
Use lookup and aggregate to find user statistics: Find users that use spaces in more than one building, use more than one room, use multiple rooms in one day. <br>
Find rooms with maximum and minimum usage time.

## 5. A timeline for what project components you plan to complete, week by week, for the remainder of the class. 
(Weeks as per class schedule) <br>
* Week 07: Setup base project, model–schema and and implement user and room routes
* Week 08: Setup building routes and aggregates
* Week 09: Setup aggregates, lookups and tests
* Week 10: (Monday) : Spillage and presentation prep


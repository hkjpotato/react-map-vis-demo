# React + D3 Visualization of Electrical Grid System (DEMO)
#### Result

![gif](./time_series.gif)

<a href="http://example.com" target="_blank">http://example.com</a>
##### Most Update
<!-- __[Video (UX study version)]__ -->

<a href="https://youtu.be/D1Dew-8vRIQ" target="_blank">Video (UX study version)</a>

<!-- __[Prototype3 (time series)]__ -->

<a href="http://www.kjhuang.com/pgdemo3/" target="_blank">Prototype3 (time series)</a>


---

[test](http://test.com){:target="_blank"}

##### Old Version
[Video (geo based zoom)](https://youtu.be/9h0TL7uOntI){:target="_blank"}



<a href="https://youtu.be/9h0TL7uOntI" target="_blank">Video (geo based zoom)</a>

<!-- __[Prototype2]__ -->
<a href="http://www.kjhuang.com/pgdemo2/public/" target="_blank">Prototype2</a>


<!-- 
[Prototype3 (time series)]: <http://www.kjhuang.com/pgdemo3/>
[Prototype2]: <http://www.kjhuang.com/pgdemo2/public/>

[Video (geo based zoom)]: <https://youtu.be/9h0TL7uOntI>
[Video (UX study version)]: <https://youtu.be/D1Dew-8vRIQ>
[Video (time series version)]: <https://https://youtu.be/D1Dew-8vRIQ> -->
---

The backend django code is not open source anymore. You can check the front end [React](./static_version/react) to get and idea of the frontend code. 

Frankly speaking, this is not a pure React App as Google Map and D3 componenet are living outside the React controlled dom. The data is not strictly one way flow. For example, zoom event of Google Map is controlled by the Google Map API. Besides, the [MapVisManager](./static_version/react/app/components/MapVisUsage/MapVisManager.js) is controlling the d3 update pattern and other Map & Svg related update. Anything related to d3 svg is controlled outside React life cycle. 

Part of reason behind it is about teamwork, as one of my teammate is an expert in d3 but not in React. That is why you can see some ES6 code with ES5...


---
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

## Development Schedule(Outdate Schedule)
 - [First Stage](#first-stage)
 - [Second Stage](#second-stage)

<br />
##<a name="first-stage">First Stage (UI prototyping)</a>
In the first stage, we focus on making the primary interface for the web application, and primary design for the backend application as well as the database. 

For the frontend, I choose to use ReactJS + D3 + GoogleMap API to make the visualiztion, The reason is to maintain a uniform state for the front end and try to abstract the UI layer from the backend server.

For the backend, our team is using django with a relational database. We use django because:
 1. The legacy code is developed in flask. 
 2. The team is more familiar with python, the ananlysis tool is developed in python.
 3. We want to make use of the ORM model provided by django to work with SQL database.

The detailed requirements for the UI is belowed:

#### UI Purpose:
Provide an interface for user to clearly see the structure of a grid, and carry out CRUD manipulation on it. The grid system will be used as an input for smart power analysis tools.

#### User Requirements:
 - Display the layout of a grid system in different levels.
 - Being able to switch between two view modes (Vis + Table).
 - Under both modes, perform selection & filtering of the elements.
 - Under table mode, be able to sort the items.
 - The interaction of two modes should be sync.
 - CRUD of the elements.
 - Mapping. Show different details in different levels.

#### Design Challenges
There are 3 major challenges when developping this application
 - 1. Thinking in React: use React to maintain an uniform state of the application, and abstract the data of backend from the frontend UI.
 - 2. Let D3 work with React
 - 3. Dynamically fetching data for the map visualization based on viewport.


#### User Testing
I am going to carry out a user testing based on the current prototype. The details is in our team report.

<br />
##<a name="second-stage">Second Stage (Improvement of the backend and whole architecture)</a>
We have a prototyping working with our primary server at the first stage. However, the design of the backend is at very primary stage. And the CRUD function is not implemented. The reasons are:
 1. The information about what data should be stored is not totally clear at this stage.
 2. The manipulation of the data is not clear at this stage. We might need a RESTful API for our backend to work with frontend.
 3. I am still not professional in python, django and database. And I am not confident enough about the whole system design.

#### Purpose
At this stage, the team will focus on improving the backend code, both on the database and django server. We need to prove why REST is important and how it works with the frontend. The goal here is not to make thing work, but also work appropriately.

#### Study Planning for the second stage
To get more prepared, I am planning to take following steps:
 - Further Python study, focus on OOD and datatype ([python tutorial](http://wiki.jikexueyuan.com/project/start-learning-python/211.html)).
 - Further Django study, focus on model and database ([django doc](https://docs.djangoproject.com/en/1.10/topics/db/models/)).
 - Django REST framework ([Django REST doc](http://www.django-rest-framework.org/tutorial/5-relationships-and-hyperlinked-apis/)).
 - Database knowledge review ([w3chool SQL tutorial](http://www.w3schools.com/sql/), textbook(Fundamentals of Database Systems by Elmasri&Navathe)).
 - Taking a system design course.

#### Principles
To make sure we are coding properly, we need to follow some design principles through the whole development process, so that we are not 'anti-pattern'.

In summary, for the backend, we want to 
 1. Make code less verbose, and more robust.
 2. Increase DRYness, raises abstraction level.

#### Some sources for reference:
 1. [The right way to use ORM](https://www.dabapps.com/blog/higher-level-query-api-django-orm/)
 2. [React Principles](https://developmentarc.gitbooks.io/react-indepth/content/)


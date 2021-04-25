```yaml
milestone:
    iteration: 06
    title: "Testing"
    date: "April 21, 2021"
group:
    number: 3
    name: "Brick Database"
    members:
    - "Amina Mahmood"
    - "Aaron Joel Parker"
    - "Edward Riley"
```

# Development Book

### Section
- [Background](#background)
- [Project Description](#project-description)
- [Project Requirement](#project-requirement)
- [Business Rules](#business-rules)
- [Technologies Used](#technologies-used)
- [Design Patterns](#design-patterns)
- [Layering](#layering)
- [Timeline](#timeline)
- [Glossary](#glossary)
- [Current System](#current-system)
- [Goals](#goals)
- [Stakeholders](#stakeholders)
- [Error & Exception Handling](#error-and-exception-handling)
- [Performance & Refactoring](#performance-and-refactoring)
- [Testing](#testing)

## Team Members and Roles
- **Brick Database Team**
    - _Documentarian_
        - **Amina Mahmood**
    - _Code Reviewer_
        - **Aaron Joel Parker**
    - _Software Architect_
        - **Aaron Joel Parker**
    - _Configuration Manager_
        - **Amina Mahmood**
        - **Edward Riley**
    - _Team Coordinator_
        - **Edward Riley**
    


## Background
Reddit is a social news aggregation, web content rating, and discussion website, recently including livestream content through Reddit Public Access Network. Registered members submit content to the site such as links, text posts, and images, which are then voted up or down by other members. A subreddit is a specific online community, and the posts associated with it, on the social media website Reddit. Subreddit's are dedicated to a particular topic that people write about, and they're denoted by /r/, followed by the subreddit's name, e.g., /r/gaming.

## Project Description
The project serves to provide a statistical analysis to show the increase or decline of subreddit and content information per day. The project will assist us with the conclusion of whether the online presence on the Internet communities are growing or reducing per day.

## Project Requirement
- 24/7 Shared Server
- Relational Database 
- API Queries
- Object-Oriented Programming Language 

## Business Rules
- A day is between 12:00 PM - 11:59 AM.
- Cron's job execute python file to retrieve data from Reddit's API.
- Store to the local database.
- User load up the web-page, Nodejs load data to the React's component.
- User Interface will display the chart of data.

## Technologies Used
- Back-end
     - **PostgreSQL**
     - **NodeJS**
     - **Fastify**
- Front-end 
     -  **React.js** 
     -  **BootStrap**
- GitHub
    - GitHub URL: https://github.com/BrickDatabase

## Design Patterns
- **Model, View, Controller (MVC)**
  - Model (Nodejs) is responsible for represent data.
  - Controller (Nodejs) is responsible for manipulation of data.
  - View (React) displays data to the GUI.
- **Single Page Application (SPA)**
  - The single page application design pattern will fit all the interactive and swapping data will be in a single page.
- **Proxy**
  - This proxy design pattern will be using python as proxy to retrieve data from Reddit's api.
- **Observer**
  - The observer design pattern will be using socket.io and react hook as event listener.
- **Composition**
  - The composition design pattern will be using the React's Component to generate another component.

## Layering 

### Server-side Layers

#### Service Layer: **Python** & **Crontab Job**
  - This layer will include Python and Crontab Job tools.
  - The responsibility of this layer is to maintain data consistency. For each new day, the crontab job will be executed which will make an API request from the source containing the data and breaking them down to be organized. The organized data will be selectively passed to the data layer.

#### Data Layer: **PostgreSQL**
  - This layer will include the MySQL/MariaDB database tool and the Reddit API functionality. 
  - Once the data is passed from the service layer, the data will add a new record along with newly made unique identifier to be the primary key and a date of when the information was collected and data to be followed afterwards.  
  - The responsibilities of this layer will be store the collected data from the service layer and pass collected data to the business layer. 

#### Business Layer: **NodeJS** & **ExpressJS**
  - This layer will act as the controller for the presentation layer.
  - Using NodeJS and ExpressJS to represent and manipulate data. 


### Client-side Layers

#### Presentation Layer: **React.js**
  -  This layer will allow the user to search queries and display the chart of datas from a web browser

Our team will keep the user interface separated from the back-end by using the tactic Separate User Interface, which will allow changes to be made easier. 

The layered architecture diagram is provided below:
![alt text](https://raw.githubusercontent.com/BrickDatabase/documents/main/BrickDatabaseDiagram.png?token=AGWYD6JY3GFCJ42XLI4B22TAODVDM)


## Timeline

| Milestones                               | Planned Meeting Date | Start         | Deadline     |
|------------------------------------------|----------------------|---------------|--------------|
| Milestone 01 - Requirements              | Feb 5, 2021          | Feb 5, 2021   | Feb 12, 2021 |
| Milestone 02 - Design & Design Patterns  | Mar 4, 2021          | Mar 2, 2021   | Mar 5, 2021  |
| Milestone 03 - Layering                  | Mar 10, 2021         | Mar 10, 2021  | Mar 12, 2021 |
| Milestone 04 - Exception Handling        | Mar 24, 2021         | Mar 24, 2021  | Mar 26, 2021 |
| Milestone 05 - Performance & Refactoring | Apr 7, 2021          | Apr 7, 2021   | Apr 9, 2021  |
| Milestone 06 - Testing                   | Apr 21, 2021         | Apr 21, 2021  | Apr 23, 2021 |
| Milestone 07 - Deploying & Packaging     | Apr 28, 2021         | Apr 28, 2021  | Apr 30, 2021 |
--------------------------------------------------------------------------------------------------

## Glossary

* __Subreddit__ - A Subreddit is a sub community within Reddit. It usually follows a well-defined theme and people interested in the topic/theme can join it to share content with other members of the community.

* __Redditor__ - A Reddit user.

* __Upvote__ - It is vote used to show agreement with a comment or a post.

* __Downvote__ - A vote used to show disagreement with a comment or a post.

* __Comment__ - A response to a post or another comment.

* __Post__ - A post constitutes one of the following: A link to an external source, a cross-post which links to another post, rich media, or pain text.


## Current System

Reddit in its current form can be rather infuriating to use. Any edit made to a comment or a post is hidden and the original content cannot be seen again. It is also hard to visualize a lot of user generated data like votes due to Reddit's various obfuscation rules on it's frontend. It's API is also very cluttered and hard to use for the purpose of research.


## Goals

Our overall goal is to make a new facade for Reddit with archival features and a better but with selected subreddit communities, more uniform API. This is how we plan to accomplish it:

* ~~Goal #1: Accumulate and track the numbers of the subreddit communities from the beginning of semester to the end of the semester by each day.~~
* Revised Goal #1: Each member of the group will select the 2 subreddit communities to use for this course.
* Goal #2: Accumulate and track the numbers of the users in the selected subreddit communities from the beginning of semester to the end of the semester by each day.
* Goal #3: Accumulate and track the numbers of the posts in the selected subreddit communities from the beginning of semester to the end of the semester by each day.
* Goal #4: Identify the factors supporting the growth or decline of selected subreddit communities.
* Goal #5: Create a consistent real-time data visualization.


## Stakeholders

* Data scientists
    * We plan to tailor our exposed API and front-end to fit the needs of people in this field so minimal work is required to extract relevant information.


## Scope

* An ETL script that will fetch data from reddit every day.
* A NodeJS backend for our API to connect to the database.
* A ReactJS front-end for users to interact with the API.


## Anticipated Input

* JSON

## Processing

* A diff utility will be used to create low cost archives of content in our database.
* Any user input will be cleaned and standardized in accordance with Reddit's markdown before being stored in our database.
* Searches will be based on time, tags, and votes.


## Anticipated Output

* JSON


## Data Sources

* [Reddit API](https://www.reddit.com/dev/api/) 

## Tech Stack

* ReactJS
* NodeJS
* ExpressJS
* PostgreSQL
* Python

## Error and Exception Handling


### Types/Categories

- Python's Exception
    - Built-in Exception
- Nodejs's Exception
    - Built-in Exception
    - User-Defined Exception
- React's Exception
    - User-Defined Exception
### React Snippet:
- app.js
```js
    render() {
        return (
            <div class="container">
            <ErrorBoundary>
            <Deck style={{width: '20rem', height: '100%'}} title="Type of Charts" subtitle="Chart 1"/>
            <Deck style={{width: '15rem', height: '100%'}} title="Result" subtitle="Bar Chart"/>
            </ErrorBoundary>
            </div>
        )
    }
```
- ErrorBoundary.js
```js
    class ErrorBoundary extends React.Component{
    constructor(props){
        this.state = {hasError:false}
    }

    componentDidCatch(error, info){

        this.state({hasError:true})

        logErrorToMyService(error,info)
    }

    render() {
        if(this.state.hasError) {

            return <h1>Something went wrong.</h1>
        }

        return this.props.children
    }
}

export default ErrorBoundary
```

### Nodejs's REST api Snippet:

- info.controller.js
```js
    create:(req, res)=>{

        if(!req.body){
            sendStatus(res)
            return
        }

        db.conn().promise().query('insert into infos (date, subscribers, active_subscribers, submission, comments, lookupId) values (?,?,?,?,?,?)',
        [req.body.date, req.body.subscribers, 
            req.body.active_subscribers, req.body.submission, 
            req.body.comments, req.body.lookupId],
        (err, results)=>{
            if(err) {sendErr(res, err)}
            else {res.send({result:results})}
        }).then(([rows,fields])=>{
            console.log(rows)
            res.send({result:rows})
        }).catch((err)=>sendErr(res,err))
        .then(()=>db.conn().end())
    },
```

- lookup.controller.js
```js
        create:(req, res)=>{
        
        if(!req.body.name){
            sendStatus(res)
            return
        }

        db.conn().promise().query('insert into lookups (name, abbreviation) values (?,?)',
        [req.body.name, req.body.abbreviation],
        (err, results)=>{
            if(err) {sendErr(res, err)}
            else {res.send({result:results})}
        }).then(([rows,fields])=>{
            console.log(rows)
            res.send({result:rows})
        }).catch((err)=>sendErr(res,err))
        .then(()=>db.conn().end())

    },
```

- status.js
```js
module.exports = {

    sendStatus:(res)=>{

        getMsg = {message:'Content can not be empty!'}
        console.log(yellow(getMsg))
        io.writeToFile(yellow(getMsg),'CORRUPTED')
        res.status(200).send({message:'success'})

        return
    },

    sendErr:(res, err)=>{

        console.log(red.bold(err.message))
        io.writeToFile(red.bold(err.message),'ERROR')
        res.status(200).send({message:'success'})

        return
    },

    sendConfirmation:(res, num)=>{

        num ? (res.send({message:"Operation executed successfully."}))
            : (res.send({message:"Operation execution failed."}))
        
            return
    }
}
```

### JS Description

We choose to handle our exceptions on the server-side and client-side with two parameters, error type and message, which helps us to handle responsibilities within the class. Anytime an error is caught, an error message will will be logged to the console and the detailed information will be stored in the error.log file in the log directory of the server. If the content was not found, the result is empty or any changes failed to update, they will also be logged. We recognize that if an exception handling was revealed to the malicious users, the malicious users will exploit that endpoint vulnerability and the security would be compromised. We will expand on the presentation layer to provide our own generic error codes to inform the user that something has occurred and to deliver the error code to the developer for them to repeat the steps the user made and resolve that vulnerability as soon as possible.


### Python Exception Handling Snippets
- baseSQL.py
```python
username = "root"
password = "students"
hostname = "localhost"
database = "subreddit_db"

try:
    databaseVar = mysql.connector.connect(
        host=hostname,
        user=username,
        password=password,
        database=database
    )
except:
    print("Database Connection Failed")
    exit(2)
```

- get_call.py
```python
try:
    import baseAPI
except:
    print("baseAPI.py file not found. ")
    exit(1)

try:
    import baseSQL
except:
    print("baseSQL.py file not found.")
    exit(1)
try:
    import json
except:
    print("JSON package not found.")
    exit(1)

try:
    import mysql
except:
    print("MySQL package not found.")
    exit(1)

try:
    from datetime import datetime
    import time
except:
    print("Datetime or Time not found.")
    exit(1)
```


### Python Exception Handling Description

There are two exception handling in the python scripts. The python scripts altogether is designed not to fail as the user will not be touching the python script at all. There is an exception handling for database connection test check. If the database connection does not work, the exit signal will be triggered with another exit signal on the base file to help follow along the "thread" where error went wrong. We do have an exception handling that checks to see if the file or python packages exists or not when we attempt to import the files. If the files or python packages do not exist, the message is logged in terminal visible only to the developers. We have determined that it is not necessary for exception handling in python scripts to store the error messages to the error.log for the meantime. 


## Performance and Refactoring

### Performance Layers

We did refactoring our codes for performance reasons by simplifying them to makes functions less verbose. This allows REST API to be optimized and boost performance in callbacks to ensure that there is no long polling.

#### Service Layers
- API calls have been changed to accomodate the Object-Orient Programming standards where the return API call information is easier to access.
 
- SQL queries uses functions with certain information inserted to allow the developer to be able to insert any values necessary and re-use code instead of re-inventing the wheel. 


### Refactoring Layers

#### Application Layer

- before refactored

```js
        //lookup.controller.js

        db.conn().promise().query('insert into lookups (name, abbreviation) values (?,?)',
        [req.body.name, req.body.abbreviation],
        (err, results)=>{
            if(err) {sendErr(res, err)}
            else {res.send({result:results})}
        }).then(([rows,fields])=>{
            console.log(rows)
            res.send({result:rows})
        }).catch((err)=>sendErr(res,err))
        .then(()=>db.conn().end())
```

- after refactored

```js
        //lookup.controller.js

        query.executeQuery('insert into lookups(name, abbreviation) values ($1,$2)',
        [req.body.name,req.body.abbreviation],
        res)
```
- The reason is that I created a query builder that will use as reusable code.

```js
        //querybuilder.js

        module.exports = {

            executeQuery:(query,parameters,res)=>{
                db.conn().connect((err, client, done)=>{
                    if(err) console.log(err)
                    client.query(query,parameters)
                    .then(results=>{
                        res.send({result:results})
                    })
                    .catch(e =>console.log(e.stack))
                })
            }
        }
```
### Refactoring Layers

#### Application Layer
Only have to refactor the db.config.js file from changing MySQL to PostgreSQL. The queries I refactored for performance reasons are what allow minimal changes to the backend. Also installed package pg - a postgresql driver for Nodejs.

##### db.config.js

- MySQL
```js
module.exports = {
    //mysql
    HOST:'localhost',
    USER: 'root',
    PASSWORD: '<Password>',
    DB:'subreddit',
    dialect:'mysql',
    pool:{
        max: 5,
        min: 0,
        acquire: 30000,
        idle: 10000
    }
}
```
- PostgreSQL
```js
module.exports = {
    //postgresql
    HOST:'localhost',
    USER: '<DBUser>',
    PASSWORD: '<Password>',
    DB:'subreddit',
    PORT:5432
}
```

#### Service Layer
##### tables.sql
The file tables.sql covers the initialization of a new database (or schema), it was originally MySQL/MariaDB. Two different changes were made: 
- The creation syntax with MySQL/MariaDB has been refactored to PostgreSQL with ease. Below is the python code snippet to demonstrate this.

MySQL/MariaDB
```sql
CREATE TABLE IF NOT EXISTS `subreddit_db`.`information` (
  `row_id` INT UNSIGNED AUTO_INCREMENT,
  `subreddit_id` INT NOT NULL,
  `date` DATETIME NOT NULL,
  `subscribers` INT NULL DEFAULT NULL,
  `active_subscribers` INT NULL DEFAULT NULL,
  `submission` INT NULL DEFAULT NULL,
  `comments` INT NULL DEFAULT NULL,
  PRIMARY KEY (`row_id`),
  INDEX `fk_information_subreddit_reference_lookup_idx` (`subreddit_id` ASC) VISIBLE,
  CONSTRAINT `fk_information_subreddit_reference_lookup`
    FOREIGN KEY (`subreddit_id`)
    REFERENCES `subreddit_db`.`subreddit_reference_lookup` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION);
```

PostgreSQL
```sql
CREATE TABLE information (
  id SERIAL NOT NULL,
  subreddit_id INT NOT NULL,
  date TIMESTAMP NOT NULL,
  subscribers INT NULL DEFAULT NULL,
  active_subscribers INT NULL DEFAULT NULL,
  submission INT NULL DEFAULT NULL,
  comments INT NULL DEFAULT NULL,
  PRIMARY KEY (id),
  CONSTRAINT fk_lookup
    FOREIGN KEY (subreddit_id)
    REFERENCES lookup (id)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION
);
```

- The arrangements on how the table is dropped and created for a smooth creation of .sql script. Below is the python code snippet to demonstrate this.

MySQL/MariaDB
```sql
DROP SCHEMA IF EXISTS `subreddit_db` ;
CREATE SCHEMA IF NOT EXISTS `subreddit_db` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
USE `subreddit_db` ;
...
DROP TABLE IF EXISTS `subreddit_db`.`subreddit_reference_lookup` ;
CREATE TABLE IF NOT EXISTS `subreddit_db`.`subreddit_reference_lookup` (
  `id` INT NOT NULL,
  `name` VARCHAR(45) NOT NULL,
  `abbreviation` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB
AUTO_INCREMENT = 11
DEFAULT CHARACTER SET = utf8mb4
COLLATE = utf8mb4_0900_ai_ci;
```


PostgreSQL
```sql
DROP DATABASE IF EXISTS subreddit_db ;
CREATE DATABASE subreddit_db;
\c subreddit_db ;
...
DROP TABLE IF EXISTS lookup;
...
CREATE TABLE IF NOT EXISTS lookup (
  id SERIAL NOT NULL,
  name VARCHAR(45) NOT NULL,
  abbreviation VARCHAR(45) NOT NULL,
  PRIMARY KEY (id)
);
```


##### baseSQL.py
The baseSQL.py is a python library for the SQL execution statements. Two different changes were made.  
- A new database python library had to be imported. This was delibrated on and shared with the group double-checking and ensuring it is not an ORM or ORM-related. Below is the python code snippet to demonstrate this. 

MySQL/MariaDB
```python
username = "root"
password = "students"
hostname = "localhost"
database = "subreddit_db"

import mysql.connector

try:
    databaseVar = mysql.connector.connect(
        host=hostname,
        user=username,
        password=password,
        database=database
    )
except:
    print("Database Connection Failed")
    exit(2)
```


PostgreSQL
```python
import psycopg2

try:
    databaseVar = psycopg2.connect("dbname=subreddit_db")
except:
    print("Database Connection Failed")
    exit(2)
```

- The execution syntax with MySQL/MariaDB has been refactored to PostgreSQL with ease. Below is the python code snippet to demonstrate this.

```python
def insertRowInformation(id, date, subscribers, activeSubscribers, submission, comment):
    mycursor = databaseVar.cursor()
    mycursor.execute("INSERT INTO information (subreddit_id, date, subscribers, active_subscribers, submission, comments) VALUES ('" + str(id) + "', '"+ str(date) + "', '" + str(subscribers) + "', '" + str(activeSubscribers) + "', '" + str(submission) + "', '" + str(comment) + "');")
```


## Testing 

### Testing Unit Framework

### Python - Service Layer

#### PyTest

PyTest is a framework that makes it easy to write small tests, yet scales to support complex functional testing for applications and libraries. It is highly recommended by critics to be used for testing and documentation purposes. We have created a sample python script based on the current script that allows us to debug and test the application with the provided values.

- To see PyTest, head to the Service Layer directory and type in `pytest -v test_get_call.py` into the terminal. This will run the python in a testing environment. It will take some time for the test to complete. If the test is successful, it is expected that you will receive a similar output to `100% / 2 passed in 93.93s (0:01:33)`. Otherwise, the output will indicate that the test has failed due to an error or raised exception. The dcode below is the only code block that is added to the service layer that needs to be written to test scheduled_job(). A reminder that the scheduled_job() method grabs the required information from subreddit for our data-driven application.

```py
def testing_op():
    try:
        scheduled_job()
    except:
        print('Dumping data gone wrong.')
        raise SystemExit(0)
def test_mytest():
        testing_op()
```


### Nodejs - Application Layer

#### Mocha & Chai

Mocha is the most popular testing framework for Nodejs installed with npm or even used as CDN in the browser.

- To use Mocha, you have to add a test in the script. Recommend add asterisk * as a wild character to run all javascript files that exist within the test directory.

```json
"scripts":{
    "test": "mocha src/test/*.js --timeout 10000"
}
```

- Run the test command from npm test.

```bash
npm test
```

However, we are testing the Nodejs' REST API to see if it is functioning as we intend it. Most developers would suggest POSTMAN by default, but it is inadequate in providing information when something goes wrong. We will need to use **Chai** packages that allow us to gather more information.

Here the example of how **Chai** api works. By looking in the test js files.

- #### lookup.test.js & info.test.js

```js
//lookup.test.js

//Retrieving all lookup data.
describe('/GET lookups',()=>{
    it('it should GET all the lookups', (done)=>{
        /*
        making request to express's app from src/index.js
        */
        chai.request(server)
        .get('/lookups')
        .end((err,res)=>{

            if(err){
                console.log(err)
            }
            //stating that it should have status of success
            res.should.have.status(200)
            //state what kind of attribute it should be
            res.body.should.be.a('object')
            //stating what each row properties should have
            res.body.result.rows[0].should.have.property('id')
            res.body.result.rows[0].should.have.property('name')
            res.body.result.rows[0].should.have.property('abbreviation')
        done()
        })
    })
})

//info.test.js

//Retrieving all information data.
describe('/GET infos',()=>{
    it('it should GET all the infos', (done)=>{
        /*
        making request to express's app from src/index.js
        */
        chai.request(server)
        .get('/infos')
        .end((err,res)=>{
            if(err){
                console.log(err)
            }
            //stating that it should have status of success
            res.should.have.status(200)
            //state what kind of attribute it should be
            res.body.should.be.a('object')
            //stating what each row properties should have
            res.body.result.rows[0].should.have.property('active_subscribers')
            res.body.result.rows[0].should.have.property('comments')
            res.body.result.rows[0].should.have.property('date')
            res.body.result.rows[0].should.have.property('submission')
            res.body.result.rows[0].should.have.property('subreddit_id')
            res.body.result.rows[0].should.have.property('subscribers')
        done()
        })
    })
})
```
- Inside the function, I stated what properties each row should have. The goal is to ensure that the codes are behaving as we intended.
```js

//lookup.test.js

//This is for inserting lookup data

describe('/POST lookup',()=>{
    it('it should POST a lookup ',(done)=>{
        /*
        generate a mock data to test the function
        */
        let lookup = {
            name: "Testing",
            abbreviation: "tst"
        }
        /*
        making request to express's app from src/index.js
        */
        chai.request(server)
        .post('/lookup')
        .send(lookup)
        .end((err,res)=>{
            //stating that it should have status of success
            res.should.have.status(200)
            //state what kind of attribute it should be
            res.body.should.be.a('object')
            //state that the property should have result
            res.body.should.have.property('result')
        done()
        })
    })
})

//info.test.js

//This is for inserting info data

describe('/POST info', ()=>{
    it('it should POST info',(done)=>{

        /*
        generate a mock data to test the function
        */
        let info = {
            active_subscribers:5,
            comments:3,
            date:'2020-12-07 10:30:39',
            submission:67,
            subreddit_id:2,
            subscribers:9
        }
        /*
        making request to express's app from src/index.js
        */
        chai.request(server)
        .post('/info')
        .send(info)
        .end((err,res)=>{
            if(err){
                console.log(err)
            }
            //stating that it should have status of success
            res.should.have.status(200)
            //state what kind of attribute it should be
            res.body.should.be.a('object')
            //state that the property should have result
            res.body.should.have.property('result')
        done()
        })
    })
})
```
- Inside the function, I stated the properties it should have as result values to state the operation is either successful or fail.

Also, it important to note that info.test.js are the exactly the same as lookup.test.js.



### React - Presentation Layer

#### React-Scripts built-in test with Jest

The React we are using is from Create-React-App, which comes with multiple packages that make the development process more rapid.

The best part about React is that we only need to manually test the components we created. The Jest API is part of the testing process that will automatically test all functions or units within each component.

- **App.test.js**
    - This is the file where all test functions evaluate each component.

    ```js
    test('sidebar',()=>{
        render(<Sidebar/>)
    })

    test('header',()=>{
        render(<Header/>)
    })

    /*The reason for using HTMLCanvasElement is to get the context of charts, 
    otherwise it will result in error & failed status*/
    test('dashboard',()=>{
        HTMLCanvasElement.prototype.getContext = () => { 
            render(<Dashboard/>)
        }
    })
    ``` 
    - This test only need to run one command and one argument
    ```bash
    npm test
    ```
    - Then if all functions within each component doesn't result in any errors. Then the result will look like this.
    ```bash
     PASS  src/App.test.js
  ✓ sidebar (81 ms)
  ✓ header (8 ms)
  ✓ dashboard

    Test Suites: 1 passed, 1 total
    Tests:       3 passed, 3 total
    Snapshots:   0 total
    Time:        6.859 s
    Ran all test suites related to changed files.

    Watch Usage: Press w to show more.
    ```
    


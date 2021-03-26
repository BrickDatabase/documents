```yaml
milestone:
    iteration: 04
    title: "Exception Handling"
    date: "March 26, 2021"
group:
    number: 03
    name: "Europa Report"
    members:
    - "Vincent Cheng"
    - "Amina Mahmood"
    - "Dishant Mishra"
    - "Aaron Wade Parker"
    - "Edward Riley"
```

# Development Book

## Team Members and Roles
- **Vincent Cheng**
    - _Documentarian_
- **Amina Mahmood**
    - _Code Reviewer_
- **Dishant Mishra**
    - _Software Architect_
- **Aaron Wade Parker**
    - _Configuration Manager_
- **Edward Riley**
    - _Team Coordinator_


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
     - **MySQL/MariaDB**
     - **NodeJS**
     - **ExpressJS**
- Front-end 
     -  **React.js** 
     -  **BootStrap**
- GitHub
    - GitHub URL: https://github.com/europa-report 

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

#### Data Layer: **MySQL/MariaDB**
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
![alt text](https://github.com/europa-report/documents/blob/main/layered.png)


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

* __Upvote__ - It is vote used to show agrrement with a comment or a post.

* __Downvote__ - A vote used to show disagreement with a comment or a post.

* __Comment__ - A response to a post or another comment.

* __Post__ - A post constitutes one of the following: A link to an external source, a crosspost which links to another post, rich media, or pain text.


## Current System

Reddit in its current form can be rather infuriating to use. Any edit made to a comment or a post is hidden and the original content cannot be seen again. It is also hard to visualize a lot of user generated data like votes due to Reddit's various obfuscation rules on it's frontend. It's API is also very cluttered and hard to use for the purpose of research.


## Goals

Our overall goal is to make a new facade for Reddit with archival features and a better but with selected subreddit communities, more uniform API. This is how we plan to accomplish it:

* ~~Goal #1: Accumulate and track the numbers of the subreddit communities from the beginning of semester to the end of the semester by each day.~~
* Revised Goal #1: Each member of the group will select the 2 subreddit communities to use for this course.
* Goal #2: Accumulate and track the numbers of the users in the selected subreddit communities from the beginning of semester to the end of the semester by each day.
* Goal #3: Accumulate and track the numbers of the posts in the selected subreddit communities from the beginning of semester to the end of the semester by each day.
* Goal #4: Identify the factors supporting the growth or decline of selected subreddit communities.
* Goal #5: Create a consistent realtime data visualiztion.


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
* MySQL/MariaDB
* Python

## Error and Exception Handling

#### Snippet:

* info.controller.js
```
    create:(req, res)=>{

        if(!req.body){
            sendStatus(res)
            return
        }
        
        Info.create(req.body)
        .then(data =>{
            res.send(data)
        })
        .catch(err =>{
            sendErr(res, err)
        })
    },
```
* lookup.controller.js
```
        .catch(err =>{
            res.status(500).send({
                message:
            err.message || "Some error occurred while creating the Lookup"
            })
        }):
        ()=>{
            res.status(400).send({
                message:"Content can not be empty!"
            })
            return
        }
            sendErr(res,err)
        })
        
    },
```
* status.js
```
module.exports = {

    sendStatus:(res)=>{

        res.status(400).send({
            message:'Content can not be empty!'
        })
    
        return
    },

    sendErr:(res, err)=>{
        res.status(500).send({
            message:
            err.message
        })
        return
    },

    sendConfirmation:(res, num)=>{

        num ? (res.send({message:"Operation executed successfully."}))
            : (res.send({message:"Operation execution failed."}))
        
            return
    }
}
```
Our error handling have two parameters, error type and message. Anytime a controller error is caught, an error message will alert the user at the presentation layer, whether or not if the content was not found, the result is empty or any changes failed to update. 
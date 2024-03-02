# Polls Barckend

## Description

This project is a backend for polls. In it you can create a Poll and users can vote on only one option per poll. This verification is done through a Cookie created by the backend and validated in REST requests

This system has two databases:
- PostgreSQL: users' queries and wishes are saved in this database
- Redis: the counting of votes by choice is saved in this bank. This is done to improve performance due to the features that this service provides for this and other ranking features.

The main functionalities are:
- Create a poll
```javascript
/* body */
{
  title : string,
  options : string[]
}  
```

- get a poll
```javascript
/* return */
{
   id: string,
   title: string,
   options: [
      id: string,
      title: string,
      score: Number
  ]
}  
```
- vote on poll
```javascript
/* '/polls/:pollId/votes' */
{
   pollOptionId: string
}  
```
- Create a Websocket connection
```
/* '/polls/:pollId/results'
With this, the Customer receives messages with total votes for an option in the poll

*/
```
## Tecnologias
- [Node](https://nodejs.org/en)
- [TypeScript](https://www.typescriptlang.org/)
- [Fastapi](https://fastapi.tiangolo.com/)
- [Docker](https://www.docker.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [Redis](https://redis.io/)

## Get Started
### Pré-requisitos
- [Node v. 20.X.X](https://nodejs.org/en/download)
  
### Installing
In the Project root run
```
npm install
```
### Enviroments
- `DATABASE_URL`

### Run application 
- Run in the CMD

```
docker compose up -d # initialize the Databases
npm run dev # started the application
```

# **Project Title**

**API pour gérer l’équipe de football de Nice en ligue 1. Le directeur sportif du club voudrait répertorier en base de données la liste de ses joueurs et le budget de l’équipe afin de gérer au mieux le marché de transfert à venir.**

## **Prerequisites**

- **Java version:** 17 or 21 (17 prefereed)
- **maven version:** apache-maven-3.9.5
- **Packaging:** nicefc-0.0.1-
- **Important:** you need to have right as administrator on your machine for the embedded postgresql dabate to be running locally ( otherwise you will need to use external postgresql server -> update and uncomment Data source parameters on application.properties for connection)
  
## **Getting Started**

Clone the Repository

```bash
git clone https://github.com/younesaa/matawan.git
cd your-repo
```
Build the Project
```bash
mvn clean install (for windows ./mvnw clean install)
```
Run the Application
```bash
mvn spring-boot:run (for windows ./mvnw spring-boot:run)
or
java -jar nice-0.0.1-SNAPSHOT.jar ( jar will be generated adter building the project on target folder -> move to the jar path )
 or
(run it on Intellij by running the main function)
```
The application will be accessible at http://localhost:8080

## **Endpoint 1: /api/teams**


GET: Retrieve a list of teams.

Parameters:

page (default: 0)

size (default: 10)

sortBy (default: "name" , you can sort by acronym and budget as well)

-------------------------------

POST: Add a new team.

(please check fields constraints for teamDto and playerDto)

team : 

   name : non-vide et entre 3 à 30 caractères.
   
   acronym : non-vide et entre 3 à 6 caractères.
   
   budget : non null

player :

   name : non-vide et entre 3 à 30 caractères.
   
   position : non-vide et entre 2 à 3 caractères.

Request Body Example:

json
```bash
{
  "name": "TeamA",
  "acronym": "TA",
  "budget": 100000,
  "players": [
    {"name": "Player1", "position": "ST"},
    {"name": "Player2", "position": "CM"}
  ]
}
```

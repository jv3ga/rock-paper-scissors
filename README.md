# rock-paper-scissors
A full stack Python Challenge

Create a Rock-Paper-Scissors Game using Python >=3.9.7 (with
or without a framework like FastAPI/Django/Masonite/Flask)
and a persistent back-end data store of choice (can be an
RDBMS like PostgreSQL or a NoSQL like Elasticsearch or
Cassandra)
Front end can utilize a web framework like Vue, React, Bootstrap, or Flutter. Jquery
is not recommended.
Solution should result in a pair of docker containers, one for the app and one for
the data store.


The final output must be a zipped file which unzips into
its own folder.
Going into the root of the folder, the application should be executable in the host by simply executing the command
below:

user@host:/Users/user/solution_folder$ docker-compose up –d

This should launch the application and the data store. There should be no need for the user to pass any parameters, nor
manually download/install components/dependencies.
A user should be able to access the application by opening a browser on the host and going to

http://localhost:8000

Solution will be judged on correctness of solution, design decision, and use of best practices. All services should be
launched with initial settings included in the docker-compose/Dockerfile environment settings.
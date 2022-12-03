# REST Api

## Instructions

2. **Source code**
    + Git clone the repository into `$GOPATH/src/paxos` folder in your computer
        ```bash
        git clone https://github.com/Adaickalavan/paxos.git $GOPATH/src/paxos
        ```
        Here, git clone syntax follows the pattern: `git clone <repo> <local folder-name>`.

3. **Run Docker-Compose to Start Application** *(requires internet connectivity)*
    + Navigate to the project folder, i.e. `$GOPATH/src/paxos/RESTApi`.
    + Start the application by running docker-compose.
        ```bash
        docker-compose up
        ```
    + When docker-compose is runs, go to "http://localhost:8080/messages" to interact with the app.
    + When docker-compose is run using Docker Toolbox, go to "http://192.168.99.100:8080/messages" to interact with the app. Here, "192.168.99.100" is the ip address of your docker-machine.

4. **Operation**
    + Several example commands and their expected outputs are given below
        ```bash
        $ curl -X POST -H "Content-Type: application/json" -d '{"message": "foo"}' http://localhost:8080/messages

        {
        "digest": "2c26b46b68ffc68ff99b453c1d30413413422d706483bfa0f98a5e886266e7ae"
        }
        ```
        ```bash
        $ curl http://localhost:8080/messages/2c26b46b68ffc68ff99b453c1d30413413422d706483bfa0f98a5e886266e7ae

        {
        "message": "foo"
        }
        ```
        ```bash
        $ curl http://localhost:8080/messages/aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

        {
        "err_msg": "Message not found"
        }
        ```

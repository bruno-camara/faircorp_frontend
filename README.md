# Building_FrontEnd
FrontEnd project of the building system

## Instructions
Download the repository in a folder, the backend is in the cloud so you don't have to run anything for that. Inside the repository go to the folder cours-dev-web-5-vuejs/demo_code/exercise_base/ and open up a command terminal where you have npm installed (if you don't have node js or npm install please follow the instructions [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm )). Run the following commands:
* npm install
* npm run serve

Wait until the terminal tells you the server is up and running. Then go to the following url: http://localhost:8080, there you will be able to see the webpage. 

## Functions
For the Windows:
* Create a window
* Read the status of the window and its room.
* Update the window status
* Delete a window.

For the Rooms:
* Create a room
* Read the target temperature in a room
* Update the target temperature in a room
* Delete a room

## Run with Docker
To deploy the project locally you can use Docker with the following commands:
- Go to the [exercise_base](./cours-dev-web-5-vuejs/demo_code/exercise_base/) folder and run:

```bash
docker build -t vuejs-cookbook/dockerize-vuejs-app .

docker run -it -p 8080:8080 -e PORT=8080 --rm --name faircorp-frontend vuejs-cookbook/dockerize-vuejs-app
```

## Docker Compose
> Deploy front and backend with a single command

### How to run:
1. Clone both repositories in your root folder

```bash
cd #goes to your root folder
git clone git@github.com:bruno-camara/faircorp.git
git clone git@github.com:bruno-camara/faircorp_frontend.git
```

2. Enter in the frontend directory

```bash
cd ~/faircorp_frontend/cours-dev-web-5-vuejs/demo_code/exercise_base/
```

3. Run docker compose

```bash
docker compose up
```
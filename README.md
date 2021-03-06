# MERN Stack

Learn how to create a full-stack web app using the MERN stack. The MERN stack is MongoDB, Express, React, and Node.js.

Also, learn how to use MongoDB Realm to convert the backend to serverless and host the entire thing for free in the cloud. You will even learn how to host the React frontend for free.

✏️ Course developed by Beau Carnes.

Youtube link - [here!](https://youtu.be/mrHNSanmqQ4)

## Setup

- Create MongoDB Cluster0 with sample data loaded
- Create project folder
- Initial node in backend folder

  ```bash
  mkdir backend
  cd backend

  npm init -y
  npm install express cors mongodb dotenv
  npm install -g nodemon
  ```

- Add "type": "module", to backend/package.json
- Create [backend/server.js](backend/server.js)
- Create backend/.env
  - go to MongoDB Cluster0, click Connect application (Node.js)
  - copy connection string to RESTREVIEWS_DB_URI in .env
  - replace `<password>` and `database-name`
  - add RESTREVIEWS_NS=`database-name`
  - add PORT=5000
- Create [backend/index.js](backend/index.js)
- Create [backend/api/restaurants.route.js](backend/api/restaurants.route.js)
- Run (test) server

  ```bash
  # in backend folder
  nodemon server
  ```

## Connect Database

- Create [backend/dao/restaurantsDAO.js](backend/dao/restaurantsDAO.js)
- Update [backend/index.js](backend/index.js)
  - add import RestaurantsDAO from "./dao/restaurantsDAO.js"
  - add await RestaurantsDAO.injectDB(client)
- Update [backend/api/restaurants.route.js](backend/api/restaurants.route.js)
  - add import RestaurantsCtrl from "./restaurants.controller.js"
  - replace router.route("/") to get RestaurantsCtrl.apiGetRestaurants
- Create [backend/api/restaurants.controller.js](backend/api/restaurants.controller.js)

## Add new Index to MongoDB database

- Open Cluster > Collection > select database (sample_restaurants.restaurants)
- Click Indexes (toolbar)
- Click create index (top-right green btn)
- replace Fields to `{"name": "text"}` (we wanna add fields "name" for api filter)
- click confirm

## Review Feature

- Update [backend/api/restaurants.route.js](backend/api/restaurants.route.js)
  - add import ReviewsCtrl from "./reviews.controller.js"
  - add route("/review") [post, put, delete]
- Create [backend/api/reviews.controller.js](backend/api/reviews.controller.js)
- Create [backend/dao/reviewsDAO.js](backend/dao/reviewsDAO.js)

## Restaurants Frontend

- Update
  - [backend/api/restaurants.route.js](backend/api/restaurants.route.js)
  - [backend/dao/restaurantsDAO.js](backend/dao/restaurantsDAO.js)
  - [backend/api/restaurants.controller.js](backend/api/restaurants.controller.js)
- Initial frontend

  ```bash
  # create/initial react in new folder called frontend
  npx create-react-app frontend

  npm install bootstrap
  npm install react-router-dom
  npm install axios

  # in frontend folder
  # run server
  npm start
  # build
  npm run build
  ```

- Update [frontend](frontend)

# MERN Stack

Learn how to create a full-stack web app using the MERN stack. The MERN stack is MongoDB, Express, React, and Node.js.

Also, learn how to use MongoDB Realm to convert the backend to serverless and host the entire thing for free in the cloud. You will even learn how to host the React frontend for free.

✏️ Course developed by Beau Carnes.

Youtube link - [here!](https://youtu.be/mrHNSanmqQ4)

## Set up

- Set up MongoDB Cluster0 with sample data loaded
- Set up project folder
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

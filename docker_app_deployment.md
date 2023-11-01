## Deploying App through Docker

Setting up Sparta Test App through Docker container 

### Step 1: Creating dockerfile 
1. Create a Directory with the app folder and a dockerfile
2. Go inside the app folder, where `app.js` exists
3. Create a `Dockerfile` by running `nano Dockerfile`
3. Inside the Docker file enter:

```
FROM node:latest
WORKDIR /app
COPY . .
RUN npm install
EXPOSE 3000
cmd [ "node", "app.js" ]

```
### Step 2: Build The Image

`docker build -t sparta-app .`

Check if image has been created using `docker images`

### Step 3: Build The Container

The image will run on port 3000

`docker run -d -p 3000:3000 sparta-app`

### Step 4: Check If It Is Working

Go onto your web browser and type in `localhost:3000`

### Step 5: Create Tag 

`docker tag sparta-app shaluomehra/sparta-app`

### Step 6: Push To Dockerhub

`docker push wafamohbubul/sparta-app`
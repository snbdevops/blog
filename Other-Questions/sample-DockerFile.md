### Sample Dockerfile

```dockerfile
# 1. Specify the base image
FROM node:18-alpine

# 2. Set the working directory inside the container
WORKDIR /app

# 3. Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# 4. Install the dependencies
RUN npm install --production

# 5. Copy the source code to the container
COPY . .

# 6. Expose the port the app will run on
EXPOSE 3000

# 7. Define environment variables
ENV NODE_ENV=production

# 8. Command to run the application
CMD ["npm", "start"]
```

### Detailed Explanation of Each Component

#### 1. `FROM`
```dockerfile
FROM node:18-alpine
```
- This specifies the base image on which the Docker image is built. In this case, we’re using the official Node.js image with the Alpine Linux distribution for its small size.
- The base image contains all the dependencies required to run a Node.js application. You can replace this with any other base image depending on your application (e.g., Python, Java, etc.).

#### 2. `WORKDIR`
```dockerfile
WORKDIR /app
```
- This sets the working directory inside the container where all subsequent commands will be run. 
- If the directory doesn't exist, Docker will create it. It helps keep the file paths clean and manageable.

#### 3. `COPY` (Copying files)
```dockerfile
COPY package*.json ./
```
- `COPY` is used to copy files from your host machine into the Docker image. 
- Here, we are copying the `package.json` and `package-lock.json` files into the current working directory (`/app`) inside the container. These files are necessary for installing Node.js dependencies.

#### 4. `RUN`
```dockerfile
RUN npm install --production
```
- The `RUN` command executes any commands in a new layer on top of the current image. Here, it runs the `npm install` command to install the Node.js dependencies listed in the `package.json` file.
- `--production` ensures that only production dependencies are installed, excluding development dependencies.
  
#### 5. `COPY` (Copying source code)
```dockerfile
COPY . .
```
- This `COPY` command copies all files from the current directory on your host machine to the current working directory (`/app`) inside the container.
- It transfers your source code into the Docker image, making it ready for use.

#### 6. `EXPOSE`
```dockerfile
EXPOSE 3000
```
- `EXPOSE` informs Docker that the container listens on the specified port at runtime. 
- In this case, the application is expected to run on port `3000`. While `EXPOSE` doesn't actually publish the port to the host, it's more for documentation purposes. You need to map ports when running the container (`docker run -p`).

#### 7. `ENV`
```dockerfile
ENV NODE_ENV=production
```
- The `ENV` command sets environment variables inside the container.
- Here, the environment variable `NODE_ENV` is set to `production`, which many frameworks and libraries use to optimize their behavior for production environments.

#### 8. `CMD`
```dockerfile
CMD ["npm", "start"]
```
- The `CMD` instruction specifies the default command to run when a container is started. It doesn’t execute during the image build; it runs when the container is started.
- Here, it runs `npm start`, which will start the Node.js application according to the command defined in the `package.json` file.
  
- If you want to override this command, you can pass a different command while starting the container, for example: `docker run <image> node app.js`.

### Dockerfile Components Summary:

1. **FROM**: Sets the base image to start with, defining the operating system and environment.
2. **WORKDIR**: Sets the working directory inside the container where commands are executed.
3. **COPY**: Copies files from the host machine into the container image.
4. **RUN**: Executes a command during the build process, creating a new layer in the Docker image.
5. **EXPOSE**: Documents the port the container listens on (not actually binding the port).
6. **ENV**: Sets environment variables inside the container.
7. **CMD**: Specifies the command to run when the container starts (runtime).

By defining these components properly in a Dockerfile, you can build a consistent, portable, and isolated environment for running your application.

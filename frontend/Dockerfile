# # Use a lightweight Node.js 22.3.0 image as the base image
# FROM node:22.3.0

# # Set the working directory inside the container to /todo-frontend/
# WORKDIR /todo-frontend/

# # Copy package.json and package-lock.json
# COPY todo-frontend/package*.json ./

# # Copy the public directory from the host to the container
# COPY todo-frontend/public/ /todo-frontend/public

# # Copy the src directory from the host to the container
# COPY todo-frontend/src/ /todo-frontend/src

# # Copy the package.json file from the host to the container
# COPY todo-frontend/package.json /todo-frontend/

# # Install axios (if not included in package.json)
# RUN npm install axios

# # Install the npm dependencies defined in the package.json file
# RUN npm install

# RUN npm start -a 0.0.0.0 --port 80

# # # Build the React application
# # RUN npm run build

# # # Install a simple HTTP server to serve the static files
# # RUN npm install -g serve

# # # Command to run when the container starts
# # CMD ["serve", "-l", "80", "-s", "build"]



# Use a lightweight Node.js 22.3.0 image as the base image
FROM node:22.3.0

# Set the working directory inside the container to /todo-frontend/
WORKDIR /todo-frontend/

# Copy the public directory from the host to the container
COPY todo-frontend/public/ /todo-frontend/public

# Copy the src directory from the host to the container
COPY todo-frontend/src/ /todo-frontend/src

# Copy the package.json file from the host to the container
COPY todo-frontend/package.json /todo-frontend/

RUN npm install

CMD ["npm", "start"]
FROM node:22

WORKDIR /app

# Copying the package.json and package-lock.json.
COPY package*.json .

# Install the dependencies(equivalent to npm i).
RUN npm ci 

# Copy the source code of our app.
COPY src/index.js index.js

# Expose the application port(sort of allocation of port inside container, not mapping).
EXPOSE 3000

# Start the app.
CMD [ "node", "index.js" ]
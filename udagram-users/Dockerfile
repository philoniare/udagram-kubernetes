# Use NodeJS base image
FROM node:13

# Create app directory in Docker
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY package*.json ./

# Install dependencies in Docker
RUN apt update && apt-get install -y p7zip \
    p7zip-full \
    zip


# Copy app from local environment into the Docker image
COPY . .

RUN npm install

RUN npm run build

# Set the API’s port number
EXPOSE 8081

# Define Docker’s behavior when the image is run
CMD ["node", "www/server.js"]

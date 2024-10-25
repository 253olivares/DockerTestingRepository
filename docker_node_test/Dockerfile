FROM node:23

# we are creating a directory
WORKDIR /app

# we are telling docker we want to copy our source documents from package json which has all our dependencies we need
# and copy that file to our root container
COPY package*.json ./

# we are telling docker what command we want to run
# At this point we want to install our dependencies
RUN npm install

# we want to now copy our source code next
# using two dots tells docker we want to copy all the code in our folder over to our container folder
# If we have a dockerignore file docker will ignore any files or folders listed in the .ignore
COPY . .

# creating enviromental variables for our container
ENV PORT=8080

# this is the port our container will listen to and forward to the user when trying to interact with the container.
# our entry point
EXPOSE 8080

# this executes our applications
# normally will be your cli script you run the application
CMD [ "node", "src/" ]

# That is everything we have a full set of instructions now that tells our container to copy a image from node
# copy our package json file to the container and install our dependencies

# Then copy our source file and run our start script

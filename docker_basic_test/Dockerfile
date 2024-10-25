# Each dockerfile executes instructions. You can see instructions that we execute below
# From will usually be our first instruction. This points to a base image
# FROM baseImage

# our from is usually imageDistro : Image verion
FROM  debian:bullseye-20190708

# creates a source directory and cds into it 
# we are telling docker where we want to start
WORKDIR /user/src

# Any command after is executes within this file directory

# Run runs our cli 
# here we would begin running scripts

# bonus note && is use to string commands in the cli
# \ is used to continue our script on the next line
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# for this script we are creating a user who will not be the rootuser
# we want to do this for security purposes
RUN useradd --create-home appuser
# tell our docker file to use our new user created
# we want to do this to avoid running any additional script as the root user
USER appuser    

# Copy copys all our source documents
# we can specify speific files names or just use . to copy everything on our source foulder where the document sits

# the second . tells our application to copy all our documents that we specified into our container source from workdir
# additional note: if we have a dockeringore then our docker copy will not copy anything listed in the ignore file
COPY app.py .

# Creates enviroment variables
# often time we do this to hide api keys for our application
# in normal usecases we would begin listing our api keys
ENV API_KEY=hi_mom

# lets us set a port we want to use to expose our container
EXPOSE 8080

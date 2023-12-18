
# ServiceNowMidDocker
A docker image to build a Linux MID Server for ServiceNow using the official Docker files provided by ServiceNow. 

# Purpose
This is mainly to serve as a CI/CD repository for getting the latest version. I'll update the Docker file as needed. Release at this time is Vancouver

# To use

    #Set mid server variables
    export instance='https://dev1234.service-now.com'
    export midservername='my-docker-midserver'
    export miduser='miduser'
    export midpassword='midpass'
    
    sudo docker run -d \
    --name $midservername \
    --env MID_INSTANCE_URL=$instance \
    --env MID_SERVER_NAME=$midservername \
    --env MID_INSTANCE_USERNAME=$miduser \
    --env MID_INSTANCE_PASSWORD=$midpassword \
    ghcr.io/mtcoffee/servicenowmiddocker:latest
    
    #to tail the mid server logs
    sudo docker logs $midservername --follow
    
    #if you need to to tear it down
    #sudo docker rm $midservername -f

#First, refernce the image in the docker file
FROM python:3.8-buster
#Specify the maintainer, the guy that is supposed 
LABEL maintainer="Harrys Kouam"
#Copy the source code
COPY requirements.txt student_age.py /
#Install the prerequisites; The API uses Flask and requires additional packages
RUN apt update -y && apt install -y python3-dev libsasl2-dev libldap2-dev libssl-dev
RUN pip3 install -r /requirements.txt
#This creates a shared folder inside the container. t lets you store files (like logs or data)
VOLUME ["/data"]
#Expose the listening requests on port 5000
EXPOSE 5000
#Tells the container to run the Python script called student_age.py when it starts
CMD ["python3", "student_age.py"]
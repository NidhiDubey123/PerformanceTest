#Base image
from alpine:3.9

#Creating a custom image with following dependencies


Run apk update \
		&& apk add ca-certificates \
		&& update-ca-certificates \
		&& apk add --update openjdk8-jre tzdata curl unzip bash tar\
		&& mkdir -p /temp/dependencies \
		&& curl -L --silent http://mirror.ox.ac.uk/sites/rsync.apache.org//jmeter/binaries/apache-jmeter-5.1.1.tgz > /temp/dependencies/apache-jmeter-5.1.1.tgz \
		&& mkdir -p /opt \
		&& tar -xzf /temp/dependencies/apache-jmeter-5.1.1.tgz -C /opt \
		&& rm -rf /temp/dependencies

#Copying the files 
COPY ./ ./
		
CMD ["echo","HELLO From Jmeter Controller!!!!"]
#waiting for few mins for running container 


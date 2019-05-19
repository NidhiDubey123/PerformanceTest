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


Run  sh  ./opt/apache-jmeter-5.1.1/bin/jmeter.sh \
    -n -X \
    -Jclient.rmi.localport=7000 \
    -R jmeter-lg1,jmeter-lg2 \
    -t /GitHubJmeterTest.jmx.jmx \
    -l /result.jtl \
    -j /jmeter.log
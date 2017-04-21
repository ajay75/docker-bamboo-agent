FROM davidcaste/debian-oracle-java:jdk8
MAINTAINER Amit Shlomovits (amut00@gmail.com)

# Copy files
COPY /root /root

# TODO - Do we need it? (it’s done on official image).
RUN mkdir -p /root/bamboo-agent-home/bin

# Add exec permission to required files.
RUN chmod +x /root/bamboo-update-capability.sh && \ 
    chmod +x /root/run-agent.sh

# Run Bamboo Agent setup script
CMD /root/run-agent.sh
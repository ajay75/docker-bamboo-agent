FROM atlassian/bamboo-base-agent
MAINTAINER Amit Shlomovits <amut00@gmail.com>

# Update apt-get
RUN apt-get update

# Remove OpenJDK 7
RUN apt-get autoremove -y openjdk-7-jdk && \
    apt-get purge -y openjdk*

# Install OpenJDK 8
RUN apt-get install -y software-properties-common && \
    add-apt-repository ppa:openjdk-r/ppa && \
    apt-get update && \
    apt-get install -y openjdk-8-jdk-headless && \
    apt-get remove -y --auto-remove software-properties-common && \
    apt-get purge -y --auto-remove software-properties-common
ENV JAVA_HOME /usr/lib/jvm/java-1.8-openjdk
ENV PATH $PATH:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin

# Install Node
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - && \
    apt-get install -y nodejs

# Do npm stuff
RUN npm config set prefix /usr/local && \
    npm install -g npm && \
    npm install -g gulp && \
    npm install -g typescript

# Run Bamboo Agent setup script
CMD /root/run-agent.sh

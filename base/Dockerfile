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

# Run Bamboo Agent setup script
CMD /root/run-agent.sh
FROM davidcaste/debian-oracle-java:jdk8
MAINTAINER Amit Shlomovits (amut00@gmail.com)

# Install Chromium and make it headless & curl, sudo for later usage
RUN apt-get update && apt-get install -y curl xvfb chromium sudo 
ADD xvfb-chromium /usr/bin/xvfb-chromium
RUN ln -s /usr/bin/xvfb-chromium /usr/bin/google-chrome && \
    ln -s /usr/bin/xvfb-chromium /usr/bin/chromium-browser

# Install zip, unzip, nodejs & git
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - && \
    apt-get -y install zip unzip nodejs git

# Do npm stuff
RUN npm config set prefix /usr/local && \
    npm install -g npm && \
    npm install -g gulp && \
    npm install -g typescript

# Install yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && \
    apt-get update && apt-get install -y yarn

# Copy files
COPY /root /root

# TODO - Do we need it? (it’s done on official image).
RUN mkdir -p /root/bamboo-agent-home/bin

# Add exec permission to required files.
RUN chmod +x /root/bamboo-update-capability.sh && \ 
    chmod +x /root/run-agent.sh

# Run Bamboo Agent setup script
CMD /root/run-agent.sh
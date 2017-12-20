[![](https://images.microbadger.com/badges/image/amitshlo/bamboo-agent.svg)](https://microbadger.com/images/amitshlo/bamboo-agent "Get your own image badge on microbadger.com")[![](https://images.microbadger.com/badges/version/amitshlo/bamboo-agent.svg)](https://microbadger.com/images/amitshlo/bamboo-agent "Get your own version badge on microbadger.com")

# Bamboo Agent (Docker) -  Includes Node.JS, Java and Docker!
An agent image for Atlassian Bamboo, built on Linux Alpine (only 126 MB!) or Linux Debian.

Plus Node.js and Java Bamboo Agent capable of running tests on Chromium (and a lot of other stuff such as Docker)!

The image is build the same way as the offical one, but is based on Alpine or Debian and has Java 8 (or in other words - it works).


Tags:

1. [node-java, latest - Image with Java and Node.js (TypeScript, Mocha, Forever and Gulp pre-installed), Maven, Yarn, Git, Zip, Unzip and Chromium (for running tests with karma etc.) Installed.](node-java/Dockerfile)
2. [base - Alpine based base image with nothing installed but Oracle Java 8.](base/Dockerfile)
3. [base-debian - Same as base, only based on Linux Debian (if you need stuff that don't work on Alpine).](base-debian/Dockerfile)

Run with the following command:

    docker run -e HOME=/root/ -e BAMBOO_SERVER=http://hostname:port/bamboo -i -t amitshlo/bamboo-agent:latest

It's recommended to mount the build folder (/root/bamboo-agent-home/xml-data/build-dir) so the container won't grow.

You should also mount the cache folders (Yarn, npm etc.) for the same reason.

If you plan on using Docker - Bind the docker socket from the container (-v /var/run/docker.sock:/var/run/docker.sock)! For more info - [here](http://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/).

Customize it:

1. Use amitshlo/bamboo-agent:base as base image.
2. Install what you need.
3. (Optional: Open a pull request so others could enjoy it too).
4. Build your image!

Enjoy!

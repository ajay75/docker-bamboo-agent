# bamboo-agent
An agent image for Atlassian Bamboo. Based on the official one, but works!

This image is pretty simple - take the Offical image, remove OpenJDK 7 (which doesn't work anymore) and add OpenJDK 8.

Tags:

1. latest, base - Base image with nothing installed but OpenJDK 8.
2. node - Image with Node.js, TypeScript and Gulp Installed.

Run with the following command:

    docker run -e HOME=/root/ -e BAMBOO_SERVER=http://hostname:port/bamboo -i -t amitshlo/bamboo-agent:latest

Customize it:

1. Use amitshlo/bamboo-agent:base as base image.
2. Install what you need with apt-get.
3. Add CMD /root/run-agent.sh' at the end of your Dockerfile.
4. (Optional: Open a pull request so others could enjoy it too).
5. Build your image!

Enjoy!


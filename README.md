[![](https://images.microbadger.com/badges/image/amitshlo/bamboo-agent.svg)](https://microbadger.com/images/amitshlo/bamboo-agent "Get your own image badge on microbadger.com")[![](https://images.microbadger.com/badges/version/amitshlo/bamboo-agent.svg)](https://microbadger.com/images/amitshlo/bamboo-agent "Get your own version badge on microbadger.com")

# bamboo-agent
An agent image for Atlassian Bamboo, built on Linux Alpine (only 126 MB!).

The image is build the same way as the offical one, but is based on Alpine and has Java 8 (or in other words - it works).


Tags:

1. latest, base - Base image with nothing installed but Oracle Java 8.
2. node - Image with Node.js, TypeScript and Gulp Installed.

Run with the following command:

    docker run -e HOME=/root/ -e BAMBOO_SERVER=http://hostname:port/bamboo -i -t amitshlo/bamboo-agent:latest


Customize it:

1. Use amitshlo/bamboo-agent:base as base image.
2. Install what you need with apk.
3. (Optional: Open a pull request so others could enjoy it too).
4. Build your image!

Enjoy!


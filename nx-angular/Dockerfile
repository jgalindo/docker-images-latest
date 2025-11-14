# Node.js current, active, and maintenance LTS versions
# https://nodejs.org/en/about/releases/
# current LTS: 24.x
# active LTS: 22.x
# maintenance LTS: 20.x
# Next LTS: 26.x
# Node.js 26 LTS will begin mid April 2026
# Update this file when a new LTS version is released
FROM node:24

# nx is v21 at the time of writing
# I'm going to tag this image with the version of nx
# Update: new nx version v22
RUN npm add --global nx

# Angular is v20 at the time of writing
RUN npm install -g @angular/cli

# Install Chromium for headless testing
RUN apt-get update && \
    apt-get install -y chromium --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the CHROME_BIN environment variable for Karma
ENV CHROME_BIN=/usr/bin/chromium

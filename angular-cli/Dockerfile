# Node.js current, active, and maintenance LTS versions
# https://nodejs.org/en/about/releases/
# current LTS: 24.x
# active LTS: 22.x
# maintenance LTS: 20.x
# Next LTS: 26.x
# Node.js 26 LTS will begin mid April 2026
# Update this file when a new LTS version is released
FROM node:24

# Angular is v20 at the time of writing
RUN npm install -g @angular/cli

# Install Chromium for headless testing
RUN apt-get update && \
    apt-get install -y chromium --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set the CHROME_BIN environment variable for Karma
ENV CHROME_BIN=/usr/bin/chromium
 
# Ensure the app directory exists, is owned by the `node` user, and switch to that user
WORKDIR /app
RUN mkdir -p /app && chown -R node:node /app
USER node

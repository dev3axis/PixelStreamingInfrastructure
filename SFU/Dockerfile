# Use the current Long Term Support (LTS) version of Node.js
FROM node:lts as BUILDER

# Copy the signalling server source code from the build context
COPY . /opt/build

# Install the dependencies for the signalling server
WORKDIR /opt/build
RUN npm install .

FROM gcr.io/distroless/nodejs
COPY --from=BUILDER /opt/build /opt/SFU
WORKDIR /opt/SFU
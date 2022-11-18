# Use the current Long Term Support (LTS) version of Node.js
FROM node:lts as BUILDER

# Copy the signalling server source code from the build context
COPY . /opt/build

# Install the dependencies for the signalling server
WORKDIR /opt/build
RUN npm install .

FROM gcr.io/distroless/nodejs
COPY --from=BUILDER /opt/build /opt/matchmaker

WORKDIR /opt/matchmaker

EXPOSE 90
EXPOSE 9999

LABEL org.opencontainers.image.source = "https://github.com/dev3axis/PixelStreamingInfrastructure"
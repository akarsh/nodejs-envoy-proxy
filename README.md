# Node.js Envoy Proxy

This project demonstrates how to use Envoy Proxy with a Node.js web server inside a Docker container.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
   - [IP_ADDRESS](#ip_address)
- [License](#license)

## Introduction

The Node.js Envoy Proxy project showcases the integration of Envoy Proxy with a Node.js web server running in a Docker container. Envoy Proxy is used as a sidecar proxy to handle incoming traffic and forward requests to the Node.js server. This setup provides features like load balancing, routing, and service discovery.

## Features

- Integration of Envoy Proxy with Node.js web server
- Dockerized deployment for easy setup and scalability
- Load balancing and routing capabilities provided by Envoy Proxy

## Installation

To run the Node.js Envoy Proxy project locally, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/akarsh/nodejs-envoy-proxy.git
   cd nodejs-envoy-proxy
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Build the Docker images:

   ```bash
   docker-compose build
   ```

## Usage

After installation, you can run the project using Docker Compose:

```bash
docker-compose up
```

Once the containers are up and running, you can access the Node.js web server via http://localhost:3000 and the Envoy Proxy at http://localhost:8080.

### IP_ADDRESS
To replace <IP_ADDRESS> with the IP address of your host machine, you need to determine the IP address that your Envoy Proxy container should use to reach the Node.js server running on the host.

Here's how you can find the IP address of your host machine:

1. macOS

If you're using macOS, you can use the ifconfig command to find the IP address of your network interface. Open a terminal and run:
```bash
ifconfig | grep "inet "
```
Look for the IP address associated with your network interface (usually en0 or en1).

2. Linux

If you're using Linux, you can use the ip addr show command to find the IP address of your network interface. Open a terminal and run:
```bash
ip addr show
```
Look for the IP address associated with your network interface (usually eth0 or wlan0).

3. Windows

If you're using Windows, you can use the ipconfig command to find the IP address of your network interface. Open a command prompt and run:
```bash
ipconfig
```
Look for the IPv4 address associated with your network interface.

Once you have the IP address, replace <IP_ADDRESS> in your Envoy configuration file with the IP address you found. Ensure that your Node.js server is listening on the same IP address. After making the changes, restart your Envoy Proxy server, and it should now be able to communicate with your Node.js server using the correct IP address.


## License

This project is licensed under the GPL-3.0 License. See the [LICENSE](LICENSE) file for details.

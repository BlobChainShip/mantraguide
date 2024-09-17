# Mantra operator node

## Step 1: Update Your Server

First, ensure your server is up to date by running the following commands:

```
sudo apt update && sudo apt upgrade -y
```
## Step 2: Install Required Dependencies

Install the necessary packages:

```
sudo apt install curl jq git build-essential -y
```
## Step 3: Install Docker

Mantra nodes run inside Docker containers. To install Docker, execute:

```
sudo apt install docker.io -y
```
Then, start and enable Docker:

```
sudo systemctl start docker
sudo systemctl enable docker
```
## Step 4: Install Docker Compose

Docker Compose is used to manage multi-container Docker applications. Install it using the following commands:

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
To verify the installation:

```
docker-compose --version
```
## Step 5: Clone the Mantra Chain Node Repository

Clone the Mantra Chain node repository from GitHub:

```
git clone https://github.com/MantraChain/MantraChain.git
cd MantraChain
```
## Step 6: Set Up Environment Variables

Mantra Chain requires certain environment variables to be set up. Copy the example environment file and edit it to your needs:

```
cp .env.example .env
nano .env
```
Edit the .env file with your preferred settings. Common values include the node name and port configurations.

## Step 7: Run the Node with Docker Compose

To launch your node, use Docker Compose to bring up the services:

```
docker-compose up -d
```
This command will run the Mantra Chain node in the background.

## Step 8: Check the Node Logs

To verify that your node is running correctly, view the logs:

```
docker-compose logs -f
```
You should see logs that indicate the node is syncing with the blockchain.

## Step 9: Keep Node Updated

Mantra Chain nodes may require periodic updates. To update your node, pull the latest changes from the repository and restart the node:

```
git pull
docker-compose down
docker-compose up -d
```
Useful Commands

Start the Node:

```
docker-compose up -d
```
Stop the Node:

```
docker-compose down
```
Check Logs:

```
docker-compose logs -f
```
Restart the Node:

```
docker-compose restart
```
Final Notes:
Ensure that your node stays connected to the network.
Consider setting up monitoring or alerts to keep track of your node’s health and performance.

# Running an Ethereum Node

## Prerequisite
1. An EC2 Machine with 8vCPU and 24GB RAM
2. Two EBS volumes
   - For Geth 1TB
   - For Nimbus 500Gb
3. Docker and docker-compose should be installed and running
4. Required ports to open
   ```
   Geth Ports:
   30303 (TCP and UDP): This is the default port for Ethereum's peer-to-peer communication.
   8545: JSON-RPC HTTP service port.
   8546: WebSocket service port.
   6060: Metrics port used by Prometheus.
   ```
   ```
   Nimbus Ports:

   9000 (TCP and UDP): For peer-to-peer communication in Nimbus.
   5052: REST API port.
   8008: Metrics port for Nimbus, also used by Prometheus.
   ```
   ```
   Prometheus ports:
   9090 
   ```

## Step 1: Preparing the infrastructure 
1. Attach the EBS volumes to the instance
2. Create a new folder called `ethereum-node`
3. Format the disks with XFS fs
   - `mkfs -t xfs /device/name`
4. Create folders for Geth and Nimbus inside `/ethereum-node`
   - `mkdir geth`
   - `mkdir nimbus`
5. Mount the disks onto the above folders
   - `mount /dev/nvme... /ethereum-node/geth`
   - `mount /dev/nvme... /ethereum-node/nimbus`

Step 2: Running the node
1. Clone this repo
2. Run the following commands
   `docker-compose up -d`  (this will create the nimbus and the geth node + will run promethues)



  

# Running an Ethereum Node

## Prerequisite
1. An EC2 Machine with 8vCPU and 24GB RAM
2. Two EBS volumes
   - For Geth 1TB
   - For Nimbus 500Gb
3. Docker and docker-compose should be installed and running

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



  

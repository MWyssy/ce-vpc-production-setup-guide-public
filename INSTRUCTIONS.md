# CREATE A NETWORK

Create the VPC

- Log into AWS and go to the VPC section
- Create a new VPC and set the CIDR to 172.31.0.0/16 - This sets the total number of IPs available to the maximum amount avaialable.

Set up the Sub-Nets

- Click on subnets
- Create 6 new subnets, one public and one private for each availability zone - This helps to make the VPC more robust, as if one availability zone goes down, two are still available. We only need 6 subnets as we are only making the VPC for one region, the UK, which only has 3 availability zones.
- Set the CIDR of each subnet to 172.31.0.0/24, 172.31.1.0/24 etc - The subnet CID ranges being unique means that there will be no crossover of IPs across any of the subnets. Setting the range to /24 portions limits each subnet to 256 nodes, meaning there will be no overlaps.

Set up an internet Gateway

- Go to the internet gateway tab, and click 'create new gateway'
- Associate that gateway with the new VPC. - This is the first step in connecting the VPC to the internet. The Gateway acts as a door that allows internet traffic in and out.

Set up a Route Table for the public subnets

- Go to the Route Table tab, and click 'create new route table'
- Associate this route table with the new VPC
- Add a route to your internet gateway by using the CIDR of 0.0.0.0/0 - This connects the route table to the gateway, and so allows you to determine which subnets can have direct public access to the internet.
- Associate your public subnets with the route table - Here you can determine which of the subnets are public.

Set up a Nat Gateways for each of the private subnets to access the internet through

- Go to the NAT gateways tab, and create a new NAT gateway, assign this to public-1, then repeat for the other two public subnets.
- The NAT-gateway's job is to allow a private subnet to connect to the internet without being accessible by outside requests.

Set up Route Tables to connect the private subnets to their respective NAT gateways

- Go to the Route Table tab, and click 'create new route table'
- Associate this to the same VPC
- Add a route to the Nat-Gateway for zone 1
- Associate the zone 1 private subnet to this route table
- Repeat for the other two zones
- The aim of this is to associate each private subnet with a NAT-Gateway hosted by it's respective public subnet, which is connected to the internet via the main route table.

# DELETE THE NETWORK

- First, delete all three NAT-Gateways
- Then dissociate the subnets from each route table
- Which will then allow you to delete the route tables
- Next, detach internet gateway
- And finally, delete the VPC

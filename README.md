# AWS-CLIENT-VPN-VPC-PEERING-RDS-CloudFormation

This project is a solution for a challenge to demonstrate advanced AWS infrastructure provisioning using CloudFormation. The goal is to create a multi-VPC architecture with an RDS Aurora MySQL Serverless database with client VPN connectivity. This project shows how to provision a development and a shared system network, establish VPC peering between them, deploy an RDS database in the development system, and set up a VPN client in the shared system and finally able to connect the RDS database from the client machine through the VPN. This project enables secure and scalable access to cloud resources across different VPCs.

## Project Components

- `shared-system.yaml`: Template for creating the shared system VPC with public and private subnets.
- `dev-system.yaml`: Template for creating the development system VPC with public and private subnets.
- `vpc-peering.yaml`: Template for establishing VPC peering between the shared and development system networks.
- `rds-aurora-db-cluster.yaml`: Template for deploying an RDS Aurora MySQL Serverless database in the development system network.

![CloudFormation designer view of RDS database template](rds-db-cf-designer.png)

## Progress

- [x] **VPC Setup**: Successfully created VPCs for both shared and development systems, each with isolated subnets.
- [x] **VPC Peering**: Established a peering connection between the VPCs, facilitating secure inter-VPC communication.
- [x] **RDS Deployment**: Succesfully deployed Aurora Serverless MySQL RDS database within the development VPC, and also integrated AWS secrets manager for passwords.
- [ ] AWS VPN Client setup in the shared system network (Pending).
- [ ] Connectivity testing and finalization.


## Next Steps

- **AWS VPN Client Configuration**: 
  - Generate client and server certificates necessary for the VPN setup.
  - Create and configure the AWS Client VPN Endpoint in the shared system network. This includes setting up authentication methods and authorization rules to control network access.
  - Associate the VPN endpoint with the relevant subnets in the shared system VPC.

- **VPN Connectivity Testing**:
  - Install and configure an OpenVPN client on a local machine using the generated client certificates.
  - Establish a VPN connection to the shared system network and ensure secure communication channels are operational.
  - Test connectivity to the Aurora Serverless MySQL RDS database in the dev-system network via the VPN connection, ensuring that the database is accessible only through the VPN.


# SMARTLEARN : 3-Tier-Web-App-AWS

**3-tier web app** that stores students and professors real-time data, A repository containing the project report and the complete Cloud architecture.


### Abstract :
The project "SMARTLEARN" aims to develop a revolutionary learning web solution that adopts a student-centric approach. Through the creation of a smart academic web application, students will benefit from enhanced engagement in courses and university activities. The project involves analyzing the needs of a fictitious university, designing a solution, conducting a risk assessment following ISO 27001 standards, and proposing a security policy for sensitive data management. By implementing critical portions of the design in a lab environment, students will gain practical experience in architecting secure cloud infrastructures.

### Introduction :

Welcome to the "SMARTLEARN" project, where innovation meets education! This project invites students to design a cutting-edge learning web solution for a fictitious university, focusing on enhancing student engagement and academic performance. Through a series of activities including needs analysis, solution design, risk assessment, and security policy development, participants will delve into the world of cloud infrastructure architecture. By implementing critical components of the design in a lab environment, students will gain practical skills and insights into creating secure and student-centric academic applications. Join us on this exciting journey to shape the future of education with the "SMARTLEARN" project.

### ARCHITECTURE OVERVIEW :

The cloud architecture for the project spans three regions: Afrique, Europe, and Asie-Pacifique. This multi-region setup aims to ensure high availability, fault tolerance, and scalability for the smart academic web application designed for the fictitious university. By distributing resources across these regions, the architecture enhances performance and resilience, catering to users in different geographical locations.

In each region, the architecture includes **Virtual Private Clouds (VPCs)**, **subnets**, and **Availability Zones (AZs)** to segment and isolate resources, optimize network traffic, and provide redundancy. The use of multiple regions allows for geographic diversity, reducing the risk of downtime due to regional outages or disruptions.

Furthermore, data replication and synchronization mechanisms can be implemented across regions to ensure data consistency and disaster recovery capabilities. By leveraging cloud services and technologies tailored to **each region's requirements and regulations**, the architecture can effectively support the smart academic web application's operations and data management across Afrique, Europe, and Asie-Pacifique.

**Here is the complete Cloud architecture diagram:**

![WhatsApp Image 2024-04-04 at 7 51 38 AM](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/ca5ee4ad-b5c6-41bb-ad4d-d8064b4f95a9)


**Here is the detailed response for the requirements of the three tiers:**

![webreq](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/37620154-54da-4779-bfae-56346087aae4)
![webreqIMG](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/5d85ef28-a7f8-4db6-ae66-937d8555ce1d)
![Databasereq](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/fbdec4b6-0990-4e72-a424-a6c0d3c03f99)
![DatabasereqImg](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/9694a558-0645-4e87-a167-45feb90b48f5)
![ApplicationReq](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/dc782434-e411-4d7f-97f3-e2ebf5ad96e6)
![ApplicationReqImg](https://github.com/SimedNaiym/3-Tier-Web-App-AWS/assets/116762638/dde8bf43-ec0e-413f-a05e-2b4c62a4ddf2)

## Scalability:
Given our project ,'Smart education platform', wich will see a growth of 90%  we useed a VPC with a  /16 CIDR block.We added of course the **internet gateway** for connectivity with the INTERNET and **NAT gateways** for for the outbound trafic for the two regions (having multiple regions will help in time of crisis so you can find a backup):
![imag](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/b3d94d79-bdcb-46d7-8ad6-df0b6d64cfd7)


## Autoscaling:
This will allow our instances to perform based on the demand, for example not a lot of traffic on our platform? turn-off the by-standers instances( as i like to call them :) ) , a lot of traffic is comming our way? No problem, more computing power will be added as more instances will be created.Exemple below to show that sometimes it can be specified.
![image](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/7ff41d70-438c-4c0d-b110-80367d092342)

But numerous time you got to create an auto-scaling group as we did:
![pp](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/a0eb2ee0-56fb-4b6e-b2fd-425d98b514b3)

 ## Security:
Security was applied in our project  through:

  1. **Data Governance**: Ensuring that data is managed, stored, and utilized in a secure and compliant manner .
  2. **Risk Management (ISO 27001)**: Following the ISO 27001 standard for assessing, treating, and managing risks related to the proposed solution, with a focus on data 
  security .
  3. **Implementation of Secure Architecture**: Designing and implementing a secure architecture that meets the university's requirements for reliability and security, 
  including encryption, access control, and identity management , .
  4. **Security Policy**: Developing a security policy that specifies how sensitive data will be stored, shared, and managed by third parties, outlining the guidelines 
  and procedures for data security
  5. **secutity groups first** :
  Each Tier had it's own security group and route table to manage inboud and outbound trafic and who can access them. Specially the Database tier
  6. **Encryption**:
  Encryption of the Data in our Database
  7. **AWS WAF**:
  For the prevention of the DDOS atacks as exemple

 ## Additional informations:
- For some services/instances we took **snapshots** specially as we had two availibilty zones. It lets you replicate the instances as it is, with the same configurations.

- We added a **CloudWatch alarm** in our Apptier for when the https requests exceeds an amount.
 
- We of course created the internal and external **load balencers** to ensure equality between our servers :)
 

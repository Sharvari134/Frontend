# Frontend Detailed Documentation

| **Author** | **Created on** | **Version** | **Last updated by**|**Last Edited On**|**Level** |**Reviewer** |
|------------|---------------------------|-------------|----------------|-----|-------------|-------------|
|Sharvari Khamkar|  16-02-2025              | v3          | Sharvari Khamkar |21-02-2025    | L2 |  Abhishek |
|Sharvari Khamkar|  16-02-2025             | v2          | Sharvari Khamkar |21-02-2025    | L1 |  Taranddeep |
| Sharvari Khamkar|   16-02-2025             | v2          |Sharvari Khamkar |18-02-2025    |  L0 | Akshit kapil | 
|Sharvari Khamkar|   16-02-2025             | v1          | Sharvari Khamkar  |16-02-2025    |  Internal Reviewer | Komal Jaiswal |

## **Table of Contents**  
1. [Introduction](#introduction)  
2. [Pre-requisites](#pre-requisites)  
3. [System Requirements](#system-requirements)  
4. [Dependencies](#dependencies)  
   - [Build Time Dependency](#build-time-dependency)  
   - [Run Time Dependency](#run-time-dependency)  
5. [Important Port ](#important-ports)
6. [Architecture](#architecture)  
7. [Installation of Software Dependencies](#installation-of-software-dependencies)  
8. [Run the Application](#run-the-application)  
9. [Monitoring](#monitoring)
10. [High Availability](#high-availability)
11. [Disaster Recovery](#disaster-recovery)
12. [Troubleshooting](#troubleshooting)
13. [Frequently Asked Questions](#frequently-asked-questions-faq)
14. [Conclusion](#conclusion)  
15. [Contacts](#contacts)  
16. [Reference](#reference)  

## Introduction

Frontend Web is a REACTJS based application that is the primary user-interface for OT-Microservices stack.The app is designed for cross-platform fuctionality and requires only the presence of javascript runtime modules.The ReactJS based web framework facilitates complete web page based operations.

## Pre-requisites

The frontend application relies on REST APIs from **[OT-Microservices](https://github.com/OT-MICROSERVICES)**. To run the application successfully, ensure the following APIs are configured:  

Follow the link below for setup instructions:

* **[Employee API](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Anuj-SCRUM-6/OT%20MS%20Understanding/Application/Employee/POC/README.MD)** <br>
The Employee API is responsible for managing all employee-related data and operations within the system. It is one of the critical microservices in the OT-Microservices stack, providing endpoints for creating, reading, updating, and deleting (CRUD) employee records.<br>

* **[Attendance API](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Aayush-SCRUM-2/OT%20MS%20Understanding/Applications/Attendance/POC/README.md)**<br>
The Attendance API handles all aspects of employee attendance tracking and management. This includes logging attendance, monitoring work hours, and tracking leaves or absences.<br>

* **[Salary API](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Nikita-SCRUM-8/OT%20MS%20Understanding/Applications/Salary/POC/README.md)**<br>
The Salary API manages all salary-related operations, including salary calculations, pay slips, and adjustments. It serves as another independent microservice in the stack and is tightly integrated with both the frontend and the other APIs.<br>

* **[Redis](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Mohit-SCRUM-12/OT%20MS%20Understanding/Middleware/Redis/POC/README.md)** - Redis is a fast in-memory database mainly used for caching in the OT-Microservices stack. It helps store frequently used data, reducing the load on backend databases and making APIs respond faster.<br>

* **[ScyllaDB](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/5318bcc70e5b5477566f87b025ddd498bf498582/OT%20MS%20Understanding/Database/ScyllaDB/POC/README.md)** - ScyllaDB is the main NoSQL database in the OT-Microservices stack, used to store employee and salary data. It is highly scalable and designed for fast performance in large applications.<br>

* **[PostgreSQL](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Pooja-SCRUM-14/OT%20MS%20Understanding/Database/PostgreSQL/POC/Readme.md)** - PostgreSQL is the relational database in the OT-Microservices stack, used for storing attendance records. It is reliable, supports complex queries, and ensures data consistency.<br>

## System Requirements

| Hardware Specifications | Minimum Recommendation |
| ----------------------- | ---------------------- |
| Processor | 1 CPU, t2.micro EC2 | 
| Ram | 1 GiB |
| Disk | 8 GB |
| OS | Ubuntu 24.04 LTS |
***
## Dependencies

### Build Time Dependency

| Name | Version | Description |
| ---- | ------- | ----------- |
| GNU make | 4.3 | To build form Makefile |
| npm | 8.5.1 | Package manager for Javasrcipt |

### Run Time Dependency
| Name | Version | Description |
| ---- | ------- | ----------- |
| Nodejs | v12.22.9 | Javasrcipt runtime environment |

## Important Ports
| Inbound Traffic	 | Description |
| ---------------- | ----------- |
| 22 | For SSH |
| 3000 | Default REACTJS port |

## Architecture

![sf](https://github.com/user-attachments/assets/a39e039e-c5eb-4b93-9469-9c5f748ccbbc)



## Installation of Software Dependencies

* **[Frontend](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Ramratan-SCRUM-10/OT%20MS%20Understanding/Applications/Frontend/POC/README.md)**<br>
To set up the environment for the frontend application follow the above link.

## Run the Application

If the frontend is displayed correctly, the application is up and running.

![frontend](https://github.com/user-attachments/assets/6d7a46a7-5eed-460b-a014-6dbdfd260a3f)

## Monitoring

The application logs should be monitored using tools like Prometheus and Grafana to track system health, API performance, and user interactions.

## High Availability

To ensure high availability, deploy the frontend using multiple instances behind a load balancer. Implement auto-scaling to handle increased traffic.

## Disaster Recovery

To prevent data loss and downtime, regular backups should be taken. In case of failure, restore from the latest backup and redeploy the application.

## Troubleshooting

- **Issue:** Application not starting  
  **Solution:** Check logs, ensure dependencies are installed, and verify the API connectivity.
- **Issue:** API requests failing  
  **Solution:** Ensure the backend services are running and accessible.
- **Issue:** UI not loading properly  
  **Solution:** Check browser console for errors and rebuild the application.

## Frequently Asked Questions (FAQ)

**Q: How do I change the default port?**  
A : Update the `package.json` start script with the desired port.

**Q: What if I get an "npm install" error?**  
A : Clear the npm cache using `npm cache clean --force` and reinstall.

**Q: What is the purpose of this frontend setup?** <br>
A : This setup is for a ReactJS-based frontend application that serves as the primary user interface for the OT-Microservices stack.


## Conclusion

The OT-Microservices stack includes a ReactJS frontend and backend services with Redis for caching, ScyllaDB for NoSQL, and PostgreSQL for relational data. It handles Employee, Salary, and Attendance data efficiently. Redis speeds up responses, while ScyllaDB and PostgreSQL ensure reliable storage. This setup makes managing employee operations smooth and fast.

## Contacts

| Name| Email Address      |
|-----|--------------------------|
| Sharvari Khamkar | sharvari.khamkar@mygurukulam.co|


## Reference
|Link |	Description|
|------------------------------------|------------------------------------|
|https://github.com/OT-MICROSERVICES/frontend| Frontend API

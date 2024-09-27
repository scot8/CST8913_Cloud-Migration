Lab 2 - IaaS/PaaS architecture


![mermaid-diagram-2024-09-19-183904](https://github.com/user-attachments/assets/3909463b-b59a-4422-9af2-996002f8422c)

The flowchart illustrates a web application architecture before IaaS, PaaS achitecture where:

React serves as the front-end, allowing users to interact with the UI.
It communicates with a Flask web server via an API to handle requests and business logic.
The Flask server interacts with a PostgreSQL database to store and manage data.

IaaS Deployment
A). ![mermaid-diagram-2024-09-19-190858](https://github.com/user-attachments/assets/52579f4b-1200-45ad-8c81-6d713c4469f4)

Description:-
In an IaaS (Infrastructure as a Service) model, you manage the virtual machines, storage, and networking resources. Here’s how you can deploy the application:

This step lies mainly on VM.

1. Creation of VMs for Frontend, backend and also database
2. Configuring of networks so VMs can communicate with each other
3. Once we are done configuring networks and creation of VM we can deploy the application.
4. Lastly, we configure the firewalls and security.

B). ![mermaid-diagram-2024-09-19-192013](https://github.com/user-attachments/assets/891f21e8-cfc8-4b39-92fb-37f7ce8e5de6)

Architecture of PaaS:-

1. So the React frontend VM is responsible for user interactions and making API calls to the backend.
2. I have also added Load balancer receives API calls from react and distributes incoming traffic to the app appropriate back-end services
3. Processes the API requests received from the load balancer
4. The Flask server queries this VM for data storage and retrieval
5. I have used cloud storage (s3) for large file stroage especially with Images and stuff.

PaaS Deployment

![Goma](https://github.com/user-attachments/assets/77cd004a-a92a-44ab-a247-50ed0f20f50b)

I felt like the image is very straight forward. 
1. I have deployed frontend in vercel.
2. Backend in Heroku
3. Also made sure, I have deloyed the database in Heroku Postgres (s3)
4. Default/prebuilt Load balancer in heroku that we don't have to worry about setting up as we did in IaaS Model
5. After I have used Azure Blob storage for Large files and backups


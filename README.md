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

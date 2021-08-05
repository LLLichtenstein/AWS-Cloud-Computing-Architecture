# Amazon Web Services (AWS) Cloud Computing Architecture
## Migration to the Cloud
### Overview
> > This final project for the AWS Academy Certificate in Cloud Computing Architecture details an architectural solution to move an existing application to AWS.<br><br>
> > In this scenario I am a Cloud Architect employed by GoGreen to help them move an application to AWS.<br><br>
> > The assignment description is as follows: <br>
> > GoGreen is a regional insurance company based in San Diego, California. GoGreen has a three-tier CRM web application, supporting sales users at headquarters, remote users, and mobile users.<br><br>
> > The application supports sales personnel to input new customers' data and edit current customers' information. GoGreen's goal is to reduce the use of paper, so whenever possible, users can also upload documents such as signed contracts and pictures of assets. <br><br>
> > The application is extremely important to the business. In addition to storing customers' data and documents, it also converts these documents into multiple formats, such as images for web and mobile use. <br><br>
> > Most of the users are located on the west coast of the United States, but because some of GoGreen's customers have presence in Europe and South America, sales representatives travel to these locations and need to access the application with acceptable performance.<br><br>
> > Currently the application runs on premises at GoGreen's data center and consistently suffers performance and reliability issues. <br><br>
> > A year ago the CIO asked the IT team to ensure that the application handles increased traffic and users. As a result, the IT team overprovisioned resources, which helped alleviate the problem for the first three months. This process had to be repeated a few times.<br><br>
> > GoGreen's CIO, in conjunction with the CFO, concluded that purchasing new equipmnet every 2 - 4 months is not a viable solution for this environment.<br><br>
> > The procurement process, which is always expedited, takes about 20 days, and it costs around $100,000. <br><br>
### Project Plan - Deliverables
> > 1. Provide a diagram of your proposed solution with as many details as possible <br>
> > &emsp; Cloud Implementation Architecture Diagram: 
> > https://github.com/LLLichtenstein/AWS-Cloud-Computing-Architecture/blob/main/go_green_diagram.jpg <br><br>
> > 2. Provide full documentation - a guide to deploy the application on AWS - about all aspects of configurations in the environment <br>
> > &emsp; Final Project Description: https://github.com/LLLichtenstein/AWS-Cloud-Computing-Architecture/blob/main/Final%20Project%20Description.pdf <br><br>
> > 3. A CloudFormation template of the environment in addition to the documentation will be accepted <br>
> > &emsp; JSON Template: https://github.com/LLLichtenstein/AWS-Cloud-Computing-Architecture/blob/main/GoGreen%20JSON.txt <br><br>
### Current Environment and Requirements
> > The following current environment and requirements were provided in order to complete the project. 
#### Current Environment
> > Web tier:<br>
> > &emsp; 6x Virtual Machines (2 vCPUS / 4GB memory)<br>
> > &emsp; SUSE Linux Enterprise Server 12 <br>
> > &emsp; Apache web server <br>
> > &emsp; PHP server with SQL connectors <br>
> > &emsp; PHP files <br><br>
> > Application tier: <br>
> > &emsp; 5x virtual machines (4 vCPUs /  32-GB memory) <br>
> > &emsp; SUSE Linux Enterprise Server 12 <br>
> > &emsp; Java SRE 7 <br>
> > &emsp; Java application files <br><br>
> > Database tier:<br>
> > &emsp; 2x virtual machines (8 vCPUs / 48-GB memory / 5.5-TB storage)<br>
> > &emsp; SUSE Linux Enterprise Server 12 <br>
> > &emsp; MySQL 5.6.22 database cluster <br>
#### Requirements
> > Environment: <br>
> > &emsp; Can only be managed by users located at GoGreen's data center <br>
> > &emsp; Headquarters and remote users require encrytped access to the application <br>
> > &emsp; Mobile users establish a connection with the application and are required to keep the same session <br>
> > &emsp; Establish a baseline for the number and type of instances needed <br>
> > &emsp; Developers require a central repository to push the production version of the code for the web and application servers <br>
> > &emsp; Recovery Point Objective for the application is four hours <br>
> > &emsp; Recovery Time Objective for the application is 30 minutes <br>
> > &emsp; Must support a user base that is expected to grow 90% in the next three years <br>
> > &emsp; Documents and pictures must be kept for five years. However, these files are rarely requested after three months <br><br>
> > Web Tier: <br>
> > &emsp; Architecture must be flexible and must handle any peak in traffic or performance <br>
> > &emsp; Servers are currently at 75% of memory capacity all the time. This number has to decrease to between 50% and 60% when initially moved to AWS <br>
> > &emsp; The overall acceptable incoming network bandwidth is between 300 Mbps and 750 Mbps <br>
> > &emsp; Application admins want to be notified by email if there are more than 100 "400 HTTP errors" per minute in the application <br><br>
> > Application tier: <br>
> > &emsp; Architecture must be flexible and must handle any peak in traffic or performance <br>
> > &emsp; Servers are currently at 90% of memory and CPU capacity all the time. This number has to decrease to between 50% and 60% when initially moved to AWS <br>
> > &emsp; Need eventual Internet access for patching and updates <br>
> > &emsp; Overall memory and CPU utilization should not go above 80% and 75% respectively or below 30% for both. <br>
> > &emsp; As servers are added/removed, the application needs a centralized location to store logs <br><br>
> > Database tier: <br>
> > &emsp; Needs to be moved with as few changes to the data structure as possible <br>
> > &emsp; Maximum downtime during migration is two hours <br>
> > &emsp; Database needs consistent storage performance at 21000 IOPS <br>
> > &emsp; Need eventual internet access for patching and updates <br>
> > ### Cost Considerations
> > The proposed solution must take into consideration all the technical requirements and the most conscious financial options: <br>
> > &emsp; Type of instances and payment models <br>
> > &emsp; Number of instances <br>
> > &emsp; Estimated monthly cost for the solution <br>


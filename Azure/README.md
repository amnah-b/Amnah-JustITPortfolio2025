# Azure Projects ☁️ 


This folder contains my Azure-related projects. These projects showcase my experience with Microsoft Azure services and tools, including cloud infrastructure, automation, and deployment.

## **Project: "Paws & Whiskers" 🐾**   
- Context: A growing pet shop aims to improve its business by analysing sales, customer information, and inventory data. Currently, the data is collected manually or stored in spreadsheets. Management is interested in transitioning to Microsoft Azure to streamline data storage, analysis, and reporting, enabling them to make data-driven decisions.


### Report:  
Paws & Whiskers is a growing pet shop aiming to analyse sales, customer information, and inventory data to make data-driven decisions. They want to transition to Microsoft Azure for better data storage, analysis, and reporting, enabling them to make data-driven decisions.



## Data Laws and Regulations:

### GDPR Compliance -
The General Data Protection Regulation (GDPR) is the European Union law designed to protect individuals' personal data. It affects any business handling data and although the UK has left the EU, the UK has incorporated GDPR into its national law through the UK GDPR.

•*How this can be helpful for Paws & Whiskers:* 
o	Customer Data: All customer personal data (e.g., names, addresses, email, phone numbers) must be stored securely.
o	Data Processing: "Paws & Whiskers" needs to ensure transparency in how they process customer data and allow customers to access, correct, or delete their information.
o	Consent: They must obtain explicit consent from customers for data collection and processing.
o	Data Breach: Any data breach must be reported to the Information Commissioner’s Office (ICO) within 72 hours if it affects personal data.
o	Data Minimisation: The shop should only collect data necessary for the purpose and limit the retention period.

### Data Protection Act (DPA) 2018 -
The Data Protection Act (DPA) 2018 is the UK’s implementation of the GDPR. It outlines how personal data must be processed, stored, and protected in the UK.

•	*How this can be helpful for Paws & Whiskers:*
o	Security: Customer data must be stored securely, and appropriate technical measures such as encryption and access controls should be applied to protect the data from unauthorised access.
o	Rights of Individuals: Customers have the right to request access to the data held about them, the right to rectify inaccuracies, and the right to request the erasure of their data.
o	Data Transfers: If Paws & Whiskers transfers customer data outside the UK, it must ensure that the data is protected to the same standard as required by the UK GDPR, including using Azure services with appropriate compliance certifications.

### Other Industry Standards - 
•	PCI-DSS (Payment Card Industry Data Security Standard):
o	If Paws & Whiskers accepts card payments, it must comply with PCI-DSS to protect customers' payment information. Azure offers services like Azure Key Vault to store encryption keys and Azure Security Centre to ensure compliance with security standards.
•	ISO 27001:
o	This standard helps organisations implement robust information security management systems. As Paws & Whiskers stores sensitive customer and payment data, using a cloud service like Azure, which is ISO 27001 certified, ensures compliance with this industry-standard framework.



## Azure Service Recommendations: 
 
![image](https://github.com/user-attachments/assets/63e50c5f-24bf-45e5-a9cf-50602a8db5e9)

### Data Storage - 
•	Azure SQL Database:
A fully managed relational database service that can securely store customer data, sales transactions, and inventory information. It supports built-in security features, including Transparent Data Encryption (TDE), to ensure data protection.

•	Azure Blob Storage: 
Ideal for storing unstructured data such as images of pets, large product catalogs, and backups. Blob Storage can also store logs, sales reports, and bulk inventory data in a scalable, flexible and cost-effective manner.

### Data Analysis Tools - 
•	Azure Machine Learning:
Azure ML allows for advanced analysis of customer behaviour and purchasing trends. Paws & Whiskers can build predictive models to forecast sales, personalise customer recommendations, and optimise inventory management.

•	Azure Synapse Analytics:
Azure Synapse combines big data and data warehousing solutions. It can analyse large datasets efficiently, enabling Paws & Whiskers to examine sales patterns, inventory trends, and customer behaviour to inform business decisions, in real time.

### Data Integration and Automation - 
•	Azure Data Factory:
Azure Data Factory automates the ETL (Extract, Transform, Load) process, making it easier to integrate data from multiple sources. It can automate the collection of sales data, customer information, and inventory levels, improving overall efficiency and reducing manual data entry errors.



## Data Types and Data Modelling:

### Data Categories - 
•	Customer Data: Demographic information (e.g., address, age, name, gender), contact information (e.g., email, phone number), and transaction history.
•	Transaction Data: Sales details (e.g., product purchased, price, amounts, payment method), transaction dates, and discounts applied.
•	Inventory Data: Product details (e.g., pet types, category, quantity in stock, price), suppliers, and restocking details.
•	Product Categories: Types of products sold, such as pet food, grooming items, pet accessories, and toys.

### Data Modelling Approach - 
•	Relational Model:
o	Entities: Key entities include Customer, Sales, Products, and Inventory.
o	Relationships: A Customer may place multiple Sales (one-to-many relationship), a Product belongs to a Product Category (many-to-one relationship), and Inventory tracks stock levels.
o	Primary Keys: Each entity should have a unique identifier, such as CustomerID, SalesID, ProductID, and InventoryID.
o	Normalisation: The data should be normalised to reduce redundancy. For example, customer data should be in a Customer table, while sales data should be stored separately in a Sales table linked via CustomerID.



## Data Storage Formats and Structures in Azure:

### Data Formats - 
•	CSV: Suitable for raw data imports, such as bulk customer or transaction data. It’s simple, but not ideal for storing complex or large datasets.
•	JSON: Ideal for structured data that requires flexibility, such as storing customer preferences or product details in a hierarchical format.
•	Parquet: A columnar storage format suitable for large-scale data analytics. It provides efficient storage and faster query performance, making it ideal for use with tools like Azure Synapse Analytics for sales trend analysis.

### Data Security and Encryption - 
•	Azure Encryption: Use Transparent Data Encryption (TDE) for Azure SQL Databases to automatically encrypt data at rest. For data in transit, use SSL/TLS encryption to ensure secure communication.
•	Azure Active Directory (AAD): Implement Role-Based Access Control (RBAC) to ensure that only authorised personnel can access or modify sensitive data.
•	Azure Key Vault: Used to manage and store sensitive keys and secrets.
•	Data Masking: Sensitive customer data, like credit card numbers, can be masked to provide limited visibility to unauthorized users.



## Additional Considerations:

### Backup and Disaster Recovery - 
•	Azure Backup: Regular, automated backups of databases and other critical data should be scheduled to ensure business continuity. Azure Backup ensures that even if data is lost or corrupted, it can be restored from a previous backup.
•	Azure Site Recovery: For disaster recovery, Azure Site Recovery can replicate virtual machines and applications to secondary regions, ensuring minimal downtime in the event of a disaster.

### Data Visualisation - 
•	Power BI:
Enables management to create interactive dashboards and reports. For example, real-time sales trends, customer purchase behaviour, and inventory levels can be displayed in easy-to-read visuals to support decision-making.

### Future Scalability - 
•	Scalable Solutions: Azure services such as Azure SQL Database and Azure Synapse Analytics support auto-scaling to handle growing data volumes. Azure Data Lake can also handle big data workloads efficiently and Azure Machine Learning can scale to support more complex models as the business needs evolve. As Paws & Whiskers expands, these services can scale without the need for additional infrastructure.



## References:
•	General Data Protection Regulation (GDPR) https://en.wikipedia.org/wiki/General_Data_Protection_Regulation
•	UK Data Protection Act (DPA) 2018 
https://www.gov.uk/data-protection
•	PCI-DSS Compliance
•	ISO 27001 Certification
•	Microsoft Azure Documentation
https://learn.microsoft.com/en-us/azure/?product=popular


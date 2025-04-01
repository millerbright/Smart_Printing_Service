# <p align = 'center'>**A SMART PRINTING SERVICE FOR STUDENTS AT HCMUT**</p>
<p align ='center'> Developed by Group 15 - L03 - HK241</p> 

## Table of content
- [Introduction](#introduction)
- [Technologies Used](#technologies-used)
- [Source code](#source-code)
- [Requirement Elicitation](#requirement-elicitation)
- [Use case diagram](#use-case-diagram)
- [Class diagram](#class-diagram)
- [Develop MVP 1](#develop-mvp-1)
- [Architecture design](#architecture-design)
- [Implementation](#implementation)
- [Feature Overview](#feature-overview)
- [Conclusion](#conclusion)
- [Contributors](#contributors)

## **📌Introduction**
🎓 The HCMUT-SSPS (HCMUT Student Smart Printing Service) system is designed to meet the smart printing needs of students at Ho Chi Minh City University of Technology. The project focuses on providing features such as document management, online print order placement, print job status tracking, and payment processing via the PayOS system.

🎓 The main goal of the system is to minimize waiting time and enhance the printing experience for students while ensuring seamless integration with existing payment and data management platforms.

<p align="center"><img src="assets/temporary.png" alt="logo" width="100"></p>

## 🛠**Technologies Used**


## 🚀**Source code:**
The source code of the software can be accessed via the following link:

🔗 [Smart Printing Service SourceCode](https://github.com/ngochidung2111/CNPM)

## 📌**Requirement Elicitation** 

### 🚀 **Context Domain and Stakeholders in the Smart Printing Service for Students at HCMUT**:

**1. Context Domain**

🎓 The Smart Student Printing Service at HCMUT (HCMUT_SSPS) is an automated system designed to meet students' document printing needs across the university’s campuses. This system provides a network of printers distributed across various buildings and classrooms, allowing students to easily access and use them. Instead of taking their documents to external printing shops, students can directly upload files to the system via a web or mobile application, select a printer near their location, and configure printing options (such as paper size, number of pages, single-sided or double-sided printing, etc.).

🎓 The system is integrated with HCMUT_SSO, ensuring that only authenticated users (students and staff) can use the printing service. Additionally, the system enables students to manage the number of pages allocated by the university each semester and purchase additional pages through the university’s online payment system (BKPay). Each student has an account to monitor their printing usage, where A3 pages are counted as double compared to A4 pages.

🎓 All printing activities are logged, including timestamps, the printer used, and the number of pages printed. The system integrates with the university’s digital services to ensure strict management of printing resources, reducing waste and improving efficiency. It also benefits administrative departments by automating monitoring and generating reports on printing service usage.

**2. Stakeholders and Their Needs in the HCMUT_SSPS System**
- Students:
  - Convenient access to printing services: Students need an easy-to-use system accessible via both web and mobile applications to upload documents, select printers, and configure printing properties (paper size, single/double-sided, number of copies, etc.).
  - Usage tracking and history management: They require a feature to review their printing history, total pages printed, and remaining print balance, allowing them to control their printing usage efficiently.
  - Purchasing additional print pages: Students need the ability to buy extra print pages (A4, A3) via online payment gateways like BKPay when their allocated print balance runs out.
  - File format support: The system must support multiple common file formats (PDF, DOCX, PPTX, etc.) to ensure smooth printing without file upload issues.
- Printing Service Management Staff (SPSO):
  - Printer system management and monitoring: SPSO staff need the ability to add, activate, or disable printers in the system. They also require real-time information on printer status for maintenance and troubleshooting.
  - Print quota and system configuration management: SPSO staff need tools to modify the default number of allocated print pages per student each semester and configure accepted file formats.
  - Monitoring and report generation: SPSO staff require features to view and export reports on students' printing history or overall system usage within a specific timeframe. These reports help in monitoring service usage and managing printing resources efficiently.
- Authentication System (HCMUT_SSO):
  - Security and authentication: The SSO system must ensure that all users, including students and SPSO staff, are securely authenticated before accessing HCMUT_SSPS. This helps protect user accounts and prevent unauthorized access.
  - Seamless integration with HCMUT_SSPS: The SSO system should integrate smoothly with HCMUT_SSPS to ensure a seamless login experience without disrupting user interaction.
  - Access control management: The SSO system must enforce clear user permissions, ensuring that students can only view and manage their documents, while SPSO staff have administrative access to manage and monitor the entire printing service.
- BKPay:
  - Integration with HCMUT_SSPS: BKPay must ensure seamless integration with HCMUT_SSPS so that students can easily purchase additional print pages without technical issues.
  - Transaction logging and verification: BKPay must accurately validate student payment transactions, ensuring correct verification of the paid amount and purchased print pages.
 
**3. Benefits of the HCMUT-SSPS System for Stakeholders**
- Students:
  - Convenient access: The system provides printing services via web and mobile applications, allowing students to access it easily from anywhere.
  - Effective management: Students can track their printing history and account balance, enabling clear cost control for service usage.
  - Financial flexibility: The ability to purchase additional print pages through online payment systems like BKPay allows students to top up pages as needed.
  - Diverse printing options: The system offers various printing settings such as paper size, number of copies, and printing mode (single-sided/double-sided) to meet individual needs.
  - Enhanced security: Authentication via the HCMUT_SSO system ensures account protection and safeguards students' personal information.
- Printing Service Management Staff (SPSO):
  - Flexible printer management: SPSO staff can easily add, activate, or disable printers, ensuring continuous and efficient operation.
  - Easy configuration adjustments: The ability to modify the default print page allocation and file format settings helps SPSO serve students better.
  - Smart monitoring and reporting: Automated tracking and reporting features allow SPSO to analyze usage history and make informed management decisions.
  - Strict resource control: SPSO can review individual student printing logs or the entire system’s usage over specific time periods, improving resource management.
- Authentication System (HCMUT_SSO):
  - User information security: The authentication system ensures that only verified users can access the service, protecting user accounts from unauthorized access.
  - Seamless user experience: Smooth integration with HCMUT_SSPS enables quick and uninterrupted login, enhancing the overall user experience.
- BKPay:
  - Increased revenue: BKPay generates income from transaction fees when students purchase additional print pages.
  - Enhanced credibility: By ensuring secure and reliable transactions, BKPay builds trust among users.
    
### 🚀 **Functional and Non-Functional Requirements of the HCMUT-SSPS System**:

**1. Functional Requirements**
- Students:
  - Select a printer to receive the document.
  - Upload document files.
  - Adjust print settings such as size, pages to print, single-sided or double-sided, and number of copies.
  - Check printing history.
  - Print documents only when sufficient pages are available.
  - Purchase additional pages through the payment system.
- Printing Service Management Staff (SPSO):
  - Restrict and adjust the types of files students are allowed to print.
  - View printing history of all students or a specific student based on date and printer.
  - Modify the number of pages allocated to students per semester.
  - View printing reports by month and year.
  - Add, start, or disable printers.
- Authentication System (HCMUT_SSO):
  - Authenticate user identity when accessing the website and assign permissions based on user type.
- BKPay:
  - Verify and confirm the payment process when students request to purchase additional pages.
  - Authenticate student transactions, verify paid amounts, and track the number of pages purchased.

**2. Non-Functional Requirements**
- Performance Requirements:
  - The system must handle multiple concurrent print requests (at least 500 requests simultaneously) without slowing response time.
  - Uploading and processing a print request should take less than 2 seconds for documents under 10MB.
  - Maximum response time must not exceed 4 seconds.
  - The system must ensure continuous printing service during peak hours, such as exam periods and semester-end.
  - Web application should use less than 300MB of RAM during operation.
- Reliability Requirements:
  - The system must log all printing activities and recover information in case of power failure or system errors.
  - The error rate in the printing process (e.g., printer failure or file errors) must not exceed 10%, ensuring a 90% success rate.
  - The system must have a backup plan to prevent service disruptions.
  - Maintenance sessions should last no longer than 20 minutes per instance, and only system owners should access the system during maintenance.
  - The system should be available from 6 AM to 8 PM, Monday to Sunday.
- Security Requirements:
  - All users must be authenticated via HCMUT_SSO before using the system.
  - All student information must be encrypted in the database and during transmission.
  - The website must comply with university regulations and legal requirements.
  - The system must log all access and operations for auditing purposes.
- Usability Requirements:
  - The user interface must be user-friendly, enabling students to easily find information and operate the printing service (97% of students should be able to use it easily with guidance).
  - New users, system staff, and admins should become proficient in using the system within 10-15 minutes, 20-30 minutes, and 35-50 minutes, respectively, after reviewing detailed instructions.
  - Video tutorials or FAQs must be provided to assist students in troubleshooting issues.
  - The system should include online support features (chatbot or email support) for timely assistance.
  - The interface should support Vietnamese and be switchable to English.
  - The system must support common file formats such as PDF, DOC/DOCX, PNG, JPEG, etc.
- Scalability Requirements:
  - The system must support adding at least 50 additional printers without reducing performance.
  - The system should accommodate 2,000 new users annually.
  - It should be expandable to include new features such as mobile payment or SMS notifications.
  - The software architecture should allow easy module upgrades without affecting other parts of the system.
- Maintainability Requirements:
  - Each system module should be designed simply and clearly for easy testing and debugging.
  - Regular maintenance should be scheduled once a month, including software updates and security checks.
  - Detailed technical documentation should be provided for system maintenance and upgrades.
- Availability Requirements:
  - The system must maintain at least 99.9% uptime, with a maximum downtime of 8.76 hours per year.
  - Continuous monitoring should be in place to detect and notify issues promptly for quick intervention.
  - The system should notify students at least one week in advance of scheduled maintenance to allow them to plan printing activities accordingly.
- Compatibility Requirements:
  - Ensure compatibility between the SSPS system and printers.
  - Ensure compatibility between the SSPS system and the HCMUT_SSO authentication service.
  - Ensure compatibility between the SSPS system and the BKPay payment system.
  - The system must function properly on major browsers such as Chrome, Firefox, Safari, and Edge, as well as on mobile operating systems like Android and iOS.
- Management and Reporting Requirements:
  - The system should automatically generate monthly reports on printing activities and usage statistics.
  - Reports must be easily accessible and customizable for administrators.

## 📌**Use case diagram** 

<p align="center"><img src="assets/temporary.png" alt="csdl" width="400"></p>

## 📌**Class diagram** 

<p align="center"><img src="assets/temporary.png" alt="csdl" width="400"></p>

The class diagram describes the print service management system, including key classes such as `User, Student, SPSO, SystemConfiguration, Report, PaymentTransaction, PrintingHistory, PrintJob, Printer, PrintProperties, Document, and Location`.
- User and Student are two main classes that extend from a base class. Users can perform actions such as `resetPassword()`, `authenticate()`, and `updateProfile()`, while Student includes additional printing-related functionalities such as `viewPrintingHistory()`, `buyPages()`, `schedulePrinting()`, and `checkBalance()`.
- SPSO (Service Printing System Operator) manages the printing system through methods like `managePrinters()`, `configureSystem()`, and `generateReports()`. This class is directly linked to SystemConfiguration, which is responsible for configuring printing quotas and allowed file types.
- PrintJob stores information about print jobs, including start time, end time, status, and printing properties. Operations on PrintJob include `submit()`, `cancel()`, `getStatus()`, and `checkBalance()`. Additionally, this class is associated with PrintProperties to manage detailed printing settings such as paper size, number of pages, and document information.
- PaymentTransaction handles student payment transactions with methods like `processPayment()`, `validateTransaction()`, and `getReceipt()`.
- Other classes such as `Location, Printer, and Document` manage information related to printers, documents, and printing locations within the system.

## 📌**Develop MVP 1** 

Our team has designed the user interface using Figma. To view the detailed MVP 1 design, please access the Figma design [here](https://www.figma.com/design/5M6OHNT6IMSLUMfqzglkhf/CNPM?node-id=0-1&p=f).

<p align="center">
<img src="assets/temporary.png" alt="Ctmn" width="200">
</p>

<p align="center">
<img src="assets/temporary.png" alt="mh" width="200">
</p>

<p align="center">
<img src="assets/temporary.png" alt="mh2" width="200">
</p>

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

## 📌**Architecture design**

### 🚀 **Layered Architecture**

**1. Overview:**

To build the HCMUT_SSPS smart printing service website, the team adopts the MVC architecture model (Model-View-Controller):
- `Model`: Handles and manages data, focusing on business logic and data processing to ensure a coherent and consistent system.
- `View`: Represents the user interface, responsible for displaying data from the Model and receiving user interactions.
- `Controller`: Acts as an intermediary between the Model and View, managing core logic and processing user requests, ensuring smooth and consistent system operation.

**2. Architectural Diagram**

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

**3. Architectural Diagram Description**

For the system architecture, the team utilizes the **MERN stack (MongoDB, Express, React, Node.js)**, structured into three main layers: **Presentation Layer, Application Layer, and Data Layer**. With the support of an **API Gateway**, microservices handle specific functions such as **user management, printing history, printers, and payment**, ensuring system stability, maintainability, and scalability.
- Presentation Strategy: This is the first layer in the architecture, designed with a focus on simplicity, usability, and user experience. To achieve this, the team employs modern technologies, specifically:
  - Front-end Library and Framework: The team uses React to develop the front-end. React allows the creation of flexible and efficient user interfaces.
  - User-Friendly Features: The team prioritizes intuitive elements such as buttons, forms, and easy-to-navigate menus to ensure that even first-time users can easily interact with the system.
  - Responsive Web Design: Ensures compatibility across different devices used by students and faculty members. The system is designed to adapt to various screen sizes, including desktops, mobile phones, and tablets.
  - With React as the front-end framework, along with a user-centric design approach, the team aims to deliver an impressive user interface for HCMUT_SSPS while ensuring smooth integration with the system's layered architecture.
- Data Storage Approach: In the system's layered architecture, the Data Layer utilizes MongoDB to store application data in collections instead of tables (as in relational databases). MongoDB provides flexibility for handling both structured and dynamic data.For the Smart Printing Service system, data is organized into collections corresponding to key entities, such as:
  - Users: Stores customer information, including fields like user_id, full_name, password (hashed), role (Student or Staff), email, balance (remaining A4 pages), and last_usage.
  - SPSO: Stores SPSO details, including sps_id, full_name, username, password (hashed), dob, email, phone, and last_usage.
  - Printers: Stores printer information with fields like printer_id, printer_name, brand, model, description, location (campus, building, room), and status.
  - Documents: Stores document details such as document_id, user_id, file_name, file_format, and page_count.
  - PrintJobs: Stores print job data, including job_id, user_id, print_config (page orientation, paper size, duplex type, pages per side), start_time, end_time, status, and page_count_used.
  - Transactions: Stores payment transactions for purchasing print pages, with fields like transaction_id, user_id, timestamp, pages_purchased, price, and status.
  - Feedback: Stores user feedback, including feedback_id, user_id, title, content, and rating.
  - Using MongoDB enhances system scalability and flexibility. MongoDB stores data in JSON-like documents (BSON), allowing the system to handle schema variations without rigid constraints. For example, printer information may have varying attributes depending on different cases, and MongoDB enables seamless management of such dynamic structures.
- API Management: API (Application Programming Interface) is a collection of methods and protocols that allow the system to interact with external applications and services. APIs provide access points for calling system functions, enabling seamless data exchange and processing. For the HCMUT_SSPS automated printing system, the APIs include:
  - Authentication and Security API: Ensures secure communications and printing operations via HCMUT_SSO authentication, while managing user access rights under SPSO supervision.
  - Data Formatting and Input Processing API: Allows applications to send print files, images, or text data to the system. This API ensures data meets format and quality requirements before processing.
  - Print Job Management API: Enables users to create, manage, and monitor print jobs, including scheduling, tracking status, checking available page balance, and canceling print jobs when needed.
  - Payment API: Facilitates transactions for printing services and additional page purchases via the BKPay payment platform.
  - Custom Print Template API: Allows users to create and manage custom print templates, supporting dynamic template generation for specific printing needs.
  - Printer Control API: Provides direct control over printers, allowing the system to send commands and interact with devices.
  - Reporting and Statistics API: Retrieves data on completed print jobs, execution time, page count, and other metrics. This API serves as a data source for tracking and generating detailed reports on printing activities.
  - These APIs automate printing workflows while optimizing security, flexibility, and system-wide monitoring from user authentication to device control and print job reporting.
  - To manage these APIs, the team will implement: API Gateway to orchestrate API requests efficiently. OpenAPI Specification (Swagger) for API documentation and testing, ensuring scalability and maintainability of the system.

### 🚀 **Component Diagram**

**1. Component Diagram for Student Document Printing Function**

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

Description of the Document Printing Component Diagram:
- PrintWebpage
  - Functionality:
    - Provides an interface for students to initiate print requests.
    - Receives input from students, including documents, printer selection, and print settings.
  - Interactions with other components:
    - Printer: Sends requests to select an available printer.
    - PrintInfor: Sends requests to configure printing attributes.
    - Document: Sends requests to load the document for printing.
- Printer
  - Functionality:
    - Manages and lists available printers in the system.
    - Checks printer statuses and selects an available printer.
  - Interactions with other components:
    - PrintWebpage: Receives requests to select a printer from the user interface and responds with the printer status.
- PrintInfor
  - Functionality:
    - Manages printing settings such as paper size, print mode (single/double-sided), etc.
    - Stores printing preferences chosen by students.
  - Interactions with other components:
    - PrintWebpage: Receives requests to set printing attributes.
    - Accounting: Triggers a process to check the student's account balance before executing the print request.
- Document
  - Functionality:
    - Handles and stores uploaded documents from students.
    - Verifies document attributes to ensure compatibility with system configurations.
  - Interactions with other components:
    - PrintWebpage: Receives requests to upload documents from students.
    - SystemConfig: Performs configuration checks on documents to ensure system compatibility.
- Accounting
  - Functionality:
    - Manages student account balances.
    - Checks the student’s balance before allowing printing.
  - Interactions with other components:
    - PrintInfor: Receives requests to verify account balances for printing.
- SystemConfig
  - Functionality:
    - Manages and stores system printing configurations, including file formats, sizes, etc.
    - Ensures that documents comply with configurations before printing.
  - Interactions with other components:
    - Document: Receives configuration check requests before executing the print job.

**2. Component Diagram for the Entire System**

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

Description of the Entire System Component Diagram:
- Subsystem Student: Functions for students, including:\
  - Login: Allows students to log in via SSO.
  - Print: Enables students to request document printing.
  - Purchase: Allows students to buy additional print pages via payment services.
  - View my history: Enables students to view their printing history.
- Subsystem SPSO: Management functions for SPSO, including:
  - Login: SPSO login component.
  - View printers: Displays a list of available printers.
  - Manage configuration: Sets system configurations (e.g., default number of pages per student).
  - Add/Enable/Disable printers: Manages printer status.
  - View all history: Views the printing history of all students.
  - View report: Reviews monthly or yearly printing reports.
- Subsystem SSO_HCMUT:
  - User authentication component of the HCMUT system, supporting student and SPSO logins.
- Subsystem Webpage:
  - Includes APIs and functionalities for core business processes, such as:
    - Documenting: Manages printing documents.
    - Printer API: Communicates with printers for print requests.
    - System config: Configures general system settings.
    - Accounting: Manages student print balances.
    - View printers: Displays and manages printer information.
    - View history: Views printing history.
- Subsystem Database:
  - Stores system information and data, including:
    - Students info: Stores student data.
    - SPSO info: Stores SPSO data.
    - System config: Stores system configurations.
    - Printers info: Stores printer information.
    - Prints info: Stores student print requests.
    - History: Stores print history.
    - Report: Stores monthly and yearly reports.
- Subsystem Printer:
  - Handles printing requests, including:
    - Queue: Manages the queue of print jobs.
    - Start Printing: Executes document printing when requested by students.

**Interactions Between Components:**
- Student/SPSO and SSO_HCMUT:
  - When a student or SPSO wants to access the system, they must authenticate through SSO_HCMUT.
  - The Authentication component in SSO_HCMUT processes the login request, verifies user credentials, and sends a success or failure response.
- SSO_HCMUT and Database:
  - The Authentication component retrieves data from Students info and SPSO info in the Database to verify user credentials.
- Student and Webpage:
  - Print from the Student Subsystem sends a print request to Documenting.
  - Documenting processes document information, while Printer API handles print settings and execution.
  - View my history from the Student Subsystem sends a request to View history in Webpage to retrieve printing history, including document name, page count, and timestamp.
- SPSO and Webpage:
  - View printers from SPSO interacts with Printer API in Webpage to fetch a list of printers and their statuses.
  - Manage configuration from SPSO communicates with System config in Webpage to adjust system settings, such as default page quotas and permitted file types.
  - View all history from SPSO sends a request to View history in Webpage to retrieve the full printing history.
- SPSO and Database:
  - View report accesses Reporting in the Database to retrieve summary data for printing reports.
- Webpage and Database:
  - Webpage components access the Database to store or retrieve information when requested by students or SPSO.
- Webpage and Printer:
  - When a student requests to print a document, Printer API in Webpage sends a request to available printers via the Printer subsystem.
  - Printer API places the document in the print queue (Queue component).
  - After completing the print job, the Printer component sends a status update (completed or failed) back to Webpage, which then updates the Database accordingly

## 📌**Implementation**

**.1 Technologies Used**
The system is designed and built using a combination of modern technologies, divided into two categories: core technologies and supporting technologies. This selection not only ensures efficiency and security but also optimizes user experience and system scalability.


<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

- Core Technologies:
  - MongoDB: MongoDB is a flexible and scalable NoSQL database management system. It uses a document-based structure instead of traditional tables, making it efficient for storing heterogeneous data. MongoDB supports powerful queries and integrates seamlessly with modern applications, reducing complexity in data processing.
  - Express.js: Express.js is a simple yet powerful backend framework for Node.js, enabling quick and efficient development of RESTful APIs. It provides various useful tools such as middleware for handling business logic and managing HTTP requests. Due to its flexibility, Express.js simplifies development and maintenance while ensuring high performance.
  - React: React is a JavaScript library developed by Facebook, used for building dynamic and interactive user interfaces. React allows the creation of reusable UI components, reducing development effort and improving code maintainability. With its Virtual DOM mechanism, React optimizes rendering performance, ensuring a smooth user experience.
  - PayOS: PayOS is a payment platform integrated to securely and efficiently process financial transactions. It supports various payment methods, including credit cards, e-wallets, and bank transfers, catering to diverse user needs. Integrating PayOS into the system ensures high security in transactions and minimizes fraud risks.

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

- Supporting Technologies:
  - Postman: Postman is a powerful API testing tool that ensures the accuracy and performance of API endpoints. It allows developers to easily send HTTP requests, view server responses, and perform automated tests. Additionally, Postman provides collection management features to organize and share test scenarios among team members.
  - Draw.io: Draw.io is an online diagramming application commonly used for modeling system architectures and data flows. It allows the creation of professional diagrams, including UML, ERD, and flowcharts. With integration support for cloud storage platforms like Google Drive and GitHub, Draw.io enhances team collaboration.
  - Figma: Figma is a web-based UI/UX design tool that enables real-time collaboration among teams. With an intuitive interface and powerful features, Figma facilitates quick and easy UI design. Furthermore, its sharing and feedback features streamline the design and deployment process.
  - GitHub: GitHub is a widely used source code management platform that tracks code changes and supports team collaboration. It provides tools such as pull requests, branches, and issue tracking for managing and reviewing changes in a project. With CI/CD integration, GitHub also automates deployment and testing workflows.
- With the seamless integration of core and supporting technologies, the system not only meets business requirements but also delivers the best user experience.

**5.2 GitHub Repository Setup**

The team has set up a GitHub repository, accessible [here](https://github.com/ngochidung2111/CNPM).

<p align="center">
<img src="assets/temporary.png" alt="mh3" width="200">
</p>

This repository stores the source code for the `Student Smart Printing Service at HCMUT`, developed by `team L03 for the Software Engineering course`. It includes the following main components:
- client: Contains the frontend source code.
- server: Contains backend logic and API implementations.
- docs: Stores documentation and project descriptions.
Additionally, configuration files such as package.json help manage project dependencies. The README file provides an overview and objectives of the project.

**3. Usability Test**

Usability testing is the process of evaluating the effectiveness, ease of use, and user-friendliness of a user interface in product development. For the printing service for students at Ho Chi Minh City University of Technology (HCMUT), this test aims to ensure that the system meets the needs and expectations of end users. This document presents the usability testing process based on methods and procedures proposed by the Nielsen Norman Group (NNGroup).

- Testing Objectives: The objectives of this usability test are:
  - User-friendly interface: Evaluate whether the interface is easy to understand and use.
  - Ease of use of functions: Assess the ability to perform key tasks efficiently and effortlessly.
  - Task completion efficiency: Measure the time taken and the success rate of task completion to determine system effectiveness.
  - Improvements based on feedback: Collect user opinions and suggestions to adjust and enhance the interface before deployment.
- Selection of Test Participants: The selection of test participants is an essential factor influencing the accuracy and completeness of the usability test. For the printing service at HCMUT, the test group selected four participants with the following characteristics:
  - Participant A: A student from the Faculty of Computer Science and Engineering with experience in developing and using similar websites.
  - Participants B, C, D: Students from other faculties without in-depth knowledge of web development.
  - This selection helps evaluate the interface from different perspectives, ensuring that the system is usable for both tech-savvy and non-tech-savvy users. Since HCMUT students are the primary users of this service, selecting representatives from this group ensures accurate and useful feedback collection.
- Test Scenario Design: Designing test scenarios is a crucial step in guiding participants through the usability test while performing the required tasks. The scenarios are based on the system’s core functionalities to ensure all aspects are tested.
  - Performing Basic Student Functions:
    - Interfaces tested: Homepage, Role selection page (Student), Login page, Personal information page, Paper purchase page, Document printing page, Print history page, Payment history page.
    - Test scenario: `Access homepage`: Open a browser and verify that the homepage is displayed correctly.`Role selection`: Select "Student" and confirm redirection to the student login page. `Login`: Enter account credentials, verify successful login, and display personal information.`Purchase printing paper`: Select the quantity, complete the payment, confirm the transaction, and check for an updated paper count. `Print document`: Upload a document, select the number of copies, confirm the print command, and complete the process. `View history`: Access print and payment history, verify that information is displayed correctly.
  - Performing SPSO Functions:
    - Interfaces tested: Includes the first four steps from the student role, plus additional pages:`Printer management, System configuration, Print history, Print reports`.
    - Test scenario: `Manage printers`: Update printer information, turn devices on/off, confirm changes. `Configure system`: Modify system settings and confirm successful application. `View print history`: Check if print orders are displayed correctly. `View reports`: Access reports and verify that print usage statistics are displayed correctly.
- Testing Methods:
  - Qualitative Usability Testing: This method focuses on collecting qualitative feedback from users, including:
    - Interface evaluation: Assessing aesthetics, clarity, and consistency.
    - User experience: Gathering opinions on ease of use and task efficiency.
    - Challenges faced: Identifying difficulties encountered while using the system.
    - Improvement suggestions: Recommending interface and functionality enhancements.
  - Remote Unmoderated Testing:This method allows users to conduct tests naturally and flexibly without direct supervision.Steps involved:
    - Figma presentation: Use Figma to share the interface with users.
    - Online testing: Users perform tasks according to pre-designed scenarios.
    - Feedback submission: Users provide comments and suggestions after completing the test.
- Preparation of Testing Environment and Tools
  - Testing Environment:
    - Devices: Computer or mobile device with internet access, web browser, and a Figma account.
  - Testing Tools:
    - Figma: Used for interface design and presentation.
    - Google Forms: Used to collect feedback and evaluations from users.
    - Time tracking: A tool to measure completion time or ask users to record the time taken for each task.
  - Supporting Documents
    - Figma usage guide.
    - Detailed test scenarios.
    - Feedback forms (comments, time tracking, task completion rate).
- Conducting the Test:
  - Introduction and Instructions: Explain the testing objectives. Provide guidance on using Figma and following test scenarios.
  - Providing Figma Access: Share the Figma interface link, ensuring access permissions and interactivity.
  - Performing the Test: Users utilize Figma’s presentation mode to complete tasks based on the test scenarios, record task completion times, and provide interface feedback.
  - Collecting Feedback: Users fill out a feedback form (Google Forms) regarding their experience, challenges, and improvement suggestions.
- Data Collection and Analysis:
  - Data Collection:
    - Task completion time: Record the average time taken to complete tasks.
    - Completion rate: Assess the percentage of successfully completed tasks.
    - Feedback and comments: Gather opinions on strengths, weaknesses, and improvement suggestions.
  - Data Analysis:
    - Quantitative analysis: Calculate average task completion time and success rates.
    - Qualitative analysis: Categorize feedback into strengths, weaknesses, and improvement suggestions.
    - Problem identification: Evaluate common issues and their severity.
  - Evaluation and Conclusion:
    - Assess the extent to which testing objectives were met.
    - Identify the strengths and weaknesses of the interface and suggest specific improvements based on user feedback.
- Test Results and Recommendations:
  - Test Results:
    - User A: Completion rate: 100%, average time: 7 seconds. Feedback: Simple interface but lacks consistency in colors and design style. Suggestion: Add a file preview feature and usage instructions.
    - User B: Completion rate: 90%, average time: 17 seconds. Feedback: Lacks usage instructions, but other elements are fine.
    - User C: Completion rate: 100%, average time: 10 seconds. Feedback: Interface is good, suggests adding a dark mode.
    - User D: Completion rate: 100%, average time: 12 seconds. Feedback: Easy-to-understand and visually appealing interface.
  - Recommended Improvements
    - Enhance color scheme and aesthetics: Use harmonious and consistent colors.
    - Add file preview functionality.
    - Provide clear usage instructions.
    - Implement a dark mode option.
    - Increase consistency in interface design.
- Conclusion:
The usability testing of the SSPS project interface helped the team identify its strengths and weaknesses. While the system is designed for ease of use and fulfills its core functions, improvements in aesthetics and usability instructions are necessary to enhance user experience. Based on the test results, the team will adjust the interface according to the suggested improvements to improve visual appeal, consistency, and add essential new features.
## 📌**Feature Overview**

**1. Login**
- First, access the homepage of the website, then select "Login":
- The role selection interface will be displayed. Choose one of the two roles to proceed with login:
- Enter the student ID (MSSV) and password to log in.

**2. Actions for SPSO**
- After successfully logging in as an SPSO, the system will redirect to the homepage. Select "Manage" to access the management interface for SPSO.

- The first section is the printer management interface. Here, you can turn printers on/off, add new printers, edit existing printer information, and remove printers from the system.

- Next is the system configuration interface, where you can adjust system parameters.

- Following that is the print history interface. You can view the printing history of all students.

- Finally, the transaction history interface allows you to view all students' paper purchase history.

**3. Actions for Students**
- Similar to SPSO, after successfully logging in as a student, the system will also redirect to the homepage. Select "Print Now" to access the student interface.
- The first section is the document printing page. Here, you can select documents, choose a printer, specify the number of pages, paper size, single/double-sided printing, and the number of copies to print.
- Next is the page purchase section. Enter the number of pages needed and proceed with the purchase.
- The system will display a QR code for payment.
- Once the system confirms a successful payment, the website will redirect to the payment result page.
- Following that is the print history page, where you can view your own print history and filter by date.
- Finally, the transaction history page allows you to view your own purchase history.

## 📌**Conclusion**

The `HCMUT-SSPS (HCMUT Student Smart Printing Service)` is a technology solution designed to modernize and optimize the printing process for students at `Ho Chi Minh City University of Technology (HCMUT)`. By integrating modern technologies such as `MongoDB, ExpressJS, React, and PayOS`, the system has made significant progress in simplifying print order placement, document management, and online payment processing.

With features like `real-time print job status tracking, cashless payment support, and a user-friendly interface`, the system not only meets fundamental requirements but also enhances the overall user experience. The development team has focused on designing the system with ease of use in mind, ensuring convenience for students while optimizing processing performance to serve a large number of users efficiently.

Additionally, development tools such as `Postman, Draw.io, Figma, and GitHub` have played a crucial role in maintaining the project's progress, testing, and structured documentation. Initial testing has demonstrated the system's stability, meeting key criteria for `accuracy, processing speed, and data security`.

Looking ahead, the project team recognizes the potential for expanding HCMUT-SSPS by integrating `advanced features` such as `automated printing workflows, data-driven resource optimization, and multilingual support` to cater to international students. Furthermore, research into integrating technologies like `artificial intelligence (AI)` and `blockchain` is being considered to enhance security and personalization within the system.

Although there are still challenges to address—such as optimizing the interface for `mobile devices` and improving `compatibility with different printing systems`—the team believes that current efforts will serve as a `solid foundation for future development`. As a result, HCMUT-SSPS is not just a `smart printing solution` but also an essential part of the `technological ecosystem` supporting student life.

## 🏆Contributors
This project was successfully developed thanks to the dedication and effort of the following contributors:
1. Hàng Nhựt Long - 2211874
2. Nguyễn Anh Khoa - 2211614
3. Nguyễn Quang Sáng - 2212922
4. Nguyễn Minh Đạt - 2210693
5. Trần Quang Tác - 2212962
6. Trần Nguyễn Anh Khoa - 2211651
7. Ngô Chí Dũng - 2210578

🎉🎉🎉 Thank you for checking out this project! 🚀

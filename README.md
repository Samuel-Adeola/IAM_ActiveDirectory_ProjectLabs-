##	Project title: Active Directory Domain Services (AD DS) Implementation and Management for Organizational User and Resource Structure Using Agile Methodology 


##	Disclaimer Notice:
The use of the name "SidodatTech" in this project is for illustrative and educational purposes only. SidodatTech is a fictional company created for this project. Any resemblance to real companies, organizations, and individuals, living or dead, is purely coincidental. The information provided is intended for educational and research purposes. SidodatTech and other names used in this project do not endorse, sponsor, or approve any content, methodologies, or recommendations presented herein. All opinions, conclusions, and recommendations expressed in this project are solely those of the author and do not represent the views or positions of any actual company or organization. By viewing or utilizing this project, the reader acknowledges and agrees to these terms and conditions.


##	Scenario Background: SidodatTech AD DS Implementation and Management
SidodatTech, a mid-sized cybersecurity consulting and SOC service provider, has recently expanded its operations across multiple regions and departments, including Security Operations, Threat Intelligence, Compliance & Governance, and Client Engagement. As a result of this rapid growth, the organization is facing increasing challenges in managing its user accounts, departmental access, and IT resource permissions.
Currently, SidodatTech uses a flat, decentralized user management structure, leading to several operational inefficiencies:

•	Lack of centralized control: User and computer accounts are created manually across individual workstations, resulting in inconsistencies, account duplication, and poor tracking.

•	Access control issues: Employees across different departments have overlapping or inappropriate access to confidential resources due to the absence of structured group policies or security scopes.

•	Ineffective user lifecycle management: There is no formal process for disabling, renaming, or resetting accounts when users change roles or leave the organization.

•	Security risks: Without a proper organizational unit (OU) structure and group strategy, the organization is exposed to unnecessary risk, including privilege escalation and data leakage.

•	Administrative overhead: IT staff spend excessive time handling repetitive tasks like user creation, password resets, and policy changes due to the lack of delegation and automation.

These gaps significantly impact operational efficiency, data security, and compliance readiness, particularly as the company seeks ISO 27001 certification and aims to support growing client demands.
To address these challenges, SidodatTech has commissioned a project to design and implement Active Directory Domain Services (AD DS). The solution will include the creation of OUs aligned with the company's departmental structure, structured user and computer account management, group policies, and administrative delegation.


##	Table of Contents

Executive Summary

Project Background

1. Introduction

2. Problem Statement

3. Objectives

4. Scope

5. Technical Tools and Technologies

6. Project Methodology - Agile Model: Justification, Project Team and Stakeholders, Roles and Responsibilities, Project Timeline, Stakeholders and Meetings, Roles and Responsibilities, Communication Plan

7. Risk Management

8. Implementation Stages

9. Testing and Validation

10. Expected Outcomes and Success Criteria

11. Conclusion

12. References


##	Executive Summary
The increasing need for organizations to safeguard their digital infrastructure, protect sensitive information, and streamline user management processes has made it imperative for companies like SidodatTech to adopt structured identity and access management systems. At the core of this strategy is the implementation of Active Directory Domain Services (AD DS) on a Hyper-V guest server named CorpDC, hosted within the CorpNet.local domain. This central directory service supports network resource management, enforces security policies, and ensures compliance with industry standards. This project focused on the design, deployment, and management of AD DS to create a centralized environment that facilitates organizational growth while enhancing security, resource allocation, and operational efficiency. The deployment was carried out on CorpDC, the primary domain controller, hosted on Hyper-V, with CorpServer supporting supplementary functions such as DNS, DHCP, and File Services to reinforce domain functionality.

The implementation process involved several key steps. Initially, the project team identified departments within SidodatTech and mapped them to corresponding Organizational Units (OUs) within the CorpDC domain controller on CorpNet.local. The IT team then proceeded with the creation of computer accounts for essential devices, such as the Sales team's laptops, and configured user accounts following Role-Based Access Control (RBAC) policies. Specific account management tasks were carried out, including renaming user accounts, resetting passwords, disabling dormant accounts, and removing outdated restrictions from legacy configurations.
Security improvements were central to this project. Global security groups and Group Policy Objects (GPOs) were introduced within the CorpNet.local domain to control access to sensitive corporate resources managed by CorpDC. Clearly defined administrative roles and permissions enabled efficient delegation of tasks. This not only enhanced security by enforcing the principle of least privilege but also reduced the workload on senior IT personnel by empowering department-level administrators to manage their respective resources within defined boundaries.

This project is expected to significantly elevate SidodatTech’s business operations by optimizing user and resource management, enhancing system security, and reducing manual administrative overhead. By effectively managing Active Directory objects and implementing standardized access controls on CorpDC, the organization will benefit from improved operational efficiency, better regulatory compliance, and a lower risk of unauthorized access. The delegation of administrative privileges and segregation of duties will further reduce internal security risks while streamlining IT workflows.

Ensuring business continuity was a key consideration throughout the project. By maintaining a well-structured Active Directory environment on CorpDC and deploying core services on CorpServer, SidodatTech is equipped to minimize disruption during user provisioning or system failures. A robust backup and recovery strategy has been integrated, ensuring swift restoration of services in the event of system outage or data loss. Regular updates and audits will be performed to uphold system integrity and maintain security baselines. These measures ensure that critical infrastructure, particularly the CorpDC domain controller, remains available and resilient to operational disturbances.

In conclusion, this project lays the foundation for a secure, scalable, and efficient Active Directory infrastructure within CorpNet.local, powered by Hyper-V guest servers CorpDC and CorpServer. The implementation minimizes risk, improves compliance, and supports business growth by reducing administrative complexity and strengthening internal security governance.


##	Project Background

In the rapidly evolving landscape of modern information technology, the implementation and management of a centralized identity and access management infrastructure is critical to the operational efficiency, security, and scalability of organizations. SidodatTech, a mid-sized technology firm specializing in managed IT services and cloud infrastructure solutions, has recognized the growing need to streamline its internal IT governance and resource management systems through the structured deployment of Active Directory Domain Services (AD DS) within a dedicated domain environment named CorpNet.local. To support this initiative, SidodatTech provisioned a Hyper-V guest server named CorpDC to serve as the primary domain controller for the CorpNet.local domain. This server is responsible for hosting the AD DS infrastructure, managing user and computer accounts, and enforcing security policies. A second Hyper-V guest server, CorpServer, was deployed to handle auxiliary services including DNS, DHCP, and file sharing, thereby ensuring redundancy and service continuity across the directory environment.

Historically, SidodatTech’s user and resource management had been executed in a decentralized manner, leading to duplicated administrative efforts, security misconfigurations, and inconsistent application of access controls. As the organization scaled, these inefficiencies began to manifest in increased IT support incidents, prolonged user onboarding times, and limited visibility into permission structures across departments. The absence of a unified directory service has also posed challenges in enforcing compliance with industry security frameworks such as ISO/IEC 27001 and NIST SP 800-53, particularly in the management of identity lifecycle and access rights delegation.

This project emerges as a strategic initiative to implement a robust Active Directory Domain Services (AD DS) environment hosted on CorpDC under CorpNet.local domain, aligning with best practices in enterprise IT management. The goal is to create a secure, manageable, and scalable directory infrastructure that reflects SidodatTech’s departmental structure while enabling efficient user account provisioning, centralized resource access, and enforceable group policies. The deployment process involves restructuring Organizational Units (OUs), creating and managing security groups, and assigning administrative roles using delegated permissions, all of which are facilitated and controlled through the CorpDC server.

By integrating AD DS into SidodatTech’s core infrastructure via CorpDC and CorpServer, the organization will not only enhance its IT service delivery but also lay the foundation for more advanced directory-integrated technologies such as Group Policy Object (GPO) automation, Role-Based Access Control (RBAC), and future hybrid identity federation with cloud platforms. This initiative is both a response to current operational challenges and a proactive measure to future-proof the organization’s digital infrastructure.


##	1.0 Introduction

Active Directory Domain Services (AD DS) is a vital component of the IT infrastructure that provides a centralized and secure way to manage network resources, users, and devices in an enterprise environment. As businesses expand and evolve, it becomes essential to have a well-structured and organized system for managing these resources effectively. In this context, the implementation and management of AD DS play a crucial role in ensuring seamless operations, security, and compliance across the organization. This project focuses on the comprehensive implementation and management of AD DS for SidodatTech, using a dedicated Hyper-V guest server named CorpDC as the primary domain controller for the custom internal domain CorpNet.local. The CorpServer, another Hyper-V guest server, was configured to support additional infrastructure roles such as DNS, DHCP, and file services that complement the AD DS deployment. This virtualized infrastructure ensures flexibility, scalability, and isolation for testing and production deployment.

The primary objective is to develop a well-organized Active Directory structure that reflects the company’s departmental hierarchy, ensuring that users, computers, and other resources are managed efficiently. The implementation involves creating Organizational Units (OUs) for each department within CorpNet.local, configuring user and computer accounts on CorpDC, applying Group Policies, and setting up Security Groups to enforce access control. In addition to managing Active Directory objects, this project will also focus on optimizing user management tasks such as enabling/disabling user accounts, renaming accounts, resetting passwords, and removing account restrictions. These actions will ensure that user roles and permissions align with the organization’s needs, and any obsolete or unnecessary accounts and OUs will be removed to maintain a clean and efficient directory within the CorpNet.local domain.

A critical aspect of this project is the establishment of Global Security Groups and the delegation of administrative tasks using role-based access control (RBAC). By setting up defined permissions and delegating responsibilities, SidodatTech will be able to ensure that only authorized personnel can perform sensitive administrative tasks on CorpDC. This delegation will enhance security, improve efficiency, and reduce the risk of human error or unauthorized actions. The benefits of a well-managed AD DS implementation extend beyond organizational efficiency. A structured directory service like CorpNet.local enables improved security, data integrity, and access management, which are essential for compliance with industry regulations and internal security policies. By ensuring that all users and systems are properly managed and that sensitive data is securely protected, the company can reduce the risk of unauthorized access, mitigate security threats, and enhance the overall reliability of its IT systems.

Overall, this project aims to provide SidodatTech with a secure, scalable, and efficient Active Directory environment hosted on CorpDC, supporting the company’s growth and operational needs. By aligning Active Directory management with best practices and organizational objectives, SidodatTech will be well-positioned to support future expansion and maintain a robust and compliant IT infrastructure.



##	2.0	Problem Statement

In response to increased business expansion and organizational growth, SidodatTech, a cybersecurity and Security Operations Center (SOC) services provider has identified significant inefficiencies in its current approach to user and resource management. The absence of a centralized identity and access management (IAM) system has resulted in operational bottlenecks, security vulnerabilities, and a lack of structured IT governance.

Presently, user accounts, computer registrations, and access permissions are handled manually without standardized procedures or hierarchy. This decentralized approach has led to the duplication of user accounts, inconsistent access control, unauthorized resource access, and administrative burdens on the IT team. The inability to manage user accounts based on department-specific policies or enforce consistent security controls across the network infrastructure undermines both the operational performance and security posture of the organization. Moreover, the lack of a defined group strategy and delegated administrative roles further exacerbates the situation by introducing latency in account lifecycle management tasks such as enabling, disabling, renaming users, or resetting passwords. With the organization now supporting multiple departments such as Security Operations, Threat Intelligence, Compliance and Governance, and Client Relations, the need for a scalable and structured directory service is evident.

In addition, SidodatTech aims to enhance its security readiness and compliance maturity, particularly in preparation for certifications such as ISO 27001 and SOC 2. The current fragmented system cannot support the audit and traceability requirements these standards demand. A modern, domain-based identity management solution is therefore essential to meet internal control requirements and to support long-term growth.

This project proposes the implementation and management of Active Directory Domain Services (AD DS) to address these challenges. The AD DS framework will enable SidodatTech to:
•	Structure and manage Active Directory objects in alignment with organizational hierarchy.


•	Enforce group-based access policies through the creation of global security groups.

•	Delegate administrative permissions to improve operational efficiency.

•	Standardize user lifecycle management (e.g., user creation, disablement, password resets).
•	Improve auditability, scalability, and compliance with industry best practices.

Through the implementation of AD DS, SidodatTech expects to achieve a secure, robust, and scalable IT environment that aligns with its strategic goals and operational requirements.



## 3.0 Project Objectives

The objectives of this project are designed to systematically implement and manage Active Directory Domain Services (AD DS) within the CorpNet.local domain using the Hyper-V guest server CorpDC as the primary domain controller. This implementation aims to establish an effective and secure organizational user and resource structure. The project will achieve the following objectives:

1.	Creation of Active Directory Organizational Units (OUs) within the CorpNet.local domain, structured according to SidodatTech’s departmental hierarchy, ensuring a logical and efficient framework for user and resource management on the CorpDC server.

2.	Identify and remove obsolete or redundant OUs from the Active Directory on CorpDC, streamlining directory management and mitigating security risks associated with outdated or misconfigured organizational units.

3.	Establish computer accounts for the Sales team’s laptops within Active Directory, registering them in the appropriate departmental OUs in the CorpNet.local domain to enable centralized device management and secure authentication.

4.	Create user accounts on the CorpDC server within CorpNet.local, ensuring each account is configured with correct group memberships and access permissions based on department-specific roles and operational requirements.

5.	Perform key user account management functions such as enabling/disabling accounts, renaming user profiles, resetting passwords, and removing restrictions all within their respective OUs on the CorpDC server to maintain proper access controls and reflect user lifecycle events accurately.

6.	Implement global security groups within CorpNet.local, assigning defined access scopes to restrict and control access to sensitive systems and resources, in alignment with SidodatTech’s internal security governance policies.

7.	Enable the delegation of administrative duties by leveraging global security groups and built-in delegation features in Active Directory, thereby empowering designated team members with appropriate privileges to manage specific OUs or administrative tasks securely through CorpDC.

Each of these objectives contributes to improving the security, scalability, and efficiency of SidodatTech’s IT environment hosted across the CorpDC and CorpServer virtual infrastructure. By following best practices in Active Directory design and access control, the project ensures compliance, supports operational excellence, and enables future integration with advanced directory services.



## 4.0	Project Scope

This project focuses on the structured implementation and management of Active Directory Domain Services (AD DS) at SidodatTech to enhance the organization’s user and resource management capabilities. The scope encompasses the creation of a well-defined organizational unit (OU) structure within the AD DS environment that mirrors the departmental hierarchy, enabling efficient administration and resource segregation. It includes the decommissioning of obsolete OUs to streamline the directory and optimize performance. The project also involves the provisioning of user and computer accounts, including the configuration of accounts for the Sales team laptops and departmental users on the CorpDC server. Lifecycle management operations—such as enabling or disabling user accounts, renaming accounts, resetting passwords, and removing restrictions—are also within scope to ensure users maintain secure and uninterrupted access to resources.

In addition, the project covers the development and implementation of a group strategy using Global Security Groups (GSGs), which will facilitate fine-grained access control aligned with organizational roles. Administrative responsibilities will be delegated through role-based access control (RBAC) mechanisms by assigning permissions to designated users via security groups, thereby supporting operational efficiency while preserving overall security integrity. However, the project explicitly excludes activities such as the integration of cloud-based identity platforms like Azure AD, the implementation of Group Policy Objects (GPOs), scripting, deployment of Active Directory Federation Services (ADFS), and advanced security configurations like Kerberos ticketing or certificate services. By remaining focused on foundational AD DS elements, this project seeks to provide SidodatTech with a secure, scalable, and well-governed directory infrastructure that supports its current and future IT needs.



##	5.0	Technical Tools and Technologies
To ensure the efficiency and success of the project, various tools and technologies will be utilized throughout the implementation process:

•	Microsoft Active Directory: For setting up and managing users, groups, and security policies.

•	PowerShell: For automating the creation of user and computer accounts, as well as managing group policies.

•	Group Policy Management Console (GPMC): For configuring and managing group policies in the AD environment.

•	Hyper-V: For virtualizing the AD environment and testing configurations in a controlled setting.

However, this project was carried out in a real-world simulated lab environment with setup AD DS (Hyper-V guest manager (CorpDC).


##	6.0	Project Methodology: Agile Model

6.1 Overview of the Agile Methodology

This project adopted the Agile methodology to guide the implementation of Active Directory Domain Services (AD DS) at SidodatTech, including the deployment of a centralized Corporate Domain Controller (CorpDC). Agile methodology was deliberately chosen to promote a flexible, iterative, and stakeholder-centric approach, enabling adaptive responses to evolving requirements throughout the project lifecycle. By emphasizing adaptive planning, incremental development, early delivery, and continuous improvement, Agile proved ideally suited to the dynamic and collaborative nature of the project, which centered on designing a secure, scalable, and enterprise-ready Active Directory infrastructure within a live corporate environment.

The iterative cycles enabled the phased development of core components, such as the CorpDC (Corporate Domain Controller), Organizational Units (OUs), user accounts, and access control structures.


6.2 Justification for Agile at SidodatTech

SidodatTech's organizational culture emphasizes flexibility, continuous improvement, and stakeholder collaboration. The Agile methodology aligned seamlessly with these values, enabling the AD DS implementation project to proceed in adaptive cycles. The implementation of the CorpDC required coordination with multiple internal stakeholders, including the cybersecurity team, IT operations, HR, and compliance units. Due to the fluid nature of access control needs, system security considerations, and policy enforcement requirements, Agile provided the flexibility and structure needed to manage these components efficiently. The following specific factors justified its adoption:

•	Dynamic Requirements: Security roles, organizational units, and access policies were defined in collaboration with different departments, evolving throughout the project.

•	Continuous Stakeholder Engagement: Frequent reviews with IT leadership, the cybersecurity team, and HR ensured alignment with real-time organizational changes and facilitated continuous input from business units on the structuring and management of AD DS objects.

•	Progressive Delivery: Incremental deployment of AD components minimized disruption to existing infrastructure and allowed thorough validation.

•	Feedback-Driven Refinement: Regular feedback loops allowed adjustments to OU designs, account provisioning, and permission strategies.

•	Evolving Scope: Permissions and OU structures were adapted throughout development in response to organizational feedback.

•	Secure Incremental Delivery: The CorpDC and related services were configured and tested incrementally, minimizing downtime and enhancing security validation.

•	Feedback-Driven Refinement: Regular feedback loops allowed adjustments to OU designs, account provisioning, and permission strategies.

•	Compliance Alignment: Sprint reviews incorporated checks for compliance with internal IT governance and ISO 27001-aligned controls.

•	Risk Management: Continuous testing of CorpDC functionality minimized system misconfigurations, ensuring lab-to-production readiness.

Agile enabled SidodatTech’s project team to rapidly iterate on directory structure, user object creation, and security policy design, reflecting typical corporate scaling and operational dynamics.



6.3 Project Timeline

The project will be completed over 12 weeks, divided into six two-week sprints:

| Phase | Week(s)  | Deliverables |
|-------|-------|-------|
|Project Initiation | Week 1 | Kickoff meeting, environment preparation, scope definition. |
| Sprint 1: Infrastructure Setup | Weeks 1–2 | Hyper-V installation, CorpDC VM deployment, Windows Server 2022 installation, basic network configuration. |
| Sprint 2: Domain Configuration | Weeks 3–4 | Promotion of CorpDC to Domain Controller, creation of CorpNet.com domain, installation of DNS/DHCP roles. |
| Sprint 3: OU and Delegation Design | Weeks 5–6 | Structuring of Organizational Units (OUs) and delegation of administrative permissions. |
| Sprint 4: User/Computer Object Management	| Weeks 7–8 | Creation of test user accounts, security groups, and computer accounts using PowerShell automation. |
| Sprint 5: Group Policies (GPOs) and Security Hardening | Week 9-10 | Development and application of Group Policies for security baselines and account policies. |
|Sprint 6: Monitoring, Documentation, Closure | Weeks 11–12 | Event monitoring setup, stakeholder review meetings, project documentation finalization, and project closure.|




6.4 Stakeholders and Meetings

Stakeholders:

| Stakeholder | Role | Meetings Involvement |
|------|----|----|
| Project Sponsor (SidodatTech CTO)	| Oversight, budget approval, and final validation.	| Attended project kickoff, Sprint Reviews, and Closure meetings. |
| IT Operations Lead | Provided requirements for OU and group structure, environment resource allocation. | 	Participated in Sprint Planning, Sprint Reviews, and Weekly Standups. |
| Cybersecurity Officer	| Validated permission delegation models and security policies.	| Engaged during Sprint 3, Sprint 5, and Final Review meetings. |
| HR Representative |	Provided employee structure information for user creation scenarios. | Consulted during Sprint 4 for accurate departmental account setups. |




Key Meetings:

| Meeting Type | Frequency | Participants |	Purpose |
|--------|------|-------|-------|
| Project Kick-off | Week 1 | All stakeholders |Define objectives, scope, deliverables, and timelines |
| Sprint Planning | Bi-weekly | Project Team, IT Ops Lead, Information Security Officer	Define sprint goals, user stories, and tasks. |
| Daily Standups | Daily (15 min) | Project team | Report progress, blockers, and coordinate activities. |
| Sprint Review/Demo | End of each Sprint | All stakeholders | Demonstrate deliverables, collect feedback, and adapt the roadmap. |
| Sprint Retrospective | End of each Sprint | Project team | Reflect on sprint execution, identify improvements. |
| Final Project Review | Week 12 | All stakeholders	| Present final system, lessons learned, project closure. |




6.5 Project Team and Stakeholders Roles and Responsibilities at SidodatTech

The Project Team and Stakeholders section provides an overview of the individuals, groups, or entities who are involved in the Active Directory Domain Services (AD DS) Implementation and Management project. Their roles and responsibilities are essential for the successful execution and delivery of the project. In this section, we outline the primary project team members, their responsibilities, and the stakeholders who will be impacted by the project.

Project Team Members: 

| Role | Responsibilities |
|------|------|
| Project Manager (Scrum Master) | Develop the project plan and timelines, Coordinate with all team members and stakeholders, Track project progress, and make necessary adjustments. Manage risk, scope, and budget. Ensure that all deliverables are achieved as scheduled. |
| IAM Administrator	| Design the Active Directory structure (OUs, users, groups, and permissions), Implement user account configurations and organizational units, Set up and manage security policies and access control mechanisms, Perform troubleshooting and ensure a secure, stable environment, Remove obsolete OUs and update configurations as needed. |
|Systems Administrator | Manage server configurations (including CorpDC server), Set up and maintain the hardware and software infrastructure needed for AD DS, Provide system support for any issues related to Active Directory implementation, Assist in network connectivity and security for Active Directory. |
| IT Security and Compliance Specialist	| Define and implement security measures for user accounts and system access, Create and manage global security groups, Design security policies for password management and user restrictions, Perform audits to ensure compliance with internal security policies and external regulations. |
| Support and Helpdesk Technician | Provide technical assistance to users for login issues and account management, Resolve user account-related problems, such as access denial and permission issues, Maintain records of helpdesk tickets related to Active Directory issues. |


6.6 Communication Plan

Effective communication was vital for successful Agile project execution, particularly given the simulated environment's dynamic conditions.

Communication Plan:
| Audience | Information Type | Frequency | Communication Method |
|-----|-----|-----|-----|
| Project Team | Sprint progress, blockers, task assignments | Daily (standups) | Microsoft Teams, Email |
| Stakeholders (CTO, HR, Cybersecurity)	| Sprint progress updates, demo reviews	| Bi-weekly (Sprint Review)		Sprint Review Meetings (MS Teams and Demo) |
| Documentation Updates	| Project plans, technical runbooks | Weekly | Confluence, SharePoint | 
| Executive Reporting |	High-level project updates, risks, and milestones | Monthly	| Executive Summary Emails, Reports |



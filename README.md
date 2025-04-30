##	Project title: Active Directory Domain Services (AD DS) Implementation and Management for Organizational User and Resource Structure Using Agile Methodology 


##	Disclaimer Notice:
The use of the name "SidodatTech" in this project is for illustrative and educational purposes only. SidodatTech is a fictional company created for this project. Any resemblance to real companies or organizations and individuals, living or dead, is purely coincidental. The information provided is intended for educational and research purposes. SidodatTech and other names used in this project, do not endorse, sponsor, or approve of any of the content, methodologies, or recommendations presented herein. All opinions, conclusions, and recommendations expressed in this project are solely those of the author and do not represent the views or positions of any actual company or organization. By viewing or utilizing this project, the reader acknowledges and agrees to these terms and conditions.


##	Scenario Background: SidodatTech AD DS Implementation and Management
SidodatTech, a mid-sized cybersecurity consulting and SOC service provider, has recently expanded its operations across multiple regions and departments, including Security Operations, Threat Intelligence, Compliance & Governance, and Client Engagement. As a result of this rapid growth, the organization is facing increasing challenges in managing its user accounts, departmental access, and IT resource permissions.
Currently, SidodatTech uses a flat, decentralized user management structure, leading to several operational inefficiencies:

•	Lack of centralized control: User and computer accounts are created manually across individual workstations, resulting in inconsistencies, account duplication, and poor tracking.

•	Access control issues: Employees across different departments have overlapping or inappropriate access to confidential resources due to the absence of structured group policies or security scopes.

•	Ineffective user lifecycle management: There is no formal process for disabling, renaming, or resetting accounts when users change roles or leave the organization.

•	Security risks: Without a proper organizational unit (OU) structure and group strategy, the organization is exposed to unnecessary risk, including privilege escalation and data leakage.

•	Administrative overhead: IT staff spend excessive time handling repetitive tasks like user creation, password resets, and policy changes due to the lack of delegation and automation.

These gaps significantly impact operational efficiency, data security, and compliance readiness—particularly as the company seeks ISO 27001 certification and aims to support growing client demands.
To address these challenges, SidodatTech has commissioned a project to design and implement Active Directory Domain Services (AD DS). The solution will include the creation of OUs aligned with the company's departmental structure, structured user and computer account management, group policies, and administrative delegation.


##	Table of Contents

Executive Summary
Project Background
1. Introduction
2. Objectives
3. Scope
4. Project Methodology
5. Project Timeline
6. Roles and Responsibilities
7. Meetings and Communication Plan
8. Risk Management
9. Implementation Stages
10. Testing and Validation
11. Expected Outcomes and Success Criteria
12. Conclusion
13. References



##	Executive Summary

The increasing need for organizations to safeguard their digital infrastructure, protect sensitive information, and streamline user management processes has made it imperative for companies like SidodatTech to adopt structured identity and access management systems. At the core of this strategy is the implementation of Active Directory Domain Services (AD DS), a central directory service that helps manage network resources, enforce security policies, and ensure compliance with industry standards. This project focuses on the design, deployment, and management of AD DS to create a centralized environment that facilitates the organization’s growth while enhancing security, resource management, and operational efficiency.

The implementation process involved several key steps. Initially, the project team identified the departments within SidodatTech and mapped these departments to corresponding OUs within the domain controller. The IT team proceeded with the creation of computer accounts for essential devices, such as the Sales team's laptops, and configured user accounts according to role-based access control (RBAC) policies. Specific user account management tasks were carried out, including renaming accounts, resetting passwords, disabling accounts when necessary, and removing user restrictions that were applied in previous configurations.

Furthermore, the project focused on improving security by introducing global security groups and group policies to control access to sensitive resources. With clearly defined roles and permissions, the IT team was able to delegate administrative tasks and manage access based on the principles of least privilege. This not only increased security but also allowed for efficient handling of administrative duties, reducing the workload for senior IT personnel and empowering department-specific administrators to manage their resources autonomously.
This project will significantly enhance SidodatTech business operations by optimizing user and resource management, improving security, and reducing manual administrative tasks. By effectively managing Active Directory objects and establishing clear access control policies, the organization will experience improved operational efficiency, better compliance, and reduced risk of unauthorized access. The segregation of duties and delegation of administrative tasks will also reduce the risk of internal threats and streamline IT management. The AD DS infrastructure will also allow the company to scale its IT resources effectively, ensuring that new users, teams, and systems can be integrated seamlessly as the business grows. The optimized Active Directory environment will also improve collaboration among departments, enhancing internal productivity.

Ensuring business continuity is a priority in this project. By maintaining a structured Active Directory environment, the company will minimize disruptions during user and system provisioning. A robust backup and recovery plan will be implemented, ensuring quick restoration of services in case of system failure or accidental data loss. Additionally, regular updates and system audits will be conducted to maintain security and system integrity. The project will ensure that critical systems, such as the CorpDC server, remain operational with high availability, thereby minimizing downtime and ensuring employees have uninterrupted access to essential resources. Clear documentation of administrative processes will further enhance the speed and efficiency of recovery efforts.

In conclusion, this project will enhance the security, scalability, and efficiency of the organization’s Active Directory, with a focus on minimizing risk and ensuring business continuity. The result will be a streamlined, secure, and scalable IT infrastructure that supports growth while reducing administrative complexity.

##	Executive Summary
The increasing need for organizations to safeguard their digital infrastructure, protect sensitive information, and streamline user management processes has made it imperative for companies like SidodatTech to adopt structured identity and access management systems. At the core of this strategy is the implementation of Active Directory Domain Services (AD DS) on a Hyper-V guest server named CorpDC, hosted within the CorpNet.local domain. This central directory service supports network resource management, enforces security policies, and ensures compliance with industry standards. This project focused on the design, deployment, and management of AD DS to create a centralized environment that facilitates organizational growth while enhancing security, resource allocation, and operational efficiency. The deployment was carried out on CorpDC, the primary domain controller, hosted on Hyper-V, with CorpServer supporting supplementary functions such as DNS, DHCP, and File Services to reinforce domain functionality.

The implementation process involved several key steps. Initially, the project team identified departments within SidodatTech and mapped them to corresponding Organizational Units (OUs) within the CorpDC domain controller on CorpNet.local. The IT team then proceeded with the creation of computer accounts for essential devices—such as the Sales team's laptops—and configured user accounts in accordance with Role-Based Access Control (RBAC) policies. Specific account management tasks were carried out, including renaming user accounts, resetting passwords, disabling dormant accounts, and removing outdated restrictions from legacy configurations.
Security improvements were central to this project. Global security groups and Group Policy Objects (GPOs) were introduced within the CorpNet.local domain to control access to sensitive corporate resources managed by CorpDC. Clearly defined administrative roles and permissions enabled efficient delegation of tasks. This not only enhanced security by enforcing the principle of least privilege, but also reduced the workload on senior IT personnel by empowering department-level administrators to manage their respective resources within defined boundaries.

This project is expected to significantly elevate SidodatTech’s business operations by optimizing user and resource management, enhancing system security, and reducing manual administrative overhead. By effectively managing Active Directory objects and implementing standardized access controls on CorpDC, the organization will benefit from improved operational efficiency, better regulatory compliance, and a lower risk of unauthorized access. The delegation of administrative privileges and segregation of duties will further reduce internal security risks while streamlining IT workflows.

Ensuring business continuity was a key consideration throughout the project. By maintaining a well-structured Active Directory environment on CorpDC and deploying core services on CorpServer, SidodatTech is equipped to minimize disruption during user provisioning or system failures. A robust backup and recovery strategy has been integrated, ensuring swift restoration of services in the event of system outage or data loss. Regular updates and audits will be performed to uphold system integrity and maintain security baselines. These measures ensure that critical infrastructure, particularly the CorpDC domain controller, remains available and resilient to operational disturbances.

In conclusion, this project lays the foundation for a secure, scalable, and efficient Active Directory infrastructure within CorpNet.local, powered by Hyper-V guest servers CorpDC and CorpServer. The implementation minimizes risk, improves compliance, and supports business growth by reducing administrative complexity and strengthening internal security governance.


##	Project Background

In the rapidly evolving landscape of modern information technology, the implementation and management of a centralized identity and access management infrastructure is critical to the operational efficiency, security, and scalability of organizations. SidodatTech, a mid-sized technology firm specializing in managed IT services and cloud infrastructure solutions, has recognized the growing need to streamline its internal IT governance and resource management systems through the structured deployment of Active Directory Domain Services (AD DS) within a dedicated domain environment named CorpNet.local. To support this initiative, SidodatTech provisioned a Hyper-V guest server named CorpDC to serve as the primary domain controller for the CorpNet.local domain. This server is responsible for hosting the AD DS infrastructure, managing user and computer accounts, and enforcing security policies. A second Hyper-V guest server, CorpServer, was deployed to handle auxiliary services including DNS, DHCP, and file sharing, thereby ensuring redundancy and service continuity across the directory environment.

Historically, SidodatTech’s user and resource management had been executed in a decentralized manner, leading to duplicated administrative efforts, security misconfigurations, and inconsistent application of access controls. As the organization scaled, these inefficiencies began to manifest in increased IT support incidents, prolonged user onboarding times, and limited visibility into permission structures across departments. The absence of a unified directory service has also posed challenges in enforcing compliance with industry security frameworks such as ISO/IEC 27001 and NIST SP 800-53, particularly in the management of identity lifecycle and access rights delegation.

This project emerges as a strategic initiative to implement a robust AD DS environment hosted on CorpDC under the CorpNet.local domain, aligning with best practices in enterprise IT management. The goal is to create a secure, manageable, and scalable directory infrastructure that reflects SidodatTech’s departmental structure while enabling efficient user account provisioning, centralized resource access, and enforceable group policies. The deployment process includes the restructuring of Organizational Units (OUs), creation and management of security groups, and assignment of administrative roles using delegated permissions—facilitated and controlled through the CorpDC server.

By integrating AD DS into SidodatTech’s core infrastructure via CorpDC and CorpServer, the organization will not only enhance its IT service delivery but also lay the foundation for more advanced directory-integrated technologies such as Group Policy Object (GPO) automation, Role-Based Access Control (RBAC), and future hybrid identity federation with cloud platforms. This initiative is both a response to current operational challenges and a proactive measure to future-proof the organization’s digital infrastructure.

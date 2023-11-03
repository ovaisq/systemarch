# systemarch

System Architectural Design Diagrams etc...

* PaaS.md: Based on my recent experience in healthcare, I've observed that healthcare platforms are still a work in progress, often appearing as inflexible, disjointed monoliths with integrations haphazardly added, and modularization often an afterthought. Furthermore, integrating post-sales modules is a labor-intensive and resource-consuming task, especially when transitioning from one Electronic Medical Record (EMR) vendor to another.

	However, my thoughts returned to the idea of PaaS in the healthcare sector when I learned about Microsoft's introduction of Fabric for Healthcare. Despite the healthcare management technology field being saturated with monolithic systems, I believe that Microsoft Fabric offers new opportunities to address the existing gaps in patient care management technology. Instead of merely using EMR/EHR systems as glorified records of clinician-patient interactions, I envision creating integrations that leverage predictive analytics to significantly enhance patient healthcare outcomes. Within this framework (see diagram), I've identified one specific gap, which I've labeled as the "Special Sauce" within the red box. This service would utilize data analytics to provide a comprehensive insight into a patient's healthcare needs.

	Consider a scenario in which a small, rural, or urban hospital network serves an underserved population, treating patients who have previously navigated various healthcare networks. In such cases, patient data analytics can empower clinicians and outreach staff to swiftly outline the patient's healthcare journey, preventing them from bouncing between different healthcare entities.

* api_gwy.md: Simple API Gateway diagram

* complex_scim.md: Somewhat complex SCIM server architecture diagram

* scim_api_gwy.md: Basic SCIM server architecture diagram

* pub_sub.md: Pub/Sub Diagram

* 2017_2021_dev-vm-infra-designed-built-by-me.png
	* I architected and deployed this VMware vSphere bases Dev/Test VM infrastructure from scratch
	* This infra is used (still in production today) for development and testing of Gliffy Plugins 
		on Atlassian Hosted (Server/Multi-node Datacenter) platform: Jira and Confluence.
	* Using this infrastructure, I was able to reverse engineer some of the undocumented APIs, and
		automate installation of Plugins, run API and Performance tests.
	* The VMs are a mix of Linux, Windows Server, Windows 10, various RDBMS databases (PostgreSQL,
		MySQL, MS-SQL) and multi-node clusters.

* high-level-architecture-of-realtime-updates-to-lesson-plan.png
	* This is the architectural blueprint that visualizes, at a very high level, post re-factor/re-architected workflow of a learning path. This diagram captures the flexibility of the new architecture, one that can be scaled as would/does the AI/ML. I had my team implement this.

* multi-tenant-courses-workflow-mindmap.png
	* A mindmap of multi-tenant design pattern that we started out with, and later architected and implemented. 

* workflow_of_workflows.png
	* A workflows of workflows that visualizes impact of AI/ML learnings on both, the direction, and update of a learning path of a frontline/warehouse worker. All this is changed in near-realtime.

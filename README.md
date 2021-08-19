# systemarch
System Architectural Design Diagrams etc...

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

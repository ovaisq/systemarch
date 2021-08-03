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

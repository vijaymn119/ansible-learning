History of Ansible:
	Ansible is developed by “Micheal DeHaan” & it was initially released on Feb - 2012. RedHat has acquired Ansible in the year 2015. 

Introduction to Ansible:
	Ansible is an Open-Source IT configuration management, Deployment & Orchestration Tool. It aims to provide large productive gains to a wide variety of automation challenges. This tool is very simple to use yet powerful enough to automate complete multi-tier IT application environment. 
    “Version in use: 2.14.18”

Use cases of Ansible/Key Functional Area of Ansible/Core Capabilities of Ansible

Configuration Management:
- Ansible has started its journey with Configuration Management, enabling system administrators to manage and maintain systems in a consistent state.

Infrastructure Automation:
- Ansible can provision and de-provision infrastructure resources across cloud providers such as AWS (EC2, S3, etc.), Microsoft Azure, Google Cloud Platform (GCP), and many others.

Application Deployment & CI/CD:
- Ansible can be used to deploy applications on multiple virtual machines, cloud instances, or even Kubernetes clusters, making it a valuable component in CI/CD pipelines.

Network Automation:
- Ansible also supports network automation. It can communicate with network devices such as Cisco routers and switches, F5 load balancers, and various API gateways to configure and manage network infrastructure.

Extra points
    1. Security & Compliance: Ansible can enforce security baselines, apply patches, manage firewall rules, and perform compliance audits — ensuring systems meet organizational or industry standards.
    2. Orchestration: Orchestration means automating and managing a series of interdependent tasks across multiple systems so they work together smoothly — for example, provisioning servers, deploying an application, and then updating load balancers in sequence.

Ansible terms & terminologies:

Controller Machine:- The system where Ansible is installed and executed. It’s responsible for provisioning resources, running playbooks, and managing target nodes (also known as managed or worker nodes).

Inventory:- A file (usually inventory or hosts) that lists and defines the target machines (hosts) you want to manage. It can be static (INI/YAML file) or dynamic (from cloud or scripts).

Playbook:- The main file that defines automation tasks in YAML format. It describes what to do and where to do it — such as configuration, deployment, or orchestration steps.

Task:- The smallest unit of action in Ansible — a single operation performed on a host.
Example: installing a package, starting a service, or copying a file.

Module:- Reusable, small programs that perform specific tasks on managed nodes (like yum, apt, service, copy, user, etc.). Tasks call modules.

Role:- Ansible roles provide a well-defined framework & structure for setting your tasks, variables, handlers, metadata, templates, & other files. Making playbooks modular and reusable.

Play:- Execution of playbook is called as Play

Facts:- System information automatically collected by Ansible from managed nodes (e.g., OS version, IP address, memory, network interfaces).

Handler:- Special tasks triggered only when notified by other tasks — often used to restart or reload services when configurations change.

Plugins:- It’s a extra piece of code, you can write your own plugins. Extensions that add extra functionality to Ansible (e.g., connection plugins, callback plugins, lookup plugins). Users can also create custom plugins.

APIs:- Ansible APIs are interfaces used to interact with cloud services or external systems (e.g., AWS, Azure, GCP). They act as transport mechanisms for automation across platforms.

How Ansible works:
When you run a playbook, Ansible interprets the YAML file, connects to target nodes over SSH, runs Python-based modules on those nodes, gathers the results, and reports back — all without needing agents.

Detailed explanation how Ansible works: 

Whenever you run an Ansible playbook (a YAML file), Ansible performs the following steps:
    1. Parses the Playbook (YAML):
The playbook — written in YAML — defines tasks, hosts, and variables. Ansible reads and interprets this YAML syntax.

    2. Connects to Managed Nodes:
The Ansible controller machine connects to the managed (worker) nodes using SSH (for Linux/Unix) or WinRM (for Windows).
No agent is required on the worker nodes — Ansible is agentless.

    3. Executes Modules:
Each task in the playbook calls an Ansible module. These modules are Python scripts (or small programs) that Ansible temporarily transfers to the managed nodes.

    4. Runs and Removes Modules:
The module executes remotely (e.g., install a package, copy a file), sends the output/results back to the controller, and then deletes itself from the managed node.

    5. Reports Results:
The controller machine aggregates the results and displays whether each task was changed, ok, or failed.
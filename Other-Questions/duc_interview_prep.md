# Q1. Know in and out of these files - 

1. JenkinsFile - https://github.com/snbdevops/blog/blob/main/Other-Questions/sample-JenkinsFile.md 

2. DockerFile - https://github.com/snbdevops/blog/blob/main/Other-Questions/sample-DockerFile.md

3. Kubernetes manifest file - https://github.com/snbdevops/blog/blob/main/Other-Questions/sample-kubernetes-manifest-file.md

4. ansible-playbooks - https://github.com/snbdevops/blog/blob/main/Other-Questions/sample-ansible-playbook.md

# Q2. Explain Docker file instructions

Refer Q1.2

# Q3. Which .yaml files are mandatory in Ansible roles?

In Ansible, roles are a way to organize playbooks and other files in a standardized format. When creating an Ansible role, there are several directories and files that are part of the standard structure. However, not all of them are mandatory. Below are the **mandatory** files and directories that must be present for an Ansible role to function properly:

### Mandatory Files in Ansible Roles

1. **`tasks/main.yml`**
   - **Purpose**: This file contains the main tasks that the role will execute. The tasks defined here are the core of the role and describe what actions should be performed.
   - **Example**:
     ```yaml
     ---
     - name: Install Nginx
       apt:
         name: nginx
         state: present
     ```

2. **`meta/main.yml`**
   - **Purpose**: This file contains metadata about the role, including dependencies (if any). It's also where you define the minimum Ansible version or galaxy dependencies if required.
   - **Example**:
     ```yaml
     ---
     dependencies:
       - { role: common, tags: ['common'] }
     ```

### Optional but Commonly Used Files and Directories

While the following files are not strictly mandatory, they are commonly used and part of the best practices for organizing roles:

1. **`handlers/main.yml`**
   - **Purpose**: This file defines handlers, which are tasks triggered by `notify` directives from tasks in the `tasks/main.yml`.
   - **Example**:
     ```yaml
     ---
     - name: Restart Nginx
       service:
         name: nginx
         state: restarted
     ```

2. **`vars/main.yml`**
   - **Purpose**: This file contains variables that are used within the role. These variables are static and cannot be overridden during runtime.
   - **Example**:
     ```yaml
     ---
     nginx_package: nginx
     ```

3. **`defaults/main.yml`**
   - **Purpose**: Contains default variables that can be overridden by playbook-level variables or other higher-priority variable sources.
   - **Example**:
     ```yaml
     ---
     nginx_port: 80
     ```

4. **`files/`**
   - **Purpose**: This directory is used to store files that can be copied to the target machine via the `copy` or `template` module.
   - **Example**: You might place a custom `nginx.conf` file here.

5. **`templates/`**
   - **Purpose**: Stores Jinja2 templates that can be used with the `template` module to dynamically generate configuration files.
   - **Example**: `nginx.conf.j2` template.

6. **`roles/`**
   - **Purpose**: This directory stores other roles if the role depends on multiple sub-roles or additional functionality.

### Minimal Role Structure

Here’s a minimal role structure with only the mandatory files:

```
myrole/
├── tasks/
│   └── main.yml      # Mandatory file
├── meta/
│   └── main.yml      # Mandatory file
```

#### Complete Role Structure Example (Including Optional Files)

```shell
myrole/
├── tasks/
│   └── main.yml      # Mandatory
├── handlers/
│   └── main.yml      # Optional but common
├── templates/
│   └── nginx.conf.j2 # Optional
├── files/
│   └── myapp.conf    # Optional
├── vars/
│   └── main.yml      # Optional but common
├── defaults/
│   └── main.yml      # Optional but common
├── meta/
│   └── main.yml      # Mandatory
└── README.md         # Optional documentation
```

### Summary of Mandatory Files:
- **`tasks/main.yml`**: Contains the primary tasks for the role.
- **`meta/main.yml`**: Contains metadata for the role, including dependencies. 

These two files are the bare minimum for a role to work in Ansible.

# Q4. Explain the ansible playbook you have written and write the same now

Refer Q1.4
 
# Q5. What is Fork in Ansible
In Ansible, a **fork** refers to the parallelism or concurrency level used to run tasks on multiple hosts simultaneously. It determines how many hosts Ansible will manage at the same time during the execution of a playbook. By default, Ansible forks processes to handle up to **5 hosts** concurrently, but this number can be adjusted based on the size of your infrastructure and performance needs.

### Key Concepts of Fork in Ansible

1. **Parallelism**:
   - The **fork** setting allows Ansible to run tasks on multiple hosts in parallel, rather than sequentially. This helps in speeding up the deployment and execution of tasks across many machines.
   
2. **Default Fork Value**:
   - Ansible defaults to using **5 forks**, meaning it will handle up to 5 hosts at a time by default.
   
3. **Controlling Forks**:
   - You can control the number of forks by setting it in the **ansible.cfg** configuration file or by using the `-f` or `--forks` flag in the command line.

### Example of Fork in Ansible

#### 1. **Setting Forks in `ansible.cfg`**

You can adjust the number of forks in the Ansible configuration file:

```ini
# ansible.cfg
[defaults]
forks = 10
```

This will allow Ansible to run tasks on 10 hosts in parallel.

#### 2. **Setting Forks via Command Line**

You can also specify the number of forks directly when running a playbook using the `-f` flag:

```bash
ansible-playbook myplaybook.yml -f 20
```

This command will run the playbook on up to 20 hosts simultaneously.

### How Forks Work Internally
When Ansible executes a playbook, it "forks" separate processes to handle multiple hosts concurrently. For example, if you set `forks = 10`, Ansible will create 10 child processes, each managing a host, and will execute tasks in parallel on all 10 hosts.

If you have more hosts than the fork limit, Ansible will process them in batches. For example, if you are managing 50 hosts and set `forks = 10`, it will first handle 10 hosts, then the next 10, and so on, until all hosts are processed.

### Performance Considerations

- **Too few forks**: If you set a low fork value, it may result in slower task execution, as Ansible will manage fewer hosts at a time.
  
- **Too many forks**: If you set a very high fork value, it might overload your control machine (the machine running Ansible) and network resources, leading to performance degradation. The optimal number of forks depends on factors like:
  - Network bandwidth
  - The resources of your control machine (e.g., CPU, RAM)
  - The number of managed hosts

### Summary
- **Fork** controls the number of hosts Ansible can manage in parallel.
- Default value is **5**.
- Can be set in the **`ansible.cfg`** file or via the `-f` flag on the command line.
- Increasing forks can improve performance, but too many forks may overload your system.

 
# Q6. If you want to deploy any Application in AWS, so what all services you Will select or use for that Application 
 
# Q7. Difference between ALB and NLB? Both ELB's work on which OSI layer?
 
# Q8. If Netflix type of application is there then which of Elb we need to use for the same?
 
# Q9. What is Terraform core?
 
# Q10. Have you write custom Modules in Terraform?

# Q11. What is State file locking in Terraform?
 
# Q12. What is Canary and Blue Green deployment in Kubernetes?
 
# Q13. If you want to deploy Blue green deployment, so in .Yaml file where you need to specify or mention Blue green deployment?

# Q14. How you upgrade in EKS, please explain the steps

# Q15. Difference between stateful set and deployment in kubernetes?

# Q15. Steps involved in creating an EC2 instance.
 
# Q16. What is Terraform refresh?

# Q17. How to get IP Address of the running pod?



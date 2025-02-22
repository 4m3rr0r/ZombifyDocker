# Docker Privilege Escalation
This script attempts to exploit Docker containers for privilege escalation by utilizing Docker images that may allow access to the host filesystem with privileged privileges. It tests a predefined list of Docker images and checks if the system is vulnerable to privilege escalation via `chroot`.

## Docker Images Tested
The script tests the following Docker images for potential privilege escalation:
Python, Node, Go, PHP, Ruby, MySQL, Postgres, Redis, and more.

## How It Works

- **Check Docker Group**: The script checks if the current user is part of the `docker` group.
- **Check Local Docker Images**: It checks for available Docker images on the system. If no images are found, it attempts to pull the `ubuntu` image.
- **Privilege Escalation Attempt**: For each Docker image in the predefined list, the script checks if it can execute `chroot` inside the container with the host's filesystem, potentially escalating privileges.
- **Execution**: If successful, it launches a root shell with access to the host filesystem.

## Prerequisites

- Docker installed and running.
- User must be a member of the `docker` group to run the script without `sudo`.

1. Clone the repository:
   ```bash
   git clone https:/github.com/4m3rr0r/ZombifyDocker.git
   ```
   ```bash
   cd ZombifyDocker
   ```
2. Make the script executable:
   
   ```bash
    chmod +x ZombifyDocker.sh
   ```
3. Run the script:
   
   ```bash
    ./ZombifyDocker.sh
   ```

   

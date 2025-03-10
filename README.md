# Setup student VM's

## Create the VM template

At the start of a new academic year you update the script `setup_debian_vm_template.sh` in this repository with the new installation information for Debian, Docker Compose and Tailscale.

Then run the script from the ProxMox Terminal:

```bash
bash <(wget -qO- https://raw.githubusercontent.com/ronnymees/ProxMox-student-vms/refs/heads/master/scripts/setup_debian_vm_template.sh)
```
💡 This script will pause fot the installation of the OS, you should watch it in the console on ProxMox and wait for it to finish before hitting enter on the script to resume.

## Create the csv-file with student credentials

Create the csv-file `vms.csv` containing the student credentials vmid, name, user, password, ip 

```csv
vmid,name,user,password,ip
101,vm-student1,student1,passw0rd1,192.168.1.101
102,vm-student2,student2,passw0rd2,192.168.1.102
103,vm-student3,student3,passw0rd3,192.168.1.103
```

💡It is best to create this file in Excel and save it as .csv. In ProxMox create the file via `nano /root/vms.csv` and copy the contents via **CRTL+X**, **Y**, and **ENTER**.

## Clone the template for all student VM's

```bash
bash <(wget -qO- https://raw.githubusercontent.com/ronnymees/ProxMox-student-vms/refs/heads/master/scripts/deploy_vms.sh)
```

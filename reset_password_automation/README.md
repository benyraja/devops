# Password reset automation

This ansible scripts helps you to automate the reset password on target machines through a secured method. 
Below are the two limitations.
1. You need a individual system to perform the password encrytion using pass_lib pip package. That system must be ubuntu.
2. You can reset passwords only to Linux distribution machines. Windows is not supported.

In the ansible machine, where you are going to run the playbook, you have to configure the **/etc/ansible/hosts** file. 
Below are the two host groups you need to configure.
```
[ubuntu]
<ipaddress_of_ubuntu_machine> ansible_ssh_user= <user_name> ansible_ssh_pass= <system_password>

[target]
<ipaddress_of_target1> ansible_ssh_user= <user_name> ansible_ssh_pass= <system_password>
<ipaddress_of_target2> ansible_ssh_user= <user_name> ansible_ssh_pass= <system_password>
```

Please keep in mind that the username and password that you enter in the target host, must be root or with sudo access and should have access to reset password.

After you download the folder or the scripts, you have to run the below command.
```
$ sudo ansible-playbook ch_password.yml -e username= <system_username> -e  password= <your_password>
```
You can now login to the target machine and check whether the password is reset.

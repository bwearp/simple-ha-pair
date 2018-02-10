# simple-ha-pair
Using ansible and an xlsx spreadsheet to set up an HA pair

Requirements:<br>

<b>BIG-IP Requirements</b><br>
The BIG-IP devices will need to have their management IP, netmask, and management gateway configured<br>

They will also need to be licensed and provisionned with ltm. It is possible to both provision and license the devices with ansible but it is not within the remit of this project.

For additional information on Ansible and F5 Ansible modules, please see:
http://clouddocs.f5.com/products/orchestration/ansible/devel/index.html


<b>Ansible Control Machine Requirements</b>
<br>I am using Centos, other OS are available<br><br>
You will need Python 2.7+<br><br>
You will need pip<br>
curl 'https://bootstrap.pypa.io/get-pip.py' > get-pip.py && sudo python get-pip.py
<br><br>
You will need ansible 2.5+ <br> 
$ pip install ansible <br>

If 2.5+ is not yet available, which it wasn't at the time of writing,  please download directly from git <br>
$ yum install git <br>
$ pip install --upgrade git+https://github.com/ansible/ansible.git<br>
<br>
You will need f5-sdk >= 3.0.9, and a few other modules
<br>
$ pip install f5-sdk==3.0.9 bigsuds netaddr deepdiff request objectpath openpyxl

You will need to create and copy a root ssh-key to <em>BOTH</em> the bigip devices<br>
$ su<br>
$ ssh-keygen <br>
Accept the defaults<br>
$ ssh-copy-id -i /root/.ssh/id_rsa.pub root@\<bigip-management-ip\><br>

You will need to download the files using git - see above for git installation<br>
$ git clone https://github.com/bwearp/simple-ha-pair/ <br>
$ cd simple-ha-pair <br>

<em> Executing the playbook </em><br>

You will then need to edit the simple-ha-pair.xlsx file to your preferences

Then execute the playbook

$ ansible-playbook simple-ha-pair.yml

NOTES:

The HA VLAN must be called 'HA'<br>
The settings where yes/no are required must be yes/no and not YES/NO or Yes/No<br>
One device must have primary=yes and the other must have primary=no

I have added only Standard Virtual Servers with http, client & server ssl profiles, but hopefully it is pretty obvious from the simple-ha-pair.yml playbook how to add in others.

I haven't added in persistence settings, as this would require a dropdown list of somekind. I will probably add it later.

Automation does not sit well with complication

To update if there are any changes, please cd to the same folder and run:<br>
$ git pull



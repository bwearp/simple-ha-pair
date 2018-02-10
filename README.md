# simple-ha-pair
Using ansible and an xlsx spreadsheet to set up an HA pair

Requirements:<br>

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

You will need to create and copy a root ssh-key to BOTH the bigip devices<br>
$ su<br>
$ ssh-keygen <br>
Accept the defaults<br>
$ ssh-copy-id -i /root/.ssh/id_rsa.pub root@\<bigip-management-ip\><br>

You will need to download the files using git - see above for git installation<br>
$ git clone https://github.com/bwearp/simple-ha-pair/ <br>
$ cd simple-ha-pair <br>

You will then need to edit the simple-ha-pair.xlsx file to your preferences

Then execute the playbook

$ ansible-playbook simple-ha-pair.yml



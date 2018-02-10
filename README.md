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









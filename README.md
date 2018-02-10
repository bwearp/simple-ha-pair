# simple-ha-pair
Using ansible and an xlsx spreadsheet to set up an HA pair

Requirements:<br><br>

You will need ansible 2.5 <br> If it is not yet available, which it wasn't at the time of writing,  please download directly from git <br>
$ pip install ansible
$ pip install --upgrade git+https://github.com/ansible/ansible.git
<br>
You will need f5-sdk >= 3.0.9, and a few other modules
<br>
$ pip install f5-sdk=3.0.9 bigsuds netaddr deepdiff request







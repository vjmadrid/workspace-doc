# Installation / Configuration Ansible Plugins



Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install ansible-cmdb](#ansible-cmdb)






## <a name="check-prerequisites">Check Prerequisites</a>

Check the following points before installing :

* Verify the version of Python installed
* Verify that you are in the established virtual environment.





## <a name="ansible-cmdb">Install ansible-cmdb</a>

Web interface to visually display the state of machines by defining a CMDB

 * Generate the output of ansible events and convert it into static HTML
 * Generate multiple outputs : HTML, CSV, SQL, etc.

https://github.com/fboender/ansible-cmdb

```bash
# Intallation
pip3 install ansible-cmdb

# Generate hosts information
ansible -m setup --tree out/ all

# Generate HTML 
ansible-cmdb out/ > overview.html
```
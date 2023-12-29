# Configuration VSC




## Extensions Backup

Create list of extensions

```bash
code --list-extensions > extensions.txt
```

Create script: **generate-extensions-backup.sh**


## Install Extensions


```bash
#!/usr/bin/env bash

cat extensions.txt | while read extension || [[ -n $extension ]];
do
  code --install-extension $extension --force
done
```


Create script: **install-extensions.sh**

Execute


```bash
./install-extensions.sh
```

Permissions

```bash
sudo chmod u+x install-extensions.sh
```




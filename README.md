## Features

  * dump multiple databases
  * dump each database into a different file
  * Kubernetes scheduled jobs examples for automatic backup of databases

## Usage :

### Kubernetes scheduled jobs

Notes:

  * Edit ConfigMaps and Secrets according to your environment. Values in secrets have to be base64 encoded.
  * Edit the `scheduledjobs` definitions to set backup location or change the linux user:

#### Backup one or more databases

1. To dump all databases use "mysqldump.scheduledjob.all.yaml" example. Also has an option to exclude one database from backup.

2. Create secret, configmap and job(s)

             kubectl create -f mysqldump/mysqldump.configmap.yaml
             kubectl create -f mysqldump/mysqldump.secret.yaml
             kubectl create -f mysqldump/mysqldump.scheduledjob.all.yaml

references : https://github.com/camilb/kube-mysqldump-cron
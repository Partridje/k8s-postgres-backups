# PostgreSQL Backup Helm Chart

This Helm Chart is designed to create backups of PostgreSQL databases using Kubernetes CronJobs.
### NOTE: :construction: Currently, this chart is still in development 	:building_construction:

## Installation and Configuration

```bash
# Clone this repository
git clone https://github.com/Partridje/k8s-postgres-backups.git
```

# Navigate into the repository directory
```
cd postgres-backup-helm
```

Modify `values.yaml` to suit your databases and schedule. The following parameters are outlined in the `values.yaml` file:

| Parameter | Description |
| --------- | ----------- |
| `databases[].name` | Name of the database |
| `databases[].host` | Host of the database |
| `databases[].username` | Username for database connection |
| `databases[].secretName` | Name of the Kubernetes secret containing the password for database connection |
| `databases[].secretKey` | Key in the secret containing the password |
| `databases[].schedule` | Schedule for backup creation in cron format |
| `pvc.name` | Name of the PersistentVolumeClaim |
| `pvc.accessModes` | Access modes for the PersistentVolume |
| `pvc.size` | Size of the PersistentVolume |

Next, install the Helm chart:

```bash
helm install postgres-backup ./postgres-backup -f values.yaml
```

## Notes

- This Helm chart does not automatically create secrets. You need to manually create secrets with database passwords before installing the Helm chart.
- This Helm chart does not automatically create a PersistentVolumeClaim. You need to create it manually or use an existing one.

Please refer to the [Russian version](README_RU.md) for instructions in Russian.

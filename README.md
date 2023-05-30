# PostgreSQL Backup Helm Chart

Этот Helm Chart предназначен для создания резервных копий PostgreSQL баз данных с помощью Kubernetes CronJobs.

## Установка

Склонируйте этот репозиторий и установите Helm chart следующим образом:

```bash
git clone https://github.com/yourusername/postgres-backup-helm.git
cd postgres-backup-helm
```

#### Перед установкой убедитесь, что вы изменили values.yaml, чтобы он соответствовал вашим базам данных и расписанию.

#### Для установки Helm chart выполните:
```
helm install postgres-backup ./postgres-backup -f values.yaml
```

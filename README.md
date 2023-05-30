# PostgreSQL Backup Helm Chart

Этот Helm Chart предназначен для создания резервных копий PostgreSQL баз данных с помощью Kubernetes CronJobs.

## Установка

Склонируйте этот репозиторий и установите Helm chart следующим образом:

```bash
git clone https://github.com/yourusername/postgres-backup-helm.git
cd postgres-backup-helm
```

Перед установкой убедитесь, что вы изменили values.yaml, чтобы он соответствовал вашим базам данных и расписанию.

Для установки Helm chart выполните:
```
helm install postgres-backup ./postgres-backup -f values.yaml
```
Измените values.yaml, чтобы он соответствовал вашим базам данных и расписанию. В файле values.yaml указаны следующие параметры:

| Параметр | Описание |
| -------- | -------- |
| `databases[].name` | Имя базы данных |
| `databases[].host` | Хост базы данных |
| `databases[].username` | Имя пользователя для подключения к базе данных |
| `databases[].secretName` | Имя секрета Kubernetes, который содержит пароль для подключения к базе данных |
| `databases[].secretKey` | Ключ в секрете, который содержит пароль |
| `databases[].schedule` | Расписание для создания резервных копий в формате cron |
| `pvc.name` | Имя PersistentVolumeClaim |
| `pvc.accessModes` | Режимы доступа к PersistentVolume |
| `pvc.size` | Размер PersistentVolume |


##### Заметки

* Данный Helm chart не создает секреты автоматически. Вы должны создать секреты с паролями баз данных вручную перед установкой Helm chart.
* Данный Helm chart не создает PersistentVolumeClaim автоматически. Вы должны создать его вручную или использовать уже существующий.

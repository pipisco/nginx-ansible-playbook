# Nginx Ansible Playbook
Давнный playbook демонстрирует настройку nginx video streaming серверов, в колличестве 20 штук. Playbook облегчает работу по быстрой настройке, применению изменений конфигураций или просто рестарта сервисов.

## Примеры
### Streaming
Пример настройки стриминга HLS: а также отдачи mp4 стрима с ограничением скорости и выставлением временной secure ссылки, можно просмотреть в `roles/files` директории для любого из 20-и серверов.

### Глобальная установка  
Для глобальной установки nginx необходимо выполнить запуск playbook

```shell script
ansible-playbook --limit=production -i inventory/hosts roles/main.yml
``` 

### Применение глобальных настроек
```shell script
ansible-playbook --limit=production --tags=configure -i inventory/hosts roles/main.yml 
```

### Применение настроек sites
```shell script
ansible-playbook --limit=production --tags=update-sites -i inventory/hosts roles/main.yml 
```
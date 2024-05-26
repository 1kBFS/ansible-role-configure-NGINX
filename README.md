Реализация идемпотентной Ansible-роли, позволяющая автоматизировать следующие действия:

1. Установка nginx, cron, jq
2. Настройка и обеспечение запуска Nginx  таким образом, чтобы `GET /service_data` отдавал ` /opt/service_state.json`
3. Настройка изменения значений в файле `/opt/serivce_state.json`

Файл `/opt/service_state.json` выглядит следующим образом: 
```
{  
	"title": "Seems working",  
	"uptime": 0  
}
```

Решение протестировано и работает на `Ubuntu 22.04`,`Centos 7`. Для автоматизации работы с виртуальными машинам, на которых тестировалась Ansible-Role, использовался IaC `Vagrant`

Свойства: 
1. Повторный запуск ansible с той же конфигурацией не сбрасывает значение uptime в файле /opt/service_state.json и не перезапускает nginx
2. После изменения поля `title` в шаблоне в файле `/opt/service_state.json`  происходит обновление `/opt/service_state.json` и рестарт nginx. 

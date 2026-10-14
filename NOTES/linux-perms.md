# Linux: права и пользователи

## Кто я
- `whoami` — имя
- `id` — UID, GID, группы
- `groups` — список групп

## Мои группы
- alehandro, http, power, docker, input, wheel

## Права (chmod)
- `chmod 755 file` — rwxr-xr-x
- `chmod 644 file` — rw-r--r--
- `chmod +x file` — добавить исполнение
- `chmod -x file` — убрать исполнение
- **Числа:** r=4, w=2, x=1

## Владелец (chown)
- `chown user:group file` — сменить владельца
- **Только root** может менять владельца

## Процессы
- `ps aux` — все процессы
- `ps aux | grep nginx` — найти nginx
- `ss -tulnp` — порты и процессы

## Systemd
- `systemctl status nginx` — статус
- `systemctl start/stop/restart/reload nginx`
- `systemctl enable nginx` — в автозапуск
- `systemctl list-units --type=service --state=running`

## Сервисы, которые я знаю
- nginx, docker, sshd, php-fpm, containerd, NetworkManager, lightdm

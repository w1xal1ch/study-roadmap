# Linux: файловая система

## Ключевые директории
- `/` — корень
- `/home` — домашние директории юзеров
- `/boot` — загрузчик (GRUB, ядро)
- `/etc` — конфиги
- `/var` — переменные данные (логи, кеш)
- `/tmp` — временные файлы
- `/usr` — программы, библиотеки
- `/opt` — опциональные программы
- `/root` — домашняя директория root
- `/srv` — данные сервисов
- `/proc`, `/sys` — виртуальные ФС

## Команды навигации
- `ls -la` — список файлов, включая скрытые, с правами
- `cd` — переход
- `pwd` — текущая директория
- `find /path -name "*.conf"` — поиск файлов
- `find /path -name "*.conf" 2>/dev/null` — без ошибок

## Команды просмотра
- `cat` — весь файл
- `less` — листать
- `head -N` — первые N строк
- `tail -N` — последние N строк
- `grep "pattern"` — поиск по тексту
- `grep -E "pattern1|pattern2"` — поиск по регулярке

## Логи
- `/var/log/` — логи
- `/var/log/nginx/` — логи Nginx (access.log, error.log)
- `/var/log/journal/` — логи systemd-journal
- `/var/log/pacman.log` — лог pacman (Arch)

## Конфиги, которые я знаю
- `/etc/nginx/` — Nginx
- `/etc/ssh/` — SSH
- `/etc/ufw/` — UFW
- `/etc/hosts` — локальные имена
- `/etc/grub/` — GRUB
- `/etc/lightdm/` — LightDM
- `/etc/mkinitcpio.conf` — initramfs (Arch)

## Команды просмотра (дополнено)
- `less` — листать файл (q — выход, /pattern — поиск)
- `tail -f` — следить в реальном времени (Ctrl+C — выход)

## Команды поиска (дополнено)
- `grep -i` — без учёта регистра
- `grep -r` — рекурсивно
- `grep -v` — инвертировать (исключить)
- `grep -E` — регулярка
- `find -type f` — только файлы
- `find -type d` — только директории
- `find -mtime -1` — изменённые за 24 часа
- `find -size +10M` — больше 10 МБ
- `find -maxdepth 1` — только на одном уровне

## Nginx: что я вижу в конфиге
- `events` — настройки соединений
- `http` — HTTP-сервер
- `server` — один сайт
- `location` — путь внутри сайта
- `proxy_pass` — куда перенаправлять
- **Важно:** `proxy_pass http://127.0.0.1:8001/acs/` — слэш в конце — причина бага Access

## Логи (дополнено)
- `/var/log/boot.log` — загрузка
- `/var/log/pacman.log` — пакеты Arch
- `/var/log/Xorg.*.log` — X-сервер
- `/var/log/journal/` — systemd-journal

## Кеш пакетов
- `/var/cache/pacman/pkg/` — кеш пакетов Arch
- Чистить: `paccache -r`

## Мои ошибки (14.10)
- `find` требует `-name` для поиска по имени
- `grep` — для текста, `find` — для файлов
- `head`/`tail` работают с файлами напрямую
- Флаги в find с дефисом: `-type`, `-maxdepth`
- `cat` не фильтрует, для этого `grep`

# DevOps Notes

## 1. Введение
- Цель конспекта: практика Linux, Git, Docker, CI/CD и облачные сервисы.
- Рабочая среда: Ubuntu (система на отдельном разделе), GitHub (репозиторий для конспекта), SSH.

---

## 2. Linux Basics
### 2.1 Системная информация
- `lsb_release -a` — показать версию Ubuntu
- `whoami` — текущий пользователь
- `hostname` — имя компьютера
- `pwd` — текущая директория

### 2.2 Работа с файлами и директориями
- `ls -lh` — список файлов с размером
- `ls -lha` — список всех файлов (включая скрытые)
- `cd <папка>` — переход в папку
- `mkdir <папка>` — создать папку
- `rm -rf <папка>` — удалить папку полностью (осторожно!)
- `df -h` — проверка свободного места

---

## 3. Git Basics
### 3.1 Инициализация и коммиты
- `git init` — инициализация репозитория
- `git add <файл>` — добавить файл в индекс
- `git commit -m "сообщение"` — создать коммит
- `git branch -M main` — переименование ветки в main

### 3.2 Работа с удалённым репозиторием
- HTTPS:
  - `git remote add origin <URL>` — подключение удалённого репо
  - `git push -u origin main` — пуш изменений (PAT вместо пароля)
- SSH:
  - `ssh-keygen -t ed25519 -C "email" -f ~/.ssh/id_ed25519_devops`
  - `cat ~/.ssh/id_ed25519_devops.pub` — копирование публичного ключа
  - `ssh -T git@github.com` — проверка соединения
  - `git remote set-url origin git@github.com:username/DevOpsNotes.git`
  - `git push -u origin main` — пуш без пароля

---

## 4. Docker
### 4.1 Установка
- `sudo apt update`
- `sudo apt install docker.io`
- `sudo systemctl start docker`
- `sudo systemctl enable docker`
- `docker --version` — проверить версию

### 4.2 Основные команды
- `docker ps` — список контейнеров
- `docker images` — список образов
- `docker run -it <image> bash` — запустить контейнер
- `docker stop <container>` — остановка контейнера
- `docker rm <container>` — удалить контейнер
- `docker rmi <image>` — удалить образ

---

## 5. Docker Compose
- `sudo apt install docker-compose`
- `docker-compose up -d` — поднять сервисы
- `docker-compose down` — остановить и удалить сервисы

---

## 6. CI/CD
- Основные инструменты: GitHub Actions, GitLab CI, Jenkins
- Примеры конфигураций, пайплайнов

---

## 7. Облачные сервисы
- Yandex Cloud, AWS, Azure
- Создание виртуальных машин, настройка сетей, деплой сервисов

---

## 8. Kubernetes (k8s)
- minikube / k3s / kubeadm
- Основные команды:
  - `kubectl get pods`
  - `kubectl get services`
  - `kubectl apply -f <file.yaml>`
  - `kubectl delete -f <file.yaml>`

---

## 9. Полезные утилиты
- `htop` — мониторинг процессов
- `curl` — проверка HTTP-запросов
- `wget` — скачивание файлов
- `nano` / `vim` — редактирование файлов
- `tar`, `zip`, `unzip` — архивирование


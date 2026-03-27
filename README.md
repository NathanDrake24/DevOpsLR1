# Docker-стек: Python-приложение + PostgreSQL
---

## Подготовка
переходим по ссылке https://www.docker.com/products/docker-desktop/
и скачиваем Docker Deskstop

Заходим в Microsoft Strore и устанавливаем Ubuntu (Для упрощения работы с линукс)

<img width="1008" height="379" alt="image" src="https://github.com/user-attachments/assets/05ba346a-d48f-4521-90a3-b9efb5fa6b75" />


---

## Регистрация

После перезагрузки нужно зайти в докер декстоп и пройти регистрацию

---

## Установка и настройка WSL

## 1. **Установка WSL2** (в PowerShell от имени администратора):
   ```powershell
   wsl --install
   ```
   
    или

   ```powershell
   wsl --update
   ```

<img width="413" height="94" alt="image" src="https://github.com/user-attachments/assets/877087e8-61fa-4f14-9042-9fb7c1dbe335" />

   
   
   
---
## 2.  Перезапуск пк
---
## 3. Обновление системы внутри WSL

Запускаем Ubuntu например через поиск. В нем пишем команду 

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
и ждем окончание обновления

---
## 4. Установка Docker и docker-compose
   
   4.1 Установка зависимостей
   ```bash
   sudo apt install -y ca-certificates curl gnupg lsb-release
   ```
   4.2 GPG-ключ
   ```bash
   sudo mkdir -p /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   ```
   4.3  Добавление репозитория
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 ```
   4.4 Установка docker
 ```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
 ```
   4.5 Проверка
   ```bash
   docker --version
   docker compose version
   ```
   <img width="488" height="74" alt="image" src="https://github.com/user-attachments/assets/75e6e31d-6e70-4e86-a6a8-a6f9d0d83d4c" />
   <img width="372" height="43" alt="image" src="https://github.com/user-attachments/assets/2f5a6712-4324-4703-a920-1f45ca93e23d" />
   
   4.6 Добавляем себя в группу докер, чтобы не прописывать sudo
   ```bash
   sudo usermod -aG docker $USER
   ```
---

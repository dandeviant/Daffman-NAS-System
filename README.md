# DAFFMAN: a Python-based Debian File Manager

<b>(short for Daniel's Flask File Manager)</b>

---

GitHub repository: https://github.com/dandeviant/Flask-file-manager

Progress so far...<br>
- Data deduplication is completed via Python MD5, but client-side process is not possible.<br>
- Server-side AES encryption during upload is completed. Using pyAesCrypt with .aes extension
- For now, every process is server-side only.<br>
- Login and profiling is completed, only small additions are needed for better UX<br>
- Users are not allowed to modify or upload in folder not belong to them, except admin<br>
- Folders for new users will be created upon registration<br>
- Passwords for files is user's password<br>
- Password is hashed using SHA256 algorithm, to be updated in Chapter 2 and 3<br>
- Download popup to input decrypt password, download only when password is correct (incomplete, broken popup error)
<br>

Next task:<br>

- Add change password features for all user<br>
- Complete upload page<br>
- Configure Raspberry Pi remote storage using SAMBA and connect to this PyFlask server: 

https://www.circuitbasics.com/making-a-nas-with-samba-and-raspberry-pi/<br>
<br>

Later:<br>
- ========================================================================<br>
- Do not allow files with same contents for storage, even for files with different names<br>
- The process happens during upload process<br>
- If file has different name, but same contents with files in database, ABORT UPLOAD and display error message.<br>
- SELECT * FROM hash where md5=" " - to list all files with same content<br>
- In the error message box, list out all file names with similar contents if found<br>
- ========================================================================<br>
- If you are to use client-side MD5 checking, create another page for file upload<br>
- Display errors of fileexist in the page, not in browser page<br>
<br>

---

### About

1. DAFFMAN is a NAS file manager built on Python and built for Debian Linux system running Bash/ZSH shell
2. This project actually started as my side timekiller during COVID lockdown
3. Now I've improved this project for my final year project
4. The system is fully Debian-based/Ubuntu-based (Ubuntu, Mint OS, etc.) as far as I have tested<b>
    - DO NOT RUN ON ANY OTHER OPERATING SYSTEM UNLESS YOU KNOW WHAT YOU'RE DOING</b>

---

### System Preview Image

File Browser Page - Folder Section<br>
![browser-preview](https://user-images.githubusercontent.com/68473358/209222789-4dc5b62a-fab2-41e2-9a2f-f3595fc62485.png)

File Browser Page - File Section<br>
![browser-preview2](https://user-images.githubusercontent.com/68473358/209222849-b7df5633-e66b-4147-8257-9832d63d6e67.png)

---

### How to run the app in development env
<code>$ python3 flask-manager.py</code><br>
<b>OR</b><br>
<code>$ flask --app flask-manager.py run</code>

Gonna look into gunicorn to deploy this app locally from my Raspberry Pi server

---

### Added/Planned features:

1. File download/upload (completed)
2. User profiling with session login (incomplete)
3. MD5 file deduplication  (completed || server-side only)
4. AES encryption using Python modules (incomplete)

---

### Python Modules (installed thru pip3):

1. Python Flask framework
2. Flask Markdown
3. werkzeug.utils (secure_filename)
4. hashlib
5. mysql-connector-python (import mysql.connector)
6. pyAesCrypt
    - pyAesCrypt is a AES Crypt module integrated with Python.<br>
    - It uses AES-256-CBC encryption mode<br>
    - It can also be used directly from the terminal<br>

---

### Other Requirements:

1. MySQL database for user profiling and hash checking
2. Bootstrap CSS framework for UI (config files in folder 'static'). DO NOT TOUCH THAT FOLDER
3. SVG Source: <a href="https://www.svgrepo.com/" target="_blank">SVG Repo</a>


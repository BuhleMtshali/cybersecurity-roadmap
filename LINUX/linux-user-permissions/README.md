## 👤 User Management Mini Project 

## 📌 Objective  

- Practice creating, managing, and securing Linux users directly from the terminal.  

- This exercise helps build foundational sysadmin + security skills that are essential in SOC & security data engineering roles.  

---

## 🛠️ Steps Performed

### 1️⃣ Create a new user with home directory

```

sudo useradd -m username

```

### 2️⃣ Set a password for the user

```

echo "username:Password123" | sudo chpasswd

```

### 3️⃣ Verify the user was created

```
grep zano /etc/passwd

id zano

```

### 4️⃣ Switch to the new user

```
su - zano

whoami

```
- NOTE: 
    - You might see a ``` $ ``` (super minimal) after you run this command, this might because the user's default shell is:

    -  ``` /bin/sh ```, and not ```/bin/bash ```

    - To get the "fancy" terminal 😜 like: ```user@kali```, basically get the bash terminal, run this as root:

    ``` chsh -s /bin/bash zano ```

    - Now when you run: ``` su - user ``` , you get the bash terminal
    

### 5️⃣ Set strict permissions on home directory

```

sudo chmod 700 /home/zano

```


## 📂 Commands Explained

- ``` useradd -m zano ``` → creates user zano with a home folder.

- ``` chpasswd ``` → changes password from zano123.

- ``` /etc/passwd ``` → file storing user account info.

- ``` chmod 700 ``` → only the user can access their home directory.

- ``` su ``` - zano → switch to that user’s environment.


## ✅ Output Example

- New user zano exists in ``` /etc/passwd ```

- Switching to zano shows ``` $ whoami ``` → zano

- Home folder ``` /home/zano ``` locked down with 700 permissions


## 🚀 Reflection

- This project taught me:

    - How Linux manages users.

    - The difference between root vs normal users.

    - How file permissions keep accounts private.

    - Next step: writing a Bash script to automate this process.

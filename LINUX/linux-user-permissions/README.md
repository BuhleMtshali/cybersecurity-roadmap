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
grep user /etc/passwd

id user

```

### 4️⃣ Switch to the new user

```
su - user

whoami

```
- NOTE: 
    - You might see a ``` $ ``` (super minimal) after you run this command, this might because the user's default shell is:

    -  ``` /bin/sh ```, and not ```/bin/bash ```

    - To get the "fancy" terminal 😜 like: ```user@kali```, basically get the bash terminal, run this as root:

    ``` chsh -s /bin/bash user ```

    - Now when you run: ``` su - user ``` , you get the bash terminal


### 5️⃣ Set strict permissions on home directory

```

sudo chmod 700 /home/user

```


## 📂 Commands Explained

- ``` useradd -m user ``` → creates user zano with a home folder.

- ``` chpasswd ``` → changes password from user password.

- ``` /etc/passwd ``` → file storing user account info.

- ``` chmod 700 ``` → only the user can access their home directory.

- ``` su ``` - user → switch to that user’s environment.


## ✅ Output Example

- New user exists in ``` /etc/passwd ```

- Switching to user shows ``` $ whoami ``` → user

- Home folder ``` /home/user ``` locked down with 700 permissions


## 🚀 Reflection

- This project taught me:

    - How Linux manages users.

    - The difference between root vs normal users.

    - How file permissions keep accounts private.

    - Next step: writing a Bash script to automate this process.

- Next step: writing a Bash script to automate this process.
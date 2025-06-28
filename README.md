# 🔐 Password Vault – Secure Desktop Credential Manager

A full-featured desktop app to store, manage, and protect your passwords using industry-standard encryption and a modern GUI. Built with Python (Tkinter) and MySQL, this vault application ensures your sensitive credentials stay safe and accessible — only to you.

---

## 🎥 Demo

> [Click to watch full demo (1 min 26 sec)] 

https://github.com/user-attachments/assets/e428e0b8-1bce-4eae-b720-5d7f83843eba



## 🖼️ Screenshots

| [App GUI Screenshot] ![Screenshot 2025-06-08 at 03 01 20](https://github.com/user-attachments/assets/4644b353-68ce-4ca0-8b63-9e969f49e243 =250x200)| [Encrypted Passwords in MySQL] ![Screenshot 2025-06-08 at 03 07 04](https://github.com/user-attachments/assets/90548663-0f27-4632-95de-a3503e51ef5f)|
|:--:|:--:|
| **Main Vault Interface** | **Encrypted Passwords Stored in DB** |

---

## 🚀 Features

- 🔐 **User Registration and Login**  
  - Master password is securely hashed using PBKDF2 with SHA-256.
  - Login protects access to the entire vault.

- ✍️ **Save New Credentials**  
  - Store website name, username, and password.
  - Passwords are encrypted before saving.

- 👁️ **View Password (with Master Password)**  
  - Re-authentication required before revealing stored passwords.

- ✏️ **Edit and Delete Credentials (secure)**  
  - Both actions require entering the master password.

- 👁️‍🗨️ **Toggle Password Visibility**  
  - Show/hide password while typing new credentials.

- 🎨 **Modern Dark Theme GUI**  
  - Styled using the 'clam' theme for clean and sharp UI.
  - All widgets follow a black-grey-white color scheme.

---

## 📁 Project Structure

- **`gui.py`** – GUI layout and event handling using `tkinter`. Manages input fields, buttons, layout structure, and opens modal windows (e.g., for master password, edit, delete).
- **`app.py`** – Main launcher file that starts the application and integrates all modules.
- **`db.py`** – Handles all MySQL database operations:
  - Connecting to the database
  - Inserting, updating, deleting credentials and user data
- **`encryption.py`** – Handles all security-related logic:
  - Master password is hashed using **PBKDF2 with SHA-256**
  - Credential passwords are encrypted and decrypted using **Fernet (symmetric encryption)**
- **`db_setup.sql`** – SQL file to set up the MySQL database:
  - Creates tables like `users`, `credentials`, and `security_questions`
  - Defines relationships and constraints
- **`requirements.txt`** – Lists all the Python dependencies required to run the project:
  - `tkinter`
  - `cryptography`
  - `mysql-connector-python`
- **`README.md`** – You’re reading it! 😄 This file explains the project, features, setup instructions, and usage.

---

## 🔧 Tech Stack

| Layer        | Technology                             |
|--------------|-----------------------------------------|
| Language     | Python 3.x                              |
| GUI          | Tkinter + tk                          |
| DB           | MySQL                                  |
| Encryption   | `cryptography.fernet` for credentials   |
| Hashing      | PBKDF2-HMAC-SHA256 for master password |
| UI Theme     | `clam` dark theme using ttk.Style       |

---

## 🧠 Security Implementation

- **Master Password**  
  - Stored as a **salted hash** using `PBKDF2-HMAC-SHA256` with a unique salt per user.
  
- **Stored Credentials**  
  - Passwords encrypted using **Fernet symmetric encryption** (AES under the hood).
  - Keys securely derived and stored in MySQL.
  
---

## 📜 Setup Guide

### 1. Clone the Repository

git clone https://github.com/DevanshuHB
cd password-vault

### 2. Set Up MySQL
- Make sure MySQL is installed and running.
* Run the provided SQL file:
> SOURCE [db_setup.sql](https://github.com/DevanshuHB/Password-Vault/blob/main/db_setup.sql);

### 3. Install Dependencies

Install the required Python libraries using:

```bash
pip install -r requirements.txt
```

Make sure you have Python 3.x installed. If `pip` doesn't work, try:

```bash
pip3 install -r requirements.txt
```

> 💡 This installs all required modules like `tkinter`, `mysql-connector-python`, etc.

### 4. Run the code
```bash
python gui.py
```

## 🔐 Folder Security Tip

- Never share your .env file or database credentials publicly.
- Avoid pushing __pycache__, .db files, or any sensitive tokens if added later.

## 🚀 Future Improvements

- 🔍 Add search functionality to find credentials quickly.
- ❓ Implement "Forgot Master Password" feature using security questions.
- 📦 Package the app as an executable for easier distribution.
- 🌙 Add dark/light theme toggle for user preference.
- 🔒 Improve encryption strategy with salting per credential.

## About The Author

### Devanshu Bansode

🧑‍🎓 2nd Year Engineering Student @ SIES GST

💻 Python Developer | Cybersecurity Enthusiast |

🌐 [**LinkedIn**](https://www.linkedin.com/in/devanshu-bansode-bb6a84320) | [**GitHub**](https://github.com/DevanshuHB)

## ⭐️ Like this project?

If this helped you, star the repo and consider sharing it — every ⭐ counts!

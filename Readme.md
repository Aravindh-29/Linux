**🔥 SEGMENT 7: User & Group Administration — Kadapa slang lo full clarity & realtime examples**

---

### 🧠 1️⃣ Basic Idea

👉 Linux lo **multi-user operating system**.
Ante **okka system lo chala mandhi users login ayi work cheyyachu** — but vallandaru ki **different permissions, passwords, folders** untayi.

Kadapa slang lo:

> “Mava, Linux ante hostel la ra. Oka building lo chala mandhi students untaru kani prathi vadi ki tana room, tana key, tana rules.”

---

### 👤 2️⃣ User Types

| User Type        | Description                              |
| ---------------- | ---------------------------------------- |
| **Root user**    | Superuser (Admin of system)              |
| **Normal user**  | Common user, limited access              |
| **Service user** | Created by services (like Apache, MySQL) |

🧩 Example:

* Root user → `/root` home directory
* Normal user → `/home/aravindh`
* Service user → `/var/lib/mysql`

Kadapa slang lo:

> “Root ante boss, normal users ante staff, service users ante background workers.”

---

### 🧩 3️⃣ User Information Files

| File           | Purpose               |
| -------------- | --------------------- |
| `/etc/passwd`  | User details          |
| `/etc/shadow`  | Passwords (encrypted) |
| `/etc/group`   | Group details         |
| `/etc/sudoers` | Sudo permissions      |

Kadapa slang lo:

> “System lo user data store ayye diaries `/etc` lo untayi mava. `/etc/passwd` ante attendance register la.”

---

### 👨‍💻 4️⃣ Create a User

👉 Command:

```bash
$ useradd raja
```

👉 Add password:

```bash
$ passwd raja
```

Kadapa slang lo:

> “`useradd` ante new student admission, `passwd` ante tana door key ivvadam.”

🧩 Example:

```
$ useradd prasad
$ passwd prasad
Changing password for user prasad:
New password: *****
```

---

### 🏠 5️⃣ Default user home directory

Every user ki `/home` lo tana folder untundi automatically.

```bash
$ ls /home
aravindh  prasad
```

Kadapa slang lo:

> “System tana kosam room ready chesthundi — `/home/prasad`.”

---

### 🧱 6️⃣ Delete a User

```bash
$ userdel raja
$ userdel -r raja   # home directory tho kalipi delete
```

Kadapa slang lo:

> “`userdel -r` ante hostel nunchi luggage tho kalipi bayata pettadam.”

---

### 👥 7️⃣ Group Management

👉 Groups use chestharu permissions easy ga assign cheyyadaniki.
Manam multiple users ni oka group lo petti **same access** ivvachu.

#### Commands:

```bash
$ groupadd devteam
$ usermod -aG devteam raja
$ groups raja
```

🧩 Example:

```
$ groups raja
raja : raja devteam
```

Kadapa slang lo:

> “Mava, office lo developers, testers, admins untaru kada. Alage Linux lo devteam, testteam ane groups create chestham.”

---

### 🔁 8️⃣ Modify Existing User

| Command                         | Use               |
| ------------------------------- | ----------------- |
| `usermod -L username`           | Lock user         |
| `usermod -U username`           | Unlock user       |
| `usermod -aG group user`        | Add user to group |
| `usermod -s /sbin/nologin user` | Block shell login |
| `usermod -d /custom/home user`  | Change home path  |

Kadapa slang lo:

> “`usermod` ante user profile lo changes cheyyadam ra — shell, group, home path anni marchachu.”

---

### 🔒 9️⃣ Switch Users

#### Command:

```bash
$ su - raja
```

(`su` = switch user)

Kadapa slang lo:

> “`su - raja` ante prasad nunchi raja ga login avvadam — system lo disguise laga.”

---

### 🧩 10️⃣ Sudo (Temporary Admin Access)

👉 **Normal user** ki admin rights kavali ante `sudo` use chesthamu.
`/etc/sudoers` file lo user add cheyyali.

#### Example:

```bash
$ visudo
raja  ALL=(ALL)  ALL
```

Ippudu raja command ivvagaladu:

```bash
$ sudo systemctl restart sshd
```

Kadapa slang lo:

> “`sudo` ante system ki cheppadam — ‘naa peru cheppina command ni admin laga run cheyyi’ ani.”

---

### 🧾 11️⃣ User Info Check

| Command       | Use                    |
| ------------- | ---------------------- |
| `id username` | User & group IDs       |
| `whoami`      | Current user           |
| `who`         | Logged-in users list   |
| `last`        | Previous login history |

Kadapa slang lo:

> “`id` ante aadhaar number la — prathi user ki separate ID. `whoami` ante ‘nuvvu evaru’ ani system ki cheppadam.”

---

### 🧹 12️⃣ Password Management

| Command                  | Description        |
| ------------------------ | ------------------ |
| `passwd username`        | Change password    |
| `passwd -l username`     | Lock user password |
| `passwd -u username`     | Unlock password    |
| `chage -l username`      | View expiry info   |
| `chage -E date username` | Set expiry         |

Kadapa slang lo:

> “Password expire avvakunda maintain cheyyali ante `chage` use chestham — like validity date set cheyyadam.”

---

### ⚡ Real-life Example

Suppose project lo 3 users unnaru:
`aravindh`, `raja`, `prasad`
and group `devteam`.

```bash
groupadd devteam
useradd -G devteam aravindh
useradd -G devteam raja
useradd -G devteam prasad
```

Ipudu devteam folder create chestham:

```bash
mkdir /devteam
chgrp devteam /devteam
chmod 770 /devteam
```

✅ Ippudu devteam lo unna vallake access untundi.

Kadapa slang lo:

> “Ippudu devteam group members matrame room open cheyyagalru, vere vallaki entry ledu.”

---

### 💬 Kadapa slang Summary:

> “Mava, Linux lo prathi user ki tana ID, tana password, tana folder untundi.
> Admin user root — adhi full rights tho untundi.
> Users create cheyyali ante `useradd`, password `passwd`, modify `usermod`.
> Groups create cheyyali ante `groupadd`, add cheyyali ante `usermod -aG`.
> Sudo rights ivvali ante `/etc/sudoers` edit cheyyali.
> Ivi gurthunte, users ni control cheyyadam butter laga untundi mava!”

---

✅ **SEGMENT 7 Completed!**
Next → **SEGMENT 8: File Permissions & Ownership (chmod, chown, umask, ACL, sticky bit)**

Mava cheppu — segment 8 start cheyyama?
**🔥 SEGMENT 8: File Permissions & Ownership — Kadapa slang lo full clarity & realtime examples**

---

### 🧠 1️⃣ Basic Idea

👉 Linux lo prathi file, folder ki **owner, group, and permissions** untayi.
Manam system ki cheppali — evaru read cheyyachu, evaru modify cheyyachu, evaru delete cheyyachu.

Kadapa slang lo:

> “Mava, manaki intlo room unte — neeke keys untayi, friends ki limited access untundi kada. Alage Linux lo kuda file ki owner, group, others permissions separate ga untayi.”

---

### 👥 2️⃣ Permission Types

| Symbol | Meaning | Action                          |
| ------ | ------- | ------------------------------- |
| **r**  | Read    | File ni chadavadam              |
| **w**  | Write   | File ni modify cheyyadam        |
| **x**  | Execute | Program or script run cheyyadam |

---

### 🧩 3️⃣ Users Classification

| Type           | Description        |
| -------------- | ------------------ |
| **u (user)**   | File owner         |
| **g (group)**  | File group members |
| **o (others)** | All other users    |

🧩 Example:
Suppose `aravindh` ane user file create chesadu —

* u = aravindh
* g = aravindh’s group
* o = system lo remaining users

---

### 📂 4️⃣ Permission Check

Command:

```bash
$ ls -l
```

Example Output:

```
-rwxr-xr--  1 aravindh devteam  5120 Oct 27  file1.sh
```

🧩 Break Down:

```
-   = file type
rwx = owner permissions
r-x = group permissions
r-- = others permissions
```

Kadapa slang lo:

> “`rwx` ante full control, `r-x` ante read + run, `r--` ante just chadavadam matrame.
> So, first three letters owner ki, next three group ki, last three others ki.”

---

### 🔢 5️⃣ Permission Numbers

Permissions ni **numeric** form lo kuda ivvachu.

| Permission        | Number |
| ----------------- | ------ |
| r (read)          | 4      |
| w (write)         | 2      |
| x (execute)       | 1      |
| - (no permission) | 0      |

👉 Add cheyyali:

* rwx = 7 (4+2+1)
* rw- = 6 (4+2)
* r-- = 4

🧩 Example:

```bash
chmod 755 file1.sh
```

Meaning:

* Owner → 7 (rwx)
* Group → 5 (r-x)
* Others → 5 (r-x)

Kadapa slang lo:

> “`chmod 755` ante neeku full rights, inka vallaki chadavadaniki mariyu run cheyyadaniki matrame permission.”

---

### ⚙️ 6️⃣ Change Permissions

| Command          | Use                                |
| ---------------- | ---------------------------------- |
| `chmod 777 file` | Everyone full rights               |
| `chmod 644 file` | Owner read-write, others read-only |
| `chmod u+x file` | Owner ki execute right add         |
| `chmod g-w file` | Group nunchi write right remove    |

🧩 Example:

```bash
chmod u+rwx,g+rx,o-r file1.sh
```

Kadapa slang lo:

> “`chmod` ante system ki cheppadam — ee file ni evaru touch cheyyachu, evaru cheyyaleru ani.”

---

### 👑 7️⃣ Ownership (Owner & Group change)

#### Command:

```bash
chown user:group filename
```

🧩 Example:

```bash
chown prasad:devteam file1.sh
```

Kadapa slang lo:

> “`chown` ante ownerni marchadam — like house peru marchadam registration lo.”

---

### 🧩 8️⃣ umask (Default Permission Template)

👉 New file create chesinappudu automatic ga permissions apply avuthayi.
Daanini control cheyyadaniki `umask` use chestham.

| File Type | Default Before umask | Common umask | Final Permission |
| --------- | -------------------- | ------------ | ---------------- |
| File      | 666                  | 022          | 644              |
| Directory | 777                  | 022          | 755              |

#### Command:

```bash
$ umask
0022
```

Kadapa slang lo:

> “`umask` ante default rules mava — new file create chesina ventane permissions decide chesthundi.”

---

### 🧩 9️⃣ Special Permissions

3 special bits untayi — sticky, SUID, SGID

#### 1️⃣ Sticky Bit (t)

👉 Folder lo only owner maathrame tana files delete cheyyagaladu.
Mostly `/tmp` folder lo untundi.

#### Command:

```bash
chmod +t /folder
```

Kadapa slang lo:

> “Sticky bit ante ‘nenu create chesina file nenu maathrame delete cheyyagalanu’ — vere vallaku no entry.”

---

#### 2️⃣ SUID (Set User ID)

👉 Command run avuthapudu **file owner permissions tho run avvali** ante SUID set chestham.
Example: `/usr/bin/passwd` lo SUID untundi.

#### Command:

```bash
chmod u+s filename
```

Kadapa slang lo:

> “`SUID` ante file run ayyaka admin laga nadustundi mava — like temporary boss permissions.”

---

#### 3️⃣ SGID (Set Group ID)

👉 File run avuthapudu **group permissions** inherit avuthayi.
Used mostly for **shared project folders**.

#### Command:

```bash
chmod g+s /project
```

Kadapa slang lo:

> “SGID ante project lo unna vallaki same access automatic ga vastundi.”

---

### 🧩 10️⃣ ACL (Access Control List)

👉 Normal `chmod` tho limited permissions matrame ivvagalamu.
ACL tho **extra users/groups** ki custom permissions ivvachu.

#### Command Example:

```bash
setfacl -m u:raja:rw file1.txt
getfacl file1.txt
```

Kadapa slang lo:

> “ACL ante advanced permissions ra mava — example, prasad file ni create chesina kuda, raja ki kuda chadavadam permission ivvachu.”

---

### 💬 Kadapa slang Summary:

> “Mava, Linux lo permissions 3 levels lo untayi – user, group, others.
> `r` read, `w` write, `x` execute.
> `chmod` tho permissions change chestham, `chown` tho owner marchadam, `umask` tho default rules set chestham.
> Special bits — Sticky bit, SUID, SGID.
> ACL ante custom permission boss-level feature.
> Ee concept strong ga thelusukunte security issues avoid cheyyachu.”

---

✅ **SEGMENT 8 Completed!**
Next → **SEGMENT 9: File Search Commands (find, locate, dd, size/date filters, etc.)**

Mava cheppu — segment 9 start cheyyama?

# Section 1 — Sanity Checks

> Platform: CyLab Security Academy (picoCTF)  
> Date: 2026-05-22  
> Difficulty: Easy  

---

## Obedient Cat

**Category:** General Skills  
**Description:** This file has a flag in plain sight.

### Solution

```bash
wget <file_url>
cat flag
```

**Flag:** `picoCTF{s4n1ty_ch3ck_28cc78c7}`

### Concepts Learned
- `cat` prints the contents of a file to the terminal
- Some challenges hide the flag in plain text files — no tricks needed

---

## Super SSH

**Category:** General Skills  
**Description:** Connect to a remote server using SSH.

### Solution

```bash
ssh -p <port> <user>@<host>
```

Enter the password when prompted. The flag is printed on login.

**Flag:** `picoCTF{s3cur3_c0nn3ct10n_<hash>}`

### Concepts Learned
- SSH (Secure Shell) is used to remotely connect to another machine
- `-p` specifies a non-default port
- SSH is a fundamental tool in pentesting for remote access

---

## what's a net cat?

**Category:** General Skills  
**Description:** Connect to a server using netcat to get the flag.

### Solution

```bash
nc <host> <port>
```

The flag is printed immediately on connection.

**Flag:** `picoCTF{nETcat_iS_a_tOol_<hash>}`

### Concepts Learned
- `nc` (netcat) is a networking utility for reading and writing data across network connections
- It's often called the "Swiss army knife" of networking
- In pentesting, netcat is used for port scanning, banner grabbing, reverse shells, and file transfers

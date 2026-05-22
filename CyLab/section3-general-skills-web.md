# Section 3 — General Skills & Web Exploitation

> Platform: CyLab Security Academy (picoCTF)  
> Date: 2026-05-22  
> Difficulty: Easy  

---

## Warmed Up

**Category:** General Skills  
**Description:** What is 0x3D (base 16) in decimal (base 10)?

### Solution

Convert hex to decimal manually:

```
0x3D = (3 × 16) + 13 = 48 + 13 = 61
```

**Flag:** `picoCTF{61}`

### Concept Learned
Hexadecimal (base 16) to decimal (base 10) conversion. Digits A–F represent 10–15.

---

## Wave a Flag

**Category:** General Skills  
**Description:** Invoke help flags for a binary to find the flag.

### Solution

```bash
wget <binary_url>
chmod +x warm
./warm -h
```

**Flag:** Found in help output of the binary.

### Concepts Learned
- Binaries are executed, not read — use `./filename` to run them
- `./` tells the shell to look in the current directory (not `$PATH`)
- `chmod +x` sets the execute permission before running
- `-h` and `--help` are standard flags for getting help output from programs

---

## Tab, Tab, Attack

**Category:** General Skills  
**Description:** Navigate a deeply nested directory structure using tab completion.

### Solution

```bash
wget <zip_url>
unzip Addadshashanammu.zip
cd Addadshashanammu
# Use tab completion to navigate each level
cd Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
./fang-of-haynekhtnamet
```

**Flag:** Found in the output of the binary at the bottom of the nested directory.

### Concepts Learned
- **Tab completion:** Type the first few characters of a filename and press Tab — the shell completes it automatically
- Deeply nested directories are navigated with `cd` one level at a time, or all at once using the full path
- `ls` reveals what's inside each directory

---

## strings it

**Category:** General Skills  
**Description:** Find the flag in a binary without running it.

### Solution

```bash
wget <binary_url>
strings <filename> | grep picoCTF
```

**Flag:** Found in the readable strings extracted from the binary.

### Concepts Learned
- `strings` extracts all human-readable text embedded in a binary file
- Piping (`|`) passes the output of one command into another
- `grep` filters output to only show lines matching a pattern
- Binaries often contain plaintext strings — a key technique in reverse engineering and CTFs

---

## First Grep

**Category:** General Skills  
**Description:** Find the flag hidden inside a large text file.

### Solution

```bash
wget <file_url>
grep picoCTF file
```

**Flag:** `picoCTF{grep_is_good_to_find_things_e3C4b360}`

### Concepts Learned
- `grep` searches through file contents for a matching pattern
- Unlike `strings | grep` (for binaries), plain text files can be grepped directly
- Quotes around the search term are optional when there are no spaces

---

## Where Are the Robots

**Category:** Web Exploitation  
**Description:** Find a hidden page that the website owner doesn't want crawled.

### Solution

Navigate to the `robots.txt` file:

```
http://<instance>/robots.txt
```

The file revealed a disallowed path:

```
User-agent: *
Disallow: /cc6b1.html
```

Visiting that path directly returned the flag.

```bash
# Alternative via terminal:
curl http://<instance>/robots.txt
curl http://<instance>/cc6b1.html
```

**Flag:** Found on the disallowed page.

### Concepts Learned
- `robots.txt` is a standard file at the root of any website that tells search engine crawlers which pages to avoid
- In pentesting, disallowed paths in `robots.txt` are prime targets — they often reveal sensitive or hidden content
- `curl` fetches a URL and prints its content directly in the terminal

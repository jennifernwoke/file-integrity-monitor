# File Integrity Monitor

## Project Overview

This is my second project that I've created to develop my Python programming and cybersecurity skills outside college.

The aim of this project was to create a simple File Integrity Monitor that can detect changes made to files by comparing their SHA-256 hashes against a previously created baseline.

The project creates a baseline of files that are considered trusted and then checks those files later to identify whether they have been modified, deleted, or whether new files have been added.

The project is currently in its first version, but I plan to come back and add more stuff.

---

## Features

The File Integrity Monitor includes:

* calculates SHA-256 hashes for files
* creates a baseline of trusted files
* stores file hashes in a JSON file
* compares current file hashes against the baseline
* detects modified files
* detects new files
* detects deleted files
* provides command-line options for creating a baseline and checking file integrity
* displays alerts when changes are detected
* displays a message when no changes are detected

---

## Requirements

My project required:

* Python 3
* Visual Studio Code (optional)
* macOS Terminal (optional)

The project uses Python's built-in modules.

---

## Running the Project

To run the File Integrity Monitor, open Terminal and navigate to the project directory.

```bash
cd file-integrity-monitor
```

### Creating a baseline

Before checking for changes, a baseline needs to be created.

Run:

```bash
python3 file_integrity_monitor.py baseline
```

The program will create a `baseline.json` file containing the SHA-256 hashes of the files inside the `test_files` directory.

The output should look like:

```text
Baseline created successfully.
```

### Checking file integrity

To compare the current files against the baseline, run:

```bash
python3 file_integrity_monitor.py check
```

If no files have changed, the program displays:

```text
No changes detected.
```

If a file has been modified, the program will display an alert such as:

```text
[!] File modified: test_files/document.txt
```

A new file will produce:

```text
[+] New file detected: test_files/newfile.txt
```

A deleted file will produce:

```text
[-] File deleted: test_files/newfile.txt
```

---

## How It Works

The File Integrity Monitor uses SHA-256 hashing to create a unique hash value for each file.

For example, the program uses Python's `hashlib` module:

```python
sha256 = hashlib.sha256()
```

The contents of each file are then read and used to generate a SHA-256 hash.

The resulting hash is stored in the baseline:

```text
test_files/document.txt → SHA-256 hash
```

When the integrity check is run, the program calculates the current hash of each file and compares it with the hash stored in the baseline.

If the hashes are different, the file has changed.

The program also compares the list of current files with the files stored in the baseline. This allows it to identify files that have been added or deleted.

The baseline is stored as a JSON file so that the information can be loaded when the program performs a future integrity check.

---

## Future Improvements

Though I'm still learning, there are several improvements I would like to add eventually.

* add timestamps to integrity alerts
* create a dedicated log file
* scan subdirectories automatically
* improve the command-line interface
* add more detailed reports
* add file permissions and metadata checks
* allow the user to select a directory to monitor
* improve error handling
* add automated monitoring rather than requiring a manual check
* research how professional File Integrity Monitoring tools work
* add unit tests
* improve the project documentation

I would also like to research how File Integrity Monitoring is used in real-world cybersecurity environments and digital forensics investigations.

---

## What I Learned

During the project I became more comfortable with:

* creating and running Python scripts
* using the macOS Terminal
* working with Python functions
* using conditional statements
* using `if`, `elif` and `else`
* working with dictionaries
* working with JSON files
* importing Python modules
* using `hashlib`
* using SHA-256 hashing
* working with file paths using `pathlib`
* using command-line arguments with `sys.argv`
* comparing file hashes
* testing a cybersecurity tool
* troubleshooting Python code
* understanding the basic concept of file integrity monitoring
* using GitHub to document and share a project

---


## Author

**Jennifer Nwoke**

Year 3 — Digital Forensics and Cyber Security

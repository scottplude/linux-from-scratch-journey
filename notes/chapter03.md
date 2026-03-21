# 🛠️ Linux From Scratch – Command Reference

This document explains the commands used during this stage of my Linux From Scratch journey in plain English. If you're following along and wondering “what does that actually do?”—this is for you.

Think of this as a cheat sheet for everything I typed, without the confusion.

---

## 📦 Disk & Partitioning

### `lsblk`
What it does:
Lists all storage devices (hard drives, partitions, USB drives) connected to the system.

Why I used it:
To confirm I was working on the correct disk before doing anything destructive.

Plain English version:
“Show me all the drives so I don’t accidentally destroy the wrong one.”

Important note:
Getting this wrong = very bad day.

sudo fdisk /dev/sdb
What it does:
A command-line tool used to create, delete, and modify disk partitions.

Why I used it:
To divide the empty drive into:

A small boot partition (~512MB)
A large root partition (everything else)

What sudo means:
sudo stands for “superuser do.” It temporarily gives you administrator (root) privileges so you can run commands that affect the system at a low level.

Plain English version:
“Hey system, let me act like the boss for a minute so I can safely mess with the disk.”
Common fdisk Commands
Key	Meaning
n	    Create a new partition
p	    Choose primary partition
w	    Write changes to disk (no going back!)
p	    Print the current partition table
Plain English version:
These are the single-letter commands I used inside fdisk to carve up the disk into usable sections.

💾 Filesystems
mkfs.ext2
sudo mkfs.ext2 /dev/sdb1
What it does:
Creates an ext2 filesystem on the specified partition.

Why I used it:
For the /boot partition—simple, lightweight, and perfect for holding boot files like the kernel and bootloader.

Plain English version:
“Turn this small section of the disk into a simple storage space the computer can use to start up.”

mkfs.ext4
sudo mkfs.ext4 /dev/sdb2
What it does:
Creates an ext4 filesystem on the specified partition.

Why I used it:
For the main system (root partition). It’s modern, reliable, and designed to handle everything else.

Plain English version:
“Set up the main storage area where the entire operating system will live.”

⚠️ General Warnings
Double-check device names (/dev/sdb, etc.)
These commands can permanently erase data
Always verify before pressing Enter on destructive commands

Plain English version:
Measure twice, type once.

🧠 Notes for Future Me
If something breaks later… it was probably here.

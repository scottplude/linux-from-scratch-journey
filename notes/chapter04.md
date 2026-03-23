# 🧱 Chapter 4: Setting Up the LFS Workspace

## 📌 Overview
In this chapter, we prepare the environment for building Linux From Scratch by creating the workspace, mounting storage, and setting permissions.

---

## 🧰 Commands Used


sudo mkdir -pv /mnt/lfs
export LFS=/mnt/lfs
umask 022

sudo mount -v -t ext4 /dev/sdb2 $LFS

sudo nano /etc/fstab
# Add:
# /dev/sdb2  /mnt/lfs  ext4  defaults  0  0

chown root:root $LFS
chmod 755 $LFS

mkdir -pv $LFS/{etc,var} $LFS/usr/{bin,lib,sbin}

for i in bin lib sbin; do
  ln -sv usr/$i $LFS/$i
done

case $(uname -m) in
  x86_64) mkdir -pv $LFS/lib64 ;;
esac

⚠️ Common Mistakes
Running commands with sudo without $LFS set
Forgetting to mount after reboot
Editing /etc/fstab incorrectly
Permission denied errors due to ownership

## 🔁 Persistent LFS Variable (Common Issue)

### ⚠️ Problem

After setting:
export LFS=/mnt/lfs
Everything works… until you close the terminal.

Open a new session and:
echo $LFS
returns nothing

🛠️ Fix (Make It Persistent)

Add the variable to your shell configuration file.

For a normal user:
nano ~/.bashrc
Add this line at the bottom:
export LFS=/mnt/lfs

For root:
nano /root/.bashrc
add the same line:
export LFS=/mnt/lfs

⚡ Apply Without Rebooting
source /.bashrc

or for root:
source /root/.bashrc



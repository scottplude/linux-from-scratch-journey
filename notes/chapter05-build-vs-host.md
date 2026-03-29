# 🏗️ LFS #5 - Build System vs Host System

These are my notes while learning Linux From Scratch (LFS).

This section explains the difference between:
- Build system
- Host system
- Target system

---

## 🧠 Simple Explanation

- **Build System** = the system doing the compiling  
- **Host System** = the system the compiled programs will run on  
- **Target System** = the system being created (LFS)

---

## 🖥️ My Setup

**Factory VM (Ubuntu):**
- Used to build everything

**LFS Disk:**
- Mounted at `/mnt/lfs`
- Will become the final system

---

## 🔄 Build Phases

### 1. Before Toolchain
- Build = Ubuntu  
- Host = Ubuntu  

### 2. Cross Compiling
- Build = Ubuntu  
- Host = LFS  

### 3. After chroot
- Build = LFS  
- Host = LFS  

---

## 🔧 Key Concepts

### Source Code
Human-readable instructions for programs.

### Compiler
Converts source code into machine code.

### Cross Compiling
Building software for a different system than the one you're currently using.

---

## 🧩 Why This Matters

This process prevents the new system from depending on the host (Ubuntu), ensuring a clean and independent build.

---

## 🔗 Full Blog Post

Read the full explanation here:  
👉 # 🏗️ LFS #5 - Build System vs Host System

These are my notes while learning Linux From Scratch (LFS).

This section explains the difference between:
- Build system
- Host system
- Target system

---

## 🧠 Simple Explanation

- **Build System** = the system doing the compiling  
- **Host System** = the system the compiled programs will run on  
- **Target System** = the system being created (LFS)

---

## 🖥️ My Setup

**Factory VM (Ubuntu):**
- Used to build everything

**LFS Disk:**
- Mounted at `/mnt/lfs`
- Will become the final system

---

## 🔄 Build Phases

### 1. Before Toolchain
- Build = Ubuntu  
- Host = Ubuntu  

### 2. Cross Compiling
- Build = Ubuntu  
- Host = LFS  

### 3. After chroot
- Build = LFS  
- Host = LFS  

---

## 🔧 Key Concepts

### Source Code
Human-readable instructions for programs.

### Compiler
Converts source code into machine code.

### Cross Compiling
Building software for a different system than the one you're currently using.

---

## 🧩 Why This Matters

This process prevents the new system from depending on the host (Ubuntu), ensuring a clean and independent build.

---

## 🔗 Full Blog Post

Read the full explanation here:  
👉 https://scottplude.com/5-linux-from-scratch-basics-build-vs-host/

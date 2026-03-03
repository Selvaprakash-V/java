# ☕ DAY 1 — Java Fundamentals

> _"Write Once, Run Anywhere"_ — Java's Core Philosophy

---

## 📌 Topics Covered

- [JVM — Java Virtual Machine](#1-jvm-java-virtual-machine)
- [JRE — Java Runtime Environment](#2-jre-java-runtime-environment)
- [Platform Independence](#3-is-java-platform-independent)
- [JIT — Just-In-Time Compiler](#4-jit-just-in-time-compiler)
- [JDK — Java Development Kit](#5-jdk-java-development-kit)
- [JVM vs JRE vs JDK — Comparison](#-difference-between-jvm-jre-and-jdk)

---

## 1. JVM — Java Virtual Machine

The **Java Virtual Machine (JVM)** is the engine that drives Java applications.

When a Java program is compiled, it generates **bytecode** (a `.class` file), which is a platform-independent intermediate code. The JVM converts this bytecode into **machine code** specific to the operating system and hardware.

> 💡 This enables Java's famous principle: **"Write Once, Run Anywhere (WORA)"**

---

### 🏗️ JVM Architecture Diagram

```
  JVM Language
     Class
       │
       ▼
 ┌─────────────────┐                    Memory Area
 │   Class Loader  │◄──────────────── Allocated by JVM
 └────────┬────────┘                          │
          │ ▲                                 │
          ▼ │                                 ▼
 ┌──────────────────────────────────────────────────────┐
 │                  Memory Area                         │
 │  ┌───────────┐ ┌──────┐ ┌───────┐ ┌────┐ ┌────────┐ │
 │  │  Class    │ │      │ │       │ │ PC │ │ Native │ │
 │  │ (Method)  │ │ Heap │ │ Stack │ │Reg.│ │ Method │ │
 │  │   Area    │ │      │ │       │ │    │ │ Stack  │ │
 │  └───────────┘ └──────┘ └───────┘ └────┘ └────────┘ │
 └──────────────────────┬───────────────────────────────┘
                        │ ▲
                        ▼ │
 ┌──────────────┐   ┌──────────────────┐   ┌─────────────────┐
 │  Execution   │◄─►│  Native Method   │◄─►│ Native Method   │
 │   Engine     │   │   Interface      │   │   Libraries     │
 └──────────────┘   └──────────────────┘   └─────────────────┘
```

---

### 🔹 Main Responsibilities of JVM

The JVM performs **three major tasks**:

| Step | Component | Description |
|------|-----------|-------------|
| 1️⃣ | **Loading** | The **Class Loader** loads the compiled bytecode into memory |
| 2️⃣ | **Verifying** | The **Bytecode Verifier** checks security, syntax rules & code integrity |
| 3️⃣ | **Executing** | The **Execution Engine** converts bytecode into machine instructions and runs the program |

---

### 🔹 Memory Management in JVM

The JVM also handles:

- 📦 Memory allocation for objects
- 🗑️ **Garbage Collection (GC)** to remove unused objects
- ⚡ Efficient memory utilization

---

## 2. JRE — Java Runtime Environment

The **Java Runtime Environment (JRE)** provides everything needed to **run** Java applications.

### 🔹 It Includes:

```
JRE
 ├── JVM (Java Virtual Machine)
 ├── Core Java Libraries
 └── Supporting Files & Resources
```

### 🔹 Important Points:

- ✅ Required for **end-users** who only *run* Java applications
- ❌ Does **NOT** include development tools like the compiler (`javac`)
- ❌ Cannot be used to **write or compile** Java programs

---

## 3. Is Java Platform Independent?

### ✅ Yes, Java is Platform Independent!

### 🔹 How?

```
Source Code (.java)
        ↓
   [javac compiler]
        ↓
  Bytecode (.class)   ← Platform Independent!
        ↓
  ┌─────┼─────┐
  ▼     ▼     ▼
 JVM   JVM   JVM
Windows Linux  Mac
```

> 📌 The **same `.class` file** runs on Windows, Linux, and Mac — as long as a JVM is installed!

---

## 4. JIT — Just-In-Time Compiler

The **JIT (Just-In-Time) Compiler** is a part of the **JRE**.

### 🔹 Purpose:

| Feature | Detail |
|---------|--------|
| ⚡ Performance | Improves performance of Java applications **during runtime** |
| 🔄 Conversion | Converts **frequently used bytecode** into native machine code |
| 🚀 Speed | Significantly **reduces execution time** |

---

## 5. JDK — Java Development Kit

The **Java Development Kit (JDK)** provides the complete environment to **develop and execute** Java programs.

### 🔹 JDK Includes:

```
JDK
 ├── Development Tools
 │    ├── javac  (compiler)
 │    ├── Debugger
 │    ├── Documentation tools
 │    └── Other utilities
 └── JRE
      ├── JVM
      └── Libraries
```

---

## 🔁 Difference Between JVM, JRE, and JDK

| Component | Purpose | Contains |
|-----------|---------|----------|
| **JVM** | Executes Java bytecode | Execution Engine + Memory Management |
| **JRE** | Runs Java applications | JVM + Libraries |
| **JDK** | Develops & Runs Java programs | JRE + Development Tools |

---

## 📌 Summary

| # | Key Takeaway |
|---|--------------|
| 1 | 🔧 **JVM** executes bytecode |
| 2 | 🏃 **JRE** provides the runtime environment |
| 3 | 🛠️ **JDK** is used for development |
| 4 | 🌍 Java is **platform independent** because of bytecode + JVM |
| 5 | ⚡ **JIT** improves runtime performance |

---

> _Made with ❤️ — Day 1 of Java Learning Journey_

---

# ☕ DAY 1 (Continued) — `main()` Method, String Pool & Packages

---

## 📌 Topics Covered

- [Components of `public static void main(String args[])`](#1-components-of-public-static-void-mainstring-args)
- [Java String Pool](#2-java-string-pool)
- [What Happens If main() Is Not Static?](#3-what-happens-if-main-is-not-static)
- [Packages in Java](#4-packages-in-java)

---

## 1. Components of `public static void main(String args[])`

The `main()` method is the **entry point** of a Java program.

### 🗂️ Anatomy Diagram

```
                  Keyword          Method name      Array of String type
                    │                  │                    │
                    ▼                  ▼                    ▼
         public  static  void       main        (String  args[])
            │                 │
            ▼                 ▼
     Access Specifier     Return type
```

---

### 1️⃣ `public`

| Property | Detail |
|----------|--------|
| Type | **Access Modifier** |
| Purpose | Specifies **who can access** the method |
| Why in main? | JVM needs to access it **from outside the class** |
| If removed? | ❌ JVM cannot invoke it — program won't run |

---

### 2️⃣ `static`

| Property | Detail |
|----------|--------|
| Type | **Keyword** |
| Purpose | Allows method to be called **without creating an object** |
| Why in main? | JVM calls `main()` **before any object is created** |
| Benefit | Avoids unnecessary memory allocation |

---

### 3️⃣ `void`

| Property | Detail |
|----------|--------|
| Type | **Return Type** |
| Purpose | Specifies that the method **does not return any value** |
| Why in main? | `main()` completes execution and returns nothing |

---

### 4️⃣ `main`

| Property | Detail |
|----------|--------|
| Type | **Method Name** |
| Purpose | Recognized by JVM as the **starting point of execution** |

---

### 5️⃣ `String args[]`

| Property | Detail |
|----------|--------|
| Type | **Array of String** |
| Purpose | Stores **command-line arguments** |
| Package | `String` belongs to `java.lang` |

**Example:**

```bash
java Program Hello
```

> 📌 `"Hello"` is stored in `args[0]`

---

## 2. Java String Pool

The **Java String Pool** is a special memory area inside the **Heap Memory**.

```
         Heap Memory
  ┌──────────────────────────┐
  │                          │
  │    ┌──────────────────┐  │
  │    │   String Pool    │  │
  │    │  ┌────────────┐  │  │
  │    │  │  "Java"    │  │  │
  │    │  └─────┬──────┘  │  │
  │    └─────── │─────────┘  │
  │             │            │
  └─────────────│────────────┘
          s1 ───┤
          s2 ───┘   (both point to same object!)
```

### 🔹 Key Points:

- 📦 Stores all **string literals**
- 🚫 Prevents creation of **duplicate string objects**
- 💾 Improves **memory efficiency**
- ♻️ If a string already exists in the pool, the **reference is reused**

**Example:**

```java
String s1 = "Java";
String s2 = "Java";
// s1 and s2 refer to the SAME object in the String Pool
```

---

## 3. What Happens If `main()` Is Not Static?

| Scenario | Result |
|----------|--------|
| Declare `main()` without `static` | ✅ Compiles successfully |
| Run the program | ❌ JVM won't treat it as the entry point |
| Execution | ❌ Program will not run properly |

> ⚠️ The JVM **cannot call a non-static method** without creating an object — and no object exists at startup!

---

## 4. Packages in Java

A **package** is a group of related **classes**, **interfaces**, and **sub-packages**.

```
 mypackage/
  ├── MyClass.java
  ├── AnotherClass.java
  └── utils/
       └── Helper.java
```

### 🔹 Purpose of Packages:

| Benefit | Description |
|---------|-------------|
| 🏷️ Namespace Management | Avoids **name conflicts** between classes |
| 🔒 Access Protection | Controls **visibility** of classes and members |
| 📂 Code Organization | Groups **related classes** together |
| 🔧 Maintainability | Makes large codebases easier to **manage** |

**Example:**

```java
package mypackage;

public class MyClass {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```

---

## 📌 Summary

| # | Key Takeaway |
|---|--------------|
| 1 | 🚀 `public static void main(String args[])` is the **entry point** of Java programs |
| 2 | 💾 **String Pool** stores string literals in heap memory to avoid duplicates |
| 3 | ⚙️ `main()` must be **static** for JVM to execute it without an object |
| 4 | 📦 **Packages** help organize, protect, and manage Java code |

---

> _Made with ❤️ — Day 1 of Java Learning Journey (Continued)_

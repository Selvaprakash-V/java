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

---

# ☕ DAY 1 (Part 3) — Data Types, Pointers & Wrapper Classes

---

## 📌 Topics Covered

- [Data Types in Java](#1-data-types-in-java)
- [Primitive Data Types](#2-primitive-data-types)
- [Non-Primitive Data Types](#3-non-primitive-reference-data-types)
- [Pointers in Java](#4-can-we-declare-pointer-in-java)
- [Wrapper Classes](#5-wrapper-classes-in-java)
- [Why Wrapper Classes?](#6-why-do-we-need-wrapper-classes)

---

## 1. Data Types in Java

Data types specify the **type of data a variable can store**.

There are **two types** of data types in Java:

```
Data Types in Java
 ├── Primitive Data Types       (8 types)
 └── Non-Primitive Data Types   (Reference Types)
```

---

## 2. Primitive Data Types

Primitive data types are **basic data types** that store **single values** and are **not objects**.

### 🔹 Java's 8 Primitive Data Types

| Data Type | Size | Description |
|-----------|------|-------------|
| `boolean` | 1 bit | Stores `true` or `false` |
| `byte` | 8-bit | Signed two's complement integer |
| `short` | 16-bit | Signed two's complement integer |
| `int` | 32-bit | Signed two's complement integer |
| `long` | 64-bit | Signed two's complement integer |
| `float` | 32-bit | Single-precision IEEE 754 floating-point |
| `double` | 64-bit | Double-precision IEEE 754 floating-point |
| `char` | 16-bit | Stores a single Unicode character |

### 🔹 Example

```java
int number    = 10;
double price  = 99.99;
char grade    = 'A';
boolean status = true;
```

### 🔹 Key Features of Primitive Types

| Feature | Detail |
|---------|--------|
| 📍 Storage | Stored **directly in memory** (stack) |
| ⚡ Speed | **Faster** access |
| 💾 Memory | **Lower** memory usage |
| 🚫 Objects | **Not** objects — no methods |

---

## 3. Non-Primitive (Reference) Data Types

Non-Primitive types are also called **Reference Data Types**.

```
 Variable                Heap Memory
 ┌──────┐               ┌────────────────┐
 │ ref  │──────────────►│  Actual Object │
 └──────┘               └────────────────┘
```

They:
- Store the **memory address** of the value
- Are created using **classes**
- Can have **methods and properties**

### 🔹 Types of Non-Primitive Data Types

| Type | Example |
|------|---------|
| `String` | `"Java"` |
| `Array` | `int[] nums = {1, 2, 3}` |
| `Class` | User-defined classes |
| `Object` | `Object obj = new Object()` |
| `Interface` | `List`, `Map`, etc. |

### 🔹 Example

```java
String name    = "Java";       // name stores reference of String object
int[] numbers  = {1, 2, 3};   // numbers stores reference of array object
```

---

## 4. Can We Declare Pointer in Java?

### ❌ No, Java does NOT support pointers.

### 🔹 Why?

| Reason | Explanation |
|--------|-------------|
| 🔒 Security | Pointers can access **direct memory locations** causing security risks |
| 💥 Stability | Pointers can cause **memory corruption** |
| 🧹 Simplicity | Java was designed to be **simpler and less error-prone** |

> 💡 Java uses **references** instead of pointers — safer and managed by the JVM's Garbage Collector.

---

## 5. Wrapper Classes in Java

A **Wrapper Class** converts a **primitive data type into an object** — it "wraps" a primitive inside an object.

### 🔹 Primitive → Wrapper Mapping

| Primitive | Wrapper Class |
|-----------|---------------|
| `int` | `Integer` |
| `byte` | `Byte` |
| `short` | `Short` |
| `long` | `Long` |
| `float` | `Float` |
| `double` | `Double` |
| `char` | `Character` |
| `boolean` | `Boolean` |

### 🔹 Example

```java
int num         = 10;
Integer obj     = Integer.valueOf(num);  // Boxing
int value       = obj.intValue();        // Unboxing
```

---

## 6. Why Do We Need Wrapper Classes?

| Reason | Detail |
|--------|--------|
| 🔒 Immutable | Wrapper classes are **final and immutable** |
| 🛠️ Utility Methods | Provide methods like `valueOf()`, `parseInt()`, `compareTo()` |
| 🔄 Autoboxing | Support **automatic** primitive ↔ object conversion |
| 📦 Collections | Required to store primitives in **Collections** (e.g., `ArrayList<Integer>`) |

### 🔹 Autoboxing & Unboxing

```
Autoboxing:   primitive  ──────────►  Object
                int 100  ──────────►  Integer(100)

Unboxing:     Object     ──────────►  primitive
           Integer(100)  ──────────►  int 100
```

```java
Integer num = 100;   // Autoboxing  — int → Integer (automatic)
int value   = num;   // Unboxing    — Integer → int (automatic)
```

---

## 📌 Summary

| # | Key Takeaway |
|---|--------------|
| 1 | 📊 Java has **2 types** of data types: Primitive and Non-Primitive |
| 2 | 🔢 There are **8 primitive** data types |
| 3 | 🔗 Non-primitive types store **references** (memory addresses) |
| 4 | 🚫 Java does **not support pointers** for security & simplicity |
| 5 | 📦 **Wrapper classes** convert primitives into objects |
| 6 | ⚡ **Autoboxing & Unboxing** simplify primitive ↔ object conversions |

---

> _Made with ❤️ — Day 1 of Java Learning Journey (Complete)_

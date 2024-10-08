# Java Installation Guide

This guide walks you through installing Java on your local computer, setting up the environment, and configuring Visual Studio Code (VS Code) for Java development. We’ll also cover common issues and solutions.

## Table of Contents
- [Java Installation Guide](#java-installation-guide)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
  - [Step 1: Install Java Development Kit (JDK)](#step-1-install-java-development-kit-jdk)
  - [Step 2: Set Up Environment Variables](#step-2-set-up-environment-variables)
    - [Windows](#windows)
    - [macOS/Linux](#macoslinux)
  - [Step 4: Install Visual Studio Code](#step-4-install-visual-studio-code)
  - [Step 5: Install Java Extensions for VS Code](#step-5-install-java-extensions-for-vs-code)
    - [Optional Extensions](#optional-extensions)
  - [Common Issues \& Solutions](#common-issues--solutions)
    - [1. `java` is not recognized as an internal or external command](#1-java-is-not-recognized-as-an-internal-or-external-command)
    - [2. `javac` command is not found](#2-javac-command-is-not-found)
    - [3. VS Code doesn't recognize Java files](#3-vs-code-doesnt-recognize-java-files)
    - [4. Classpath issues when running Java projects](#4-classpath-issues-when-running-java-projects)

## Prerequisites
- **Operating System:** Windows, macOS, or Linux
- **VS Code:** Installed on your system. If not installed, follow [this link](https://code.visualstudio.com/Download) to download and install it.

## Step 1: Install Java Development Kit (JDK)

Java applications require a Java Development Kit (JDK). Follow these steps to install it:

1. **Download JDK:**
   - Visit the official Oracle JDK website: [Oracle JDK Downloads](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
   - Download the version appropriate for your OS (Windows, macOS, or Linux).

2. **Install the JDK:**
   - Follow the instructions to install the JDK for your platform:
     - **Windows:** Run the `.exe` installer and follow the prompts.
     - **macOS:** Run the `.dmg` installer and drag the JDK into the `/Library/Java/JavaVirtualMachines` directory.
     - **Linux:** Use the terminal and install via package manager (e.g., `sudo apt install openjdk-11-jdk` for Ubuntu).

## Step 2: Set Up Environment Variables

After installing the JDK, you need to set up the `JAVA_HOME` environment variable:

### Windows
1. Open **Control Panel** → **System and Security** → **System**.
2. Click **Advanced system settings**.
3. In the **System Properties** window, click **Environment Variables**.
4. Under **System variables**, click **New**, and set:
   - **Variable name:** `JAVA_HOME`
   - **Variable value:** Path to the JDK installation (e.g., `C:\Program Files\Java\jdk-11.0.10`).
5. Add the `bin` folder of the JDK to the `Path` variable:
   - Under **System Variables**, find and edit the `Path` variable.
   - Add a new entry: `C:\Program Files\Java\jdk-11.0.10\bin`.

### macOS/Linux
1. Open a terminal and edit your shell profile:
   - **bash:** `nano ~/.bash_profile`
   - **zsh:** `nano ~/.zshrc`
   - **Linux:** `nano ~/.bashrc` or `~/.profile`
2. Add the following lines:
   ```bash
   export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.jdk/Contents/Home
   export PATH=$JAVA_HOME/bin:$PATH
3. Save and close the file, then run `source ~/.bash_profile` (or `~/.zshrc`, etc.) to apply the changes.

## Step 3: Verify Installation

To verify that Java is installed correctly:

1. Open a terminal/command prompt.
2. Run the following command:
   ```bash
   java -version
   ```
    You should see output showing the installed version of Java, such as java version "11.0.10".
3. Also, check the javac (Java Compiler) installation:
    ```bash
    javac -version
    ```
    You should see output showing the installed version of Java compiler, such as javac 11.0.10.

## Step 4: Install Visual Studio Code

1. If you don't have VS Code, download it from the [official website](https://code.visualstudio.com/Download) and install it.
2. Launch VS Code after installation.

## Step 5: Install Java Extensions for VS Code

VS Code does not natively support Java, so you'll need to install extensions to enable Java development.

1. Open VS Code.
2. Go to the **Extensions** view by clicking on the Extensions icon in the Activity Bar on the side of the window or pressing `Ctrl+Shift+X`.
3. Search for and install the following extensions:
   - **Java Extension Pack** by Microsoft. This includes:
     - Language Support for Java™ by Red Hat
     - Debugger for Java
     - Java Test Runner
     - Maven for Java
     - Java Dependency Viewer

4. After installing, reload VS Code to activate the extensions.

### Optional Extensions
- **Spring Boot Extension Pack** (for Spring Boot development)
- **Lombok Extension** (if using Lombok in Java projects)

## Common Issues & Solutions

### 1. `java` is not recognized as an internal or external command
- **Cause:** This error typically occurs when Java is not added to your system’s `PATH`.
- **Solution:** Ensure that the `JAVA_HOME` and the `bin` directory of the JDK are properly added to your system's `PATH`.

### 2. `javac` command is not found
- **Cause:** This occurs if the Java compiler (`javac`) is not installed or not set up properly.
- **Solution:** Verify the installation of the JDK and ensure that the `bin` directory is correctly added to your `PATH`.

### 3. VS Code doesn't recognize Java files
- **Cause:** The necessary Java extensions may not be installed or activated.
- **Solution:** Ensure that the **Java Extension Pack** is installed and enabled in VS Code. You can also try reloading VS Code or reinstalling the extension.

### 4. Classpath issues when running Java projects
- **Cause:** The `CLASSPATH` variable might not be correctly set for your project.
- **Solution:** Ensure that the `CLASSPATH` is properly defined for your project or use VS Code's configuration options to set classpath settings via `launch.json` or `tasks.json`.

---

Now you're ready to start building Java applications in your local environment and Visual Studio Code!



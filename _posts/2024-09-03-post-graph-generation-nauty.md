---
title: "Graph Generation with Nauty"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Graph Theory
  - Tool
  - english
---

In this short article I want to write down the needed steps in order to generate a list of all graphs (no automorphisms!) with nauty.
<!--more-->

# What is it?

A more detailed explanation with additional information can be found [here](https://pallini.di.uniroma1.it/). Also, the documentation can be found [here](https://pallini.di.uniroma1.it/Guide.html)

# How to get it?
You can find it [here](https://pallini.di.uniroma1.it/nauty2_8_9.tar.gz) Download the gzipped tar file from there.

# How to install it?
In order to install it on a max, follow these simple steps:

- **Navigate to the directory containing the tar.gz file**
   - Use the `cd` command to change to the directory where your `nauty2_8_9.tar.gz` file is located. For example:
     ```
     cd ~/Downloads
     ```
   - Replace `~/Downloads` with the actual path if it's located elsewhere.

- **Extract the tar.gz file**
   - Run the following command to extract the contents of the tarball:
     ```
     tar xvzf nauty2_8_9.tar.gz
     ```
   - This command will unpack the contents into a directory named `nauty2_8_9`.

- **Navigate into the extracted directory**
   - Change to the newly created directory:
     ```
     cd nauty2_8_9
     ```

- **Run the configure script**
   - Run the `configure` script to prepare the build environment:
     ```
     ./configure
     ```
   - This script checks your system for the necessary tools and libraries and sets up the Makefile accordingly.

- **Compile the package**
   - Compile the source code by running:
     ```
     make
     ```
   - The `make` command compiles the program and builds the executables.

- **Install (Optional)**
   - If you want to install the binaries system-wide (usually under `/usr/local/bin`), you can run:
     ```
     sudo make install
     ```
   - You'll be prompted to enter your password because this command requires administrative privileges.

- **Verify the installation**
   - To verify that the installation was successful, you can try running one of the `nauty` commands. For example:
     ```
     ./dreadnaut
     ```
   - If the command runs without errors, the installation was successful.

# Examples

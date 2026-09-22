<img src="logo/bustub.svg" alt="BusTub Logo" height="200">

-----------------

# BusTub for CSCI 5817 Database Systems

BusTub is an educational relational database management system originally
developed at Carnegie Mellon University.

This repository is the version used for CSCI 5817: Database Systems at the
University of Colorado Boulder.

## Important Course Repository Rules

Students in CSCI 5817 must use this repository as the source repository for
course projects:

https://github.com/asaashraf/bustub

Do NOT use the current Carnegie Mellon BusTub repository for your course work.

Do NOT:

- fork this public repository directly for your project work
- create a public repository containing your project solutions
- push your work to this public repository
- push your work to the Carnegie Mellon BusTub repository
- open pull requests or issues against the Carnegie Mellon BusTub repository
  related to this course
- share your project code with other students

Your project repository must remain **PRIVATE**.

Do not remove the LICENSE file or existing attribution from the repository.

---

# Creating Your Private Repository

You will create a private copy of the CSCI 5817 BusTub repository under your
own GitHub account.

Before continuing, make sure GitHub SSH access is configured on your computer.
If it is not, complete the **GitHub SSH Setup** section below first.

## 1. Create an Empty Private GitHub Repository

Create a new repository under your GitHub account.

For example:

    private-bustub

Make sure the repository is set to **Private**.

You are not allowed to make this repository public at any time during or after
this course.

Do not initialize the repository with a README, `.gitignore`, or license.

## 2. Create a Temporary Bare Copy of the Course Repository

From a terminal:

    git clone --bare https://github.com/asaashraf/bustub.git

This creates a temporary directory named:

    bustub.git

## 3. Copy It Into Your Private Repository

Replace `YOUR_GITHUB_USERNAME` and `private-bustub` with your information:

    cd bustub.git
    git push --mirror git@github.com:YOUR_GITHUB_USERNAME/private-bustub.git

After the push completes, return to the parent directory and remove the
temporary copy:

    cd ..
    rm -rf bustub.git

## 4. Clone Your Private Repository

Now clone the private repository that you just created:

    git clone git@github.com:YOUR_GITHUB_USERNAME/private-bustub.git
    cd private-bustub

All of your project work should be completed in this private repository.

---

# GitHub SSH Setup

If GitHub SSH access is already working on your computer, you can skip this
section.

GitHub's recommended SSH key type is Ed25519:

    ssh-keygen -t ed25519 -C "your_email@example.com"

Follow GitHub's official SSH setup instructions if needed:

https://docs.github.com/en/authentication/connecting-to-github-with-ssh

After configuring SSH, verify your connection with:

    ssh -T git@github.com

---

# Course Repository Remote

After cloning your private repository, add the CSCI 5817 public repository as
a remote named `course`:

    git remote add course https://github.com/asaashraf/bustub.git

Verify your remotes with:

    git remote -v

You should see your private GitHub repository as `origin` and the CSCI 5817
repository as `course`.

If the instructor announces an update to the course repository, retrieve the
latest course changes with:

    git fetch course

Follow the instructor's directions for merging any course updates into your
work.

Do not add the Carnegie Mellon BusTub repository as a remote.

---

# Development Environment

Use the development environment specified in the CSCI 5817 course setup
instructions.

The course setup guide is the authoritative source for supported operating
systems, compilers, CMake, Visual Studio Code, and other development tools.

Do not assume that setup instructions from newer versions of BusTub found
online apply to this course repository.

---

# Building BusTub

All commands in this section should be run from the root of your private
BusTub repository.

Configure the project in Debug mode:

    cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug

Compile the project:

    cmake --build build

The `build` directory will be created automatically if it does not already
exist.

If you later change CMake configuration files or need to reconfigure the
project, you can run the configuration command again:

    cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug

---

# Running Tests

All commands in this section should be run from the root of your private
BusTub repository.

To compile and run all enabled tests:

    cmake --build build --target check-tests

Individual project tests can also be compiled and executed separately.

## LRU Replacer Test

Compile the test:

    cmake --build build --target lru_replacer_test

Run the test:

    ./build/test/lru_replacer_test

## Buffer Pool Manager Test

Compile the test:

    cmake --build build --target buffer_pool_manager_test

Run the test:

    ./build/test/buffer_pool_manager_test

The provided tests are only a subset of the tests that may be used for
grading. You should write and run additional tests to verify the complete
functionality of your implementation.

---

# Code Formatting and Static Analysis

Before submitting your project, run the formatting and code-quality checks
specified in the project instructions.

All commands should be run from the root of your private BusTub repository.

Format your code:

    cmake --build build --target format

Run the lint checks:

    cmake --build build --target check-lint

Run clang-tidy:

    cmake --build build --target check-clang-tidy

Your code must compile and conform to the course formatting and style
requirements.

---

# Project Work

Do not change public method signatures unless the project instructions
explicitly tell you to do so.

Do not remove required class members or replace provided course
infrastructure.

You may add helper methods or additional private data members when permitted
by the individual project specification.

Always follow the requirements in the project document provided through the
course shell.

The version of BusTub used in this course is intentionally based on an older
course codebase. Do not attempt to update it to match newer versions of BusTub
found online.

---

# Academic Integrity

All programming projects must be completed individually unless the instructor
explicitly states otherwise.

Do not share project code with other students.

Do not publish completed project code in a public GitHub repository or any
other publicly accessible location.

Your private repository must remain private during and after the course.

See the CSCI 5817 syllabus for the complete collaboration and academic
integrity policies.

---

# Attribution

BusTub was originally developed at Carnegie Mellon University for educational
use.

This repository contains the course version used for CSCI 5817 at the
University of Colorado Boulder.

See the LICENSE file included with this repository for applicable licensing
information.

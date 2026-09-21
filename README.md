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

Your project repository must remain PRIVATE.

Do not remove the LICENSE file or existing attribution from the repository.

---

# Creating Your Private Repository

You will create a private copy of the CSCI 5817 BusTub repository under your
own GitHub account.

## 1. Create an empty private GitHub repository

Create a new repository under your GitHub account.

For example:

    private-bustub

Make sure the repository is set to **Private**. Remember, you are not allowed to make this repo public at any time during or after this course.

Do not initialize the repository with a README, .gitignore, or license.

## 2. Create a temporary bare copy of the course repository

From a terminal:

    git clone --bare https://github.com/asaashraf/bustub.git

This creates a temporary directory named:

    bustub.git

## 3. Copy it into your private repository

Replace `YOUR_GITHUB_USERNAME` and `private-bustub` with your information:

    cd bustub.git
    git push --mirror git@github.com:YOUR_GITHUB_USERNAME/private-bustub.git

After the push completes, remove the temporary copy:

    cd ..
    rm -rf bustub.git

## 4. Clone your private repository

Now clone the private repository that you just created:

    git clone git@github.com:YOUR_GITHUB_USERNAME/private-bustub.git
    cd private-bustub

All of your project work should be completed in this private repository.

---

# GitHub SSH Setup

If GitHub SSH access is already working on your computer, you can skip this
section.

GitHub's current recommended SSH key type is Ed25519:

    ssh-keygen -t ed25519 -C "your_email@example.com"

Follow GitHub's official SSH setup instructions if needed:

https://docs.github.com/en/authentication/connecting-to-github-with-ssh

After configuring SSH, you can verify your connection with:

    ssh -T git@github.com

---

# Course Repository Remote

After cloning your private repository, add the CSCI 5817 public repository as
a remote named `course`:

    git remote add course https://github.com/asaashraf/bustub.git

You can verify your remotes with:

    git remote -v

You should see your private GitHub repository as `origin` and the CSCI 5817
repository as `course`.

If the instructor announces an update to the course repository, retrieve it
with:

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

From the repository root:

    mkdir build
    cd build
    cmake ..
    make

To create a Debug build:

    mkdir build
    cd build
    cmake -DCMAKE_BUILD_TYPE=Debug ..
    make

If the `build` directory already exists, you do not need to create it again.

---

# Running Tests

From inside the `build` directory, all enabled tests can be run with:

    make check-tests

Individual project tests can also be compiled and executed separately.

For example:

    make lru_replacer_test
    ./test/lru_replacer_test

and:

    make buffer_pool_manager_test
    ./test/buffer_pool_manager_test

The provided tests are not necessarily all of the tests that will be used for
grading. You should test your own implementation thoroughly.

---

# Code Formatting and Static Analysis

Before submitting your project, run the formatting and code-quality checks
specified in the project instructions.

From the `build` directory:

    make format
    make check-lint
    make check-clang-tidy

Your code must compile and conform to the course formatting and style
requirements.

---

# Project Work

Do not change public method signatures unless the project instructions
explicitly tell you to do so.

Do not remove required class members or replace provided course infrastructure.

You may add helper methods or additional private data members when permitted
by the individual project specification.

Always follow the requirements in the project document provided through the
course shell.

---

# Academic Integrity

All programming projects must be completed individually unless the instructor
explicitly states otherwise.

Do not share project code with other students.

Do not publish completed project code in a public GitHub repository or any
other publicly accessible location.

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

# AWS IAM Security Project

## 📌 Overview

This project demonstrates how to secure AWS resources using **IAM (Identity and Access Management)** policies and user groups. The primary goal was to apply the **principle of least privilege** by ensuring that developers can manage only development resources but are restricted from modifying or stopping production resources.

## 🛠️ Tools & Services Used

* **AWS EC2**
* **AWS IAM**
* **JSON Policies**


## 🚀 What I Did

* Created **EC2 instances** with tags:

  * `Env=production`
  * `Env=development`
* Set up an **AWS account alias** for a more user-friendly login URL.
* Created an **IAM group** and **IAM user** to manage access.
* Designed **IAM policies** that:

  * Allow full management of EC2 instances tagged as `development`
  * Allow viewing of all EC2 instances
  * Prevent modifying or stopping instances tagged as `production`


## Concepts Learned

* **IAM Policies**: Control access using *Effect*, *Action*, and *Resource* fields.
* **IAM Groups & Users**: Simplify access control by grouping users and attaching policies.
* **Tags**: Used for resource identification and applying policy conditions.
* **Least Privilege Principle**: Restricting access to only what’s necessary.


## 🧪 Testing the Policy

* ✅ Attempted to stop a **development instance** → Successfully stopped.
* ❌ Attempted to stop a **production instance** → Access denied (as expected).


## 📚 Reflection

This project took around **2 hours** to complete. It was rewarding to move from theoretical understanding of IAM and policies to practical implementation in AWS.





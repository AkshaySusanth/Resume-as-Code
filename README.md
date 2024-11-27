# Resume-as-Code 

![Workflow Status](https://github.com/AkshaySusanth/Resume-as-Code/actions/workflows/resume-as-code.yml/badge.svg)

**Resume-as-Code** is a GitHub repository that transforms resume management into an automated, code-driven process. This project leverages GitHub Actions to ensure that the resume is always up-to-date and available in the repository.

The repository contains a `resume-as-code.tex` file, which serves as the source for the resume. Every commit to this file triggers a GitHub Actions workflow that automatically generates a PDF version, ensuring the resume remains up-to-date with every change.

## ✨ Features

- **Automated Compilation**: Automatically compiles `.tex` files into a PDF whenever changes are pushed to the repository.
- **Artifact Storage**: Stores the compiled PDF as an artifact for download.
- **Version Control**: Commits and pushes the compiled PDF back to the repository for seamless version tracking.

---

## 🚀 Workflow Overview

### **Trigger Events**
1. **Push to Repository**:
   - Triggers when `.tex` files or workflow configurations are updated.
2. **Manual Dispatch**:
   - Allows you to run the workflow manually via GitHub's UI.

### **Jobs**

#### **1. Compile**
- **Runs on**: `ubuntu-latest`
- **Tasks**:
  - Install LaTeX dependencies.
  - Compile the `.tex` file into a PDF.
  - Rename the output PDF to `resume.pdf`.
  - Upload the PDF as a GitHub Actions artifact.

#### **2. Publish**
- **Runs on**: `ubuntu-latest`
- **Dependency**: Runs only after the `Compile` job succeeds.
- **Tasks**:
  - Download the compiled PDF artifact.
  - Commit and push the PDF back to the repository.

## 🏆 Benefits

- Ensures **consistent formatting** and output for resumes.
- Maintains a **history of updates** for easy versioning.
- Reduces **manual effort** with end-to-end automation.

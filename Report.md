# 📄 Claude Max Usage Report

## 1️⃣ Project Context

* **Project Name:** Microplan Ingestion
* **Service Name:** `excel-ingestion`
* **Purpose:** Automate Excel ingestion and validation for the microplan facility sheet, with schema-driven configuration, cascading dropdowns, and rich formatting.

---

## 2️⃣ Overview

* Generates Excel templates **directly from MDMS JSON schema**.
* Supports:

  * Localized headers
  * Color coding
  * Dropdowns (simple + cascading)
  * Multi-select values
* Uses **hidden sheets** for mapping parent–child relationships and localization.

---

## 3️⃣ Key Features

### **1. Schema-Driven Columns**

* Reads `stringProperties`, `numberProperties`, `enumProperties` from MDMS.
* Applies **color**, **order**, **required flags**, **hide/freeze settings**.

### **2. Header Structure**

* **Row 1 (hidden):** Technical column names.
* **Row 2 (visible):** Localized names with color formatting.

### **3. Dropdowns**

* **Enum Dropdown:** Static list of values.
* **Cascading Dropdown:** Dependent on the previous column’s selection.
* **Multi-Select:** Multiple visible columns + hidden concatenated column for backend.

### **4. Hidden Mapping Sheets**

* Store **parent → child** boundaries.
* Store **level → boundary lists**.
* Maintain **localization mappings**.

### **5. Cell Locking & Freezing**

* Cells are **unlocked by default**.
* Freeze columns when `freezeColumnIfFilled = true`.

### **6. Sheet Protection**

* Password-protected after setup.
* Only unlocked cells are editable.

---

## 4️⃣ Workflow

1. **Read** schema from MDMS.
2. **Generate** columns & headers.
3. **Add** dropdowns (enum/cascading).
4. **Expand** multi-select columns.
5. **Lock/Freeze** cells as per rules.
6. **Protect** and deliver sheet to user.

---

## 5️⃣ Usage Cautions

⚠ **Best Practices When Using Claude Max for Refactoring**

* **Review all suggestions** carefully — some changes may be inaccurate.
* **Test all working cases** before committing.
* **Commit small, functional changes** instead of large refactors.
* After each refactor, **validate all use cases** again.

---

## 6️⃣ Recommended Practice for Ongoing Improvements

It’s better to maintain a **dedicated `.md` file** to log changes and decisions, and update it periodically.
This way, Claude Max (and future developers) will have a **clear, evolving view of the project context** and can provide more accurate, relevant refactoring suggestions.

---

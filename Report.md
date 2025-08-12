# 📄 Claude Max – Microplan Ingestion

## Overview
- Builds Excel templates **from MDMS JSON schema**.
- Supports **localized headers**, **color coding**, **dropdowns** (normal + cascading), and **multi-select**.
- Uses hidden sheets for **parent-child** and **localization** mappings.

---

## Key Features
1. **Schema-Based Columns**
   - Reads `stringProperties`, `numberProperties`, `enumProperties` from MDMS.
   - Applies color, order, required flags, and hide/freeze settings.

2. **Headers**
   - **Row 1 (hidden):** Technical names.
   - **Row 2 (visible):** Localized names with color.

3. **Dropdowns**
   - **Enum:** Simple value lists.
   - **Cascading:** Next column’s values depend on previous column’s selection.
   - **Multi-Select:** Multiple visible selection columns + one hidden concatenated column.

4. **Hidden Mapping Sheets**
   - Store **parent → child** boundaries.
   - Store **level → boundaries**.
   - Store localization mappings.

5. **Cell Locking**
   - All cells unlocked by default.
   - Freeze columns once filled if `freezeColumnIfFilled=true`.

6. **Sheet Protection**
   - Password-protected after setup.
   - Allows editing only unlocked cells.

---

## Workflow
1. Read schema from MDMS.
2. Generate columns & headers.
3. Add dropdowns (enum/cascading).
4. Expand multi-select columns.
5. Lock/freeze cells as per rules.
6. Protect sheet and deliver to user.

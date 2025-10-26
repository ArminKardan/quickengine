
# QE Databases

In the QE system, when a new project is created by cloning an **Explore**, a **MongoDB database** is automatically initialized. This database is shared across all blocks within the project, allowing them to store and even share data with each other.

## 🗃️ Universal Database (`udb`)

- **Name**: `udb`
- **Owner**: `topuser`
- **Scope**: Global (shared across all blocks)
- **Access**:
  - **Back-end**: Direct access
  - **Front-end**: Access only via **GAPIs**
- **Purpose**: 
  - Used to store global project data
  - Enables data sharing between blocks
- **Example Use Cases**:
  - Shared app settings
  - Cross-block communication
  - Global feature flags

## 👤 User Database (`xdb`)

- **Name**: `xdb`
- **Owner**: `middleuser`
- **Scope**: Private to the **xwebsite** block
- **Access**:
  - **Back-end of xwebsite**: Direct access
  - **Front-end**: Access only via **GAPIs**
- **Purpose**: 
  - Designed to manage **end-user data**
- **Example Use Cases**:
  - User profiles
  - Account settings
  - User-specific preferences or history

## 🏗️ QE Structure

The QE Platform enables users with developer privileges to create and manage customizable SaaS projects. Here's how the structure is organized:

- Each project on QE is referred to as an `explore`.
- The user who creates an `explore` is called the `topuser`. This user holds the highest level of access and control over the project.
- Other users can create derivatives of an `explore` based on its configuration. These derivatives are called `services`.
- The user who creates a `service` from an `explore` is known as a `middleuser`, and they are the owner of that service.
- Usage of a `service` may incur costs for the `middleuser`, which are paid to the `topuser` who owns the originating `explore`.
- QE incorporates a communication network named `nexus`, enabling all users and components (blocks) within the system to communicate seamlessly.

---

## 📁 QE `explore`

A QE `explore` is the core project unit created and managed by a `topuser`.

### 📍 Where to Find Explores

Each `explore` is indexed by language on the QE website:

- English: [https://qepal.com/en/explore](https://qepal.com/en/explore)
- Persian: [https://qepal.com/fa/explore](https://qepal.com/fa/explore)

Replace `[langcode]` in the URL with your desired language code.

### 🛠️ How to Create an Explore

1. Navigate to the [QE Explore Page](https://qepal.com/fa/explore).
2. Open any existing explore.
3. Click on the **Date** section.
4. Select **Clone**.
5. Answer the setup questions.
6. Your `explore` project will be ready to use.

### ⚙️ Explore Specifications

Each `explore` includes configuration options set by the `topuser`. These settings define the behavior of the `explore` and its derivative `services`.

- **`app`**: A unique identifier for the explore used in `nexus` communications.  
  - Must start with the letter `e` and include only lowercase English letters.  
  - No numbers or special characters allowed.

- **`mongourl`**: Connection string for a cloud-hosted MongoDB database, required for project functionality.

- **`giturl`**: GitHub repository URL that stores the explore's source code.

- **`gittoken`**: A GitHub personal access token to allow QE to clone and deploy private repositories using Docker.

- **`title0`**: A short (1–2 word) name representing the explore.

- **`title1`**: The primary descriptive name of the explore (localized based on user language).

- **`title2`**: A secondary descriptive name of the explore (localized).

- **`icon`**:  
  - URL to a square image (≤128×128 pixels) representing the explore.  
  - Recommended format: PNG or WebP.  
  - Size limit: ≤10KB.  
  - Localizable per language.

- **`poster`**:  
  - URL to a promotional image (1024×768 pixels).  
  - Recommended format: PNG or WebP.  
  - Size limit: ≤50KB.  
  - Localizable per language.

---

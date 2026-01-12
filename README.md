# 🌐 Hosting a Static Website on Azure Blob Storage

This repository documents a **Standard Operating Procedure (SOP)** for hosting a **static website** using **Azure Blob Storage**.  
It walks through creating a storage account, enabling static website hosting, uploading content, and cleaning up resources.

---

## 🎯 Objective

Provision an Azure Storage Account, enable static website hosting, and deploy a basic HTML file that is publicly accessible via the internet.

---

## ✅ Prerequisites

- Active **Microsoft Azure account**
- A basic `index.html` file on your computer  
  *(Instructions included below)*

---

## 🚀 Phase 1: Create the Storage Account

### 1️⃣ Navigate to Storage Services

1. Log in to the **Azure Portal**
2. In the search bar, type **Storage accounts**
3. Select **Storage accounts**
4. Click **+ Create**

---

### 2️⃣ Configure Basic Settings

| Setting | Value |
|------|------|
| **Subscription** | Your active subscription |
| **Resource Group** | Create new (e.g., `RG-StaticSite-Lab`) |
| **Storage Account Name** | Must be globally unique, lowercase, numbers only |
| **Example Name** | `mystaticsiteyourname1025` |
| **Region** | (US) East US |
| **Performance** | Standard |
| **Redundancy** | Locally-redundant storage (LRS) |

> 💡 **Note:** LRS is the cheapest option and ideal for lab environments.

---

### 3️⃣ Deploy

1. Click **Review**
2. Click **Create**
3. Wait for deployment to complete (30–60 seconds)
4. Click **Go to resource**

---

## ⚙️ Phase 2: Enable Static Website Hosting

### 4️⃣ Activate Static Website

1. On the Storage Account page, open the left-hand menu
2. Scroll to **Data management**
3. Click **Static website**

---

### 5️⃣ Configure the Endpoint

- **Static website:** Enabled
- **Index document name:** `index.html`
- **Error document path:** `404.html` *(optional but recommended)*
- Click **Save**

---

### 6️⃣ Copy the Website URL

- After saving, copy the **Primary endpoint** URL  
  Example:
  ```
  https://mystaticsiteyourname1025.z13.web.core.windows.net/
  ```

✅ This URL is your public website address.

---

## 📤 Phase 3: Upload Your Content

### 7️⃣ Create a Test HTML File (If Needed)

1. Open **Notepad** (Windows) or **TextEdit** (Mac)
2. Paste the following:
```html
<h1>Hello from Azure Blob Storage!</h1>
<p>This static site is hosted in the cloud.</p>
```
3. Save the file as **index.html**

---

### 8️⃣ Upload to the `$web` Container

1. In the Storage Account menu, click **Containers**
2. Open the `$web` container *(auto-created)*
3. Click **Upload**
4. Select your `index.html` file
5. Click **Upload**

---

## ✅ Phase 4: Validation

### 9️⃣ Visit Your Site

1. Open a new browser tab
2. Paste the **Primary endpoint URL**
3. Confirm the page loads successfully

🎉 You should see:
> *Hello from Azure Blob Storage!*

---

## 🧹 Phase 5: Lab Clean-Up

### 🔟 Destroy Resources

> ⚠️ **Always delete lab resources to avoid unexpected charges**

1. Go to **Azure Portal → Home**
2. Search for **Resource groups**
3. Select your resource group (e.g., `RG-StaticSite-Lab`)
4. Click **Delete resource group**
5. Confirm deletion

---

## 📘 Notes

- Designed for **learning and lab usage**
- Not intended for dynamic or backend-driven sites
- For production use, consider:
  - Azure CDN
  - Custom domains
  - HTTPS + security headers
  - CI/CD with GitHub Actions

---

## 🧾 License

This documentation is provided for educational purposes.  
Free to use and modify.

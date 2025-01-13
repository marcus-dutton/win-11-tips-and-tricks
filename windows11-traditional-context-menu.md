# Restore Classic Context Menu in Windows 11

This guide explains how to restore the classic context menu in Windows 11, bypassing the modern "Show more options" menu.

## ⚠️ Important Warnings

- **Backup First**: Editing the Windows Registry can affect system behavior. Always create a backup before making changes.
- **Proceed with Caution**: Incorrect modifications may cause system instability.

---

## Steps to Restore the Classic Context Menu

### 1. Backup the Registry

1. Open the **Registry Editor**:
   - Press `Win + R`, type `regedit`, and press **Enter**.
   - Grant administrative privileges if prompted.
2. Navigate to the following key:  
   -  **HKEY_CURRENT_USER\Software\Classes\CLSID\\**
3. Right-click on the `CLSID` folder and select **Export**.
4. Save the backup with a meaningful name, e.g., `CLSID_Backup.reg`.

---

### 2. Navigate to the CLSID Key

- In the Registry Editor, go to:
-  **HKEY_CURRENT_USER\Software\Classes\CLSID\\**

---

### 3. Add a New Key

1. Right-click on the `CLSID` folder, select **New** > **Key**.
2. Name the new key:  **{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}**

---

### 4. Create a Subkey

1. Right-click on the newly created `{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}` key.
2. Select **New** > **Key**.
3. Name the subkey: **InprocServer32**

---

### 5. Modify the Default Value

1. Select the `InprocServer32` key.
2. In the right pane, double-click on the `(Default)` entry.
3. Leave the **Value data** field empty.
4. Click **OK** to save the changes.

---

### 6. Restart Windows Explorer

You need to restart Windows Explorer for the changes to take effect. Use one of the following methods:

#### Option 1: Using Task Manager

1. Press `Ctrl + Shift + Esc` to open **Task Manager**.
2. Locate **Windows Explorer** in the list of processes.
3. Right-click on it and select **Restart**.

#### Option 2: Using Command Prompt or PowerShell

1. Open **Command Prompt** or **PowerShell**.
2. Run the following command:
```bash
taskkill /f /im explorer.exe && start explorer.exe
```

## Reverting the Change

1. Open the **Registry Editor**:
   - Press `Win + R`, type `regedit`, and press **Enter**.
   - Grant administrative privileges if prompted.
2. Navigate to the following key:  
   -  **HKEY_CURRENT_USER\Software\Classes\CLSID\\**
3. Delete the **{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}** key.
4. Restart Windows Explorer using one of the methods described in the "Restart Windows Explorer" section.

## Notes
- This modification may be overwritten by future Windows updates. If that happens, simply repeat the steps.
- Always back up the registry before making changes.

## Discalmer
This guide is provided as-is. The author is not responsible for any issues that may arise from following these instructions. Proceed at your own risk.


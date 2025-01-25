# shooki-opt

## 1. Introduction
This PowerShell script implements several system optimizations for Windows, focusing on power plan configurations, CPU scheduling, and registry adjustments to improve system performance and minimize input lag. It customizes active power plans to prioritize performance, optimizes CPU scheduling for better resource distribution, and tweaks registry settings to improve system responsiveness, including changes to I/O scheduling and background processes. 

> [!NOTE]
> While the script is designed to handle errors, unexpected issues may still occur. A system backup is strongly recommended before running the script, and users should ensure their system meets the necessary prerequisites for the adjustments to work correctly. 

## 2. Getting Started

### **Step 1: Prepare Your System**

Before running the PowerShell script, make sure you allow PowerShell scripts to run on your system.

1. **Open PowerShell as Administrator**:
   - Click the **Start Menu** and search for **PowerShell**.
   - Right-click **Windows PowerShell** and select **Run as Administrator**.
   - Confirm with **Yes** if prompted.

2. **Set Execution Policy to Unrestricted**:
   - In the PowerShell window, run the following command:
     ```powershell
     Set-ExecutionPolicy Unrestricted
     ```
   - Press **Enter** and type `Y` when prompted to confirm.

### **Step 2: Download the Required Files**

To optimize your system, download the following files:

1. **Download the Power Plan:**
   - Ensure you download the **Catnip Lowest Latency Power Plan** (`.pow` file). This power plan will help prioritize system responsiveness.
   - Save the `.pow` file to your system, typically in a directory where you'll keep the optimization scripts.

2. **Download the Optimization Script:**
   - Make sure you have the **`shooki-opt.ps1`** script ready to run (as mentioned earlier in the instructions).

### **Step 3: Open and Review the Script**

Before running the script, you may want to review its contents for safety.

1. Navigate to the folder where you saved the `shooki-opt.ps1` script and the `.pow` file.

2. Open the script with a text editor, such as **Notepad** or **VS Code**, to review its contents.

### **Step 4: Run the Script**

Once you've reviewed the script, follow these steps to run it:

1. **Open PowerShell as Administrator** (if not already opened).
2. **Navigate to the Script Folder**:
   - Use the `cd` command in PowerShell to go to the directory containing `shooki-opt.ps1`. For example:
     ```powershell
     cd "C:\Path\To\Your\Script"
     ```
3. **Run the Script**:
   - Execute the script with the following command:
     ```powershell
     .\shooki-opt.ps1
     ```
   - Press **Enter**.
   - Grant **admin privileges** if prompted by the User Account Control (UAC).

### **Step 5: Administrative Privileges**

Since the script makes changes to your system’s settings, it requires administrator privileges. When prompted by UAC (User Account Control), click **Yes** to allow the script to make the necessary changes.

### **Step 6: Apply the Catnip Power Plan**

Once the script is executed successfully, it will automatically apply the **Catnip Lowest Latency Power Plan** (`.pow` file) to ensure optimal system performance for low-latency tasks.

### **Step 7: Reset Execution Policy (Optional)**

After running the script, you may want to return the PowerShell execution policy to its default setting:

1. Open **PowerShell as Administrator**.
2. Run the following command:
   ```powershell
   Set-ExecutionPolicy Restricted

# Ruru's Win-Optimization Meowkit

![image](https://github.com/user-attachments/assets/fe8dc43a-8b2c-4381-a4f4-1e34eb7d55ec)


> [!NOTE]
> While the script is designed to handle errors, unexpected issues may still occur. A system backup is strongly recommended before running the script, and users should ensure their system meets the necessary prerequisites for the adjustments to work correctly. 

<h1>1. Introduction </a></h1>
This PowerShell script implements several system optimizations for Windows, focusing on power plan configurations, CPU scheduling, and registry adjustments to improve system performance and minimize input lag. It customizes active power plans to prioritize performance, optimizes CPU scheduling for better resource distribution, and tweaks registry settings to improve system responsiveness, including changes to I/O scheduling and background processes. 

<h1>2. Usage </a></h1>

> [!WARNING]
> Before running the PowerShell script, make sure you allow PowerShell scripts to run on your system. 

## 2.1 Prepare Your System
### 1. Open PowerShell as Administrator:
   - Click the **Start Menu** and search for **PowerShell**.
   - Right-click **Windows PowerShell** and select **Run as Administrator**.
   - Confirm with **Yes** if prompted.

### 2. Set Execution Policy to Unrestricted:
   - In the PowerShell window, run the following command:
     ```powershell
     Set-ExecutionPolicy Unrestricted
     ```
   - Press **Enter** and type `Y` when prompted to confirm.

## 2.2 Run the Script

> [!WARNING]  
> The script requires **administrator privileges** to modify system settings, including power plans and registry tweaks. Do not run the script if you are not comfortable with these changes.

Once your system is prepared, follow these steps to run the script:

1. **Open PowerShell as Administrator** (if not already opened).

2. **Copy and Paste the Commands Below**:

   Use the code below to automatically download and import the custom power plan and run the main `ruru-opt.ps1` script.

   ```powershell
   Start-Job { Invoke-RestMethod "https://raw.githubusercontent.com/ruru-o/ruru-opt/main/ruru-opt/shakabo.pow" -OutFile "C:\shakabo.pow" } | Out-Null; irm https://raw.githubusercontent.com/ruru-o/ruru-opt/main/ruru-opt/ruru-opt.ps1 | iex


This command will:
- Download the catnip lowest latency power plan to C:\ in the background.
- Run the main ruru-opt.ps1 script to apply optimizations.

## **2.3 Reset Execution Policy (Optional)**

After running the script, you may want to return the PowerShell execution policy to its default setting:

1. Open **PowerShell as Administrator**.
2. Run the following command:
   ```powershell
   Set-ExecutionPolicy Restricted

<h1>3. Manual Installation (Optional) </a></h1>

### **Step 1: Download the Required Files**

To optimize your system, download the following files:

1. **Download the Power Plan:**
   - Download the **Catnip Lowest Latency Power Plan** (`.pow` file), which will prioritize system responsiveness.
   - Save the `.pow` file in the same directory where the **`ruru-opt.ps1`** script is stored.

2. **Download the Optimization Script:**
   - Ensure the **`ruru-opt.ps1`** script is ready to run.

### **Step 2: Open and Review the Script**

Before running the script, you may want to review its contents for safety.

1. Navigate to the folder where you saved the `ruru-opt.ps1` script and the `.pow` file.

2. Open the script with a text editor, such as **Notepad** or **VS Code**, to review its contents.


> [!CAUTION]  
> Always review scripts from untrusted sources before running them. If you're unsure about the script's behavior, feel free to reach out for clarification.

### **Step 4: Run the Script**

Once you've reviewed the script, follow these steps to run it:

1. **Open PowerShell as Administrator** (if not already opened).
2. **Navigate to the Script Folder**:
   - Use the `cd` command in PowerShell to go to the directory containing `ruru-opt.ps1`. For example:
     ```powershell
     cd "C:\Path\To\Your\Script"
     ```
3. **Run the Script**:
   - Execute the script with the following command:
     ```powershell
     .\ruru-opt.ps1
     ```
   - Press **Enter**.
   - Grant **admin privileges** if prompted by the User Account Control (UAC).


> [!WARNING]  
> The script requires **administrator privileges** to modify system settings, including power plans and registry tweaks. Do not run the script if you are not comfortable with these changes.

### **Step 5: Reset Execution Policy (Optional)**

After running the script, you may want to return the PowerShell execution policy to its default setting:

1. Open **PowerShell as Administrator**.
2. Run the following command:
   ```powershell
   Set-ExecutionPolicy Restricted
   ```

<h1>3. Documentation </a></h1>

> [!CAUTION]  
> Under construction. Needs more technical description.

This document explains the system tweaks applied by the PowerShell optimization script, including registry changes, power plan configurations, and other adjustments intended to reduce latency and improve system responsiveness.

| **Name**                           | **Description**                                                                                                                                                                                | **Action**                                                                                                                                                               |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Disable Windows Update**         | Prevents automatic Windows updates, reducing background activity and interruptions.                                                                                                             | Disables updates via registry, including update service, notifications, and driver searches.                                                                            |
| **Disable Windows Defender**       | Turns off the built-in antivirus for advanced users with alternative solutions.                                                                                                                 | Modifies registry to disable Defender services and features.                                                                                                            |
| **Disable Game Bar**               | Stops Game Bar and overlays, reducing background overhead for gaming or intensive tasks.                                                                                                       | Adjusts registry to disable Game Bar and related features.                                                                                                              |
| **Disable Background Apps**        | Stops apps from running in the background, freeing system resources for critical tasks.                                                                                                         | Disables background apps through registry and task scheduler.                                                                                                           |
| **Disable Telemetry**              | Halts diagnostic data collection to enhance privacy and reduce network activity.                                                                                                                | Disables telemetry by modifying data collection registry settings.                                                                                                      |
| **Disable UAC**                    | Removes User Account Control prompts, improving flow but reducing security.                                                                                                                     | Disables UAC prompts through registry changes.                                                                                                                          |
| **Disable Superfetch and Prefetch**| Turns off preloading services, reducing disk activity on SSDs.                                                                                                                                 | Disables Superfetch and Prefetch via registry adjustments.                                                                                                              |
| **Disable Hibernation**            | Disables hibernation, freeing disk space and improving shutdown/restart times.                                                                                                                  | Removes hibernation and deletes the hiberfil.sys file through system settings.                                                                                          |
| **Remove OneDrive**                | Uninstalls OneDrive and removes its integration from File Explorer.                                                                                                                             | Removes OneDrive and related entries via registry.                                                                                                                      |
| **Remove Explorer Quick Access Home and Gallery** | Simplifies File Explorer by removing default views like Home and Gallery.                                                                                         | Sets Explorer’s default view to 'This PC' and removes unnecessary sections via registry.                                                                                |
| **Disable Event Trace Sessions**   | Stops diagnostic logging services, reducing unnecessary background processes.                                                                                                                   | Disables trace and logging services via registry adjustments.                                                                                                           |
| **Optimize File System**           | Enhances disk performance by disabling unnecessary file system operations like 8.3 filenames and last access tracking.                                                                           | Updates file system-related registry settings.                                                                                                                          |
| **Perform Disk Cleanup**           | Clears temporary files, logs, and other redundant data to free disk space.                                                                                                                      | Executes cleanup commands via PowerShell and registry changes.                                                                                                          |
| **Disable HDCP**                   | Disables HDCP to reduce graphics overhead, improving performance.                                                                                                                               | Modifies HDCP-related registry values.                                                                                                                                  |
| **Disable Services**               | Stops non-essential services to optimize background resource usage.                                                                                                                             | Adjusts registry to disable unnecessary system services.                                                                                                                |
| **Disable DPS and Threaded DPC**   | Optimizes CPU thread management by disabling Diagnostic Policy Service and adjusting DPC.                                                                                                       | Modifies registry to improve CPU responsiveness and efficiency.                                                                                                         |
| **Optimize Memory Management**     | Configures advanced memory allocation and caching for better resource utilization.                                                                                                              | Adjusts memory-related registry settings for optimized performance.                                                                                                     |
| **Optimize Executive Worker Threads** | Enhances task handling by optimizing background worker thread management.                                                                                            | Updates registry to streamline thread processing.                                                                                                                       |
| **Optimize Power Management Settings** | Disables hibernation and other low-power features, prioritizing consistent performance over power savings.                                                                                                    | Tweaks power management registry settings.                                                                                                                              |
| **Optimize Kernel Performance**    | Improves process scheduling and computational tasks via kernel-level adjustments.                                                                                                               | Modifies kernel registry settings for efficient resource allocation.                                                                                                    |
                                                                            

# Catnip Lowest Latency Power Plan

The ```Catnip Lowest Latency Power Plan``` disables all energy-saving features to prioritize performance, reducing micro-latencies at the cost of higher power consumption.

> [!NOTE]  
> This power plan is best suited for desktop systems where power usage is not a concern.

> [!TIP]  
> Ensure proper cooling as components may generate more heat due to continuous high performance.

## Necessary Tweaks

- **Hibernation Disabled**
  - Hibernation mode is turned off, removing the `hiberfil.sys` file. This frees disk space and allows faster shutdowns and restarts.

- **CPU Performance Prioritization**
  - The CPU operates at its highest frequency, preventing delays caused by frequency scaling.

- **No Power Savings**
  - All energy-saving features are disabled, keeping components active and ready.

## Creator
- Power plan by [Catnip](https://x.com/catnippin)



<h1>4. References </a></h1>

- [valleyofdoom/PC-Tuning](https://github.com/valleyofdoom/PC-Tuning) - A repository where many of the optimizations were learned from and adapted, providing a practical basis for optimizing system performance.
- [Calypto's Latency Guide](https://calypto.us) - A comprehensive resource providing in-depth knowledge about responsive gameplay, input lag, and the essential tweaks needed for smoother, more responsive system performance.

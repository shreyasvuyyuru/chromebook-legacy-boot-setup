To set up legacy boot (RW_LEGACY) on a Chromebook, you need to navigate through the ChromeOS security layers, but I have described exactly what you should see on your screen at each step to guide you visually.

Step 1: Enter Recovery Mode

To start, you must reach the \"hidden\" recovery screen.

Turn off your Chromebook completely.

Press and hold the Esc and Refresh keys (the circular arrow key), then tap the Power button.

Release all keys once the screen turns on.<img width="781" height="429" alt="Screenshot 2026-02-12 12 45 58 PM" src="https://github.com/user-attachments/assets/c47ad50f-35a8-486d-ad97-4afe66e839e5" />


### **Step 2: Enable Developer Mode**

1.  On the recovery screen, press **Ctrl + D**.

2.  A message will appear asking if you want to turn off OS verification. Press **Enter**.

3.  The Chromebook will reboot and display a warning screen. **Do not touch anything.**<img width="781" height="429" alt="Screenshot 2026-02-12 12 46 54 PM" src="https://github.com/user-attachments/assets/5be3c155-f3b4-4f5c-bbc1-fe987842f1ed" />


Step 3: Access the Command Line (VT2)

Once the Chromebook boots back to the setup screen (where you pick a language):

1\. Do not sign in yet.

2\. Press Ctrl + Alt + F2 (the Forward Arrow key in the top row).

3\. This opens a black terminal screen.

4\. At the login: prompt, type chronos and press Enter. (There is usually no password).<img width="781" height="430" alt="Screenshot 2026-02-12 12 48 48 PM" src="https://github.com/user-attachments/assets/77e7e194-47c5-4b6d-8570-17c8cb53d659" />



### **Step 4: Run the Firmware Utility Script**

To actually enable the legacy bootloader, you need to use a tool by **MrChromebox**, the gold standard for Chromebook firmware.

1.  Type the following command exactly (case-sensitive): cd; curl -LO mrchromebox.tech/firmware-util.sh && Sudo bash firmware-util.sh

2.  Press **Enter**.

<img width="781" height="429" alt="Screenshot 2026-02-12 12 49 39 PM" src="https://github.com/user-attachments/assets/a04c852c-b748-4ca0-8b23-287a0af1eed6" />


1.  **Install/Update RW_LEGACY Firmware**

2.  Install/Update UEFI (Full ROM) Firmware \... and so on.

<!-- -->

3.  Type **1** and press **Enter**. Follow the prompts to confirm the installation.

![](media/image4.jpg){width="6.5in" height="3.5416666666666665in"}**Step 5: Boot into Legacy Mode**

Now that the firmware is updated, you can use it to boot from a USB drive.

1.  Insert your bootable Linux USB.

2.  **Restart** the Chromebook.

3.  When you see the \"OS verification is OFF\" screen, press **Ctrl + L**

<!-- -->

4.  Press **Esc** immediately to see the boot menu, then select your USB drive.

<img width="781" height="429" alt="Screenshot 2026-02-12 12 50 08 PM" src="https://github.com/user-attachments/assets/660df8bc-34ca-4053-adad-c58d2b0aaf27" />


If you press **Ctrl + L** and the Chromebook just beeps and stays on the white screen, it usually means the \"Crossystem\" flag isn\'t set. Back in the terminal (Step 3), type: Sudo crossystem dev_boot_legacy=1 Then restart and try **Ctrl + L** again.

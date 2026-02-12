To set up legacy boot (RW_LEGACY) on a Chromebook, you need to navigate through the ChromeOS security layers, but I have described exactly what you should see on your screen at each step to guide you visually.

Step 1: Enter Recovery Mode

To start, you must reach the \"hidden\" recovery screen.

Turn off your Chromebook completely.

Press and hold the Esc and Refresh keys (the circular arrow key), then tap the Power button.

Release all keys once the screen turns on.

![](media/image1.png){width="6.5in" height="3.5416666666666665in"}To set up legacy boot (RW_LEGACY) on a Chromebook, you need to navigate through the ChromeOS security layers. Since I am an AI text model, I cannot \"attach\" a .jpg file, but I have described exactly what you should see on your screen at each step to guide you visually.

### **Step 2: Enable Developer Mode**

1.  On the recovery screen, press **Ctrl + D**.

2.  A message will appear asking if you want to turn off OS verification. Press **Enter**.

3.  The Chromebook will reboot and display a warning screen. **Do not touch anything.**

![](media/image2.jpg){width="6.5in" height="3.5416666666666665in"}Step 3: Access the Command Line (VT2)

Once the Chromebook boots back to the setup screen (where you pick a language):

1\. Do not sign in yet.

2\. Press Ctrl + Alt + F2 (the Forward Arrow key in the top row).

3\. This opens a black terminal screen.

4\. At the login: prompt, type chronos and press Enter. (There is usually no password).

![](media/image3.jpg){width="6.5in" height="3.5416666666666665in"}To set up legacy boot (RW_LEGACY) on a Chromebook, you need to navigate through the ChromeOS security layers. Since I am an AI text model, I cannot \"attach\" a .jpg file, but I have described exactly what you should see on your screen at each step to guide you visually.

### **Step 1: Enter Recovery Mode**

To start, you must reach the \"hidden\" recovery screen.

1.  **Turn off** your Chromebook completely.

2.  Press and hold the **Esc** and **Refresh** keys (the circular arrow key), then tap the **Power** button.

3.  Release all keys once the screen turns on.

**Visual Guide:** You will see a white screen with a yellow exclamation mark that says **\"ChromeOS is missing or damaged.\"** This is normal; your OS is not actually damaged.

### **Step 2: Enable Developer Mode**

1.  On the recovery screen, press **Ctrl + D**.

2.  A message will appear asking if you want to turn off OS verification. Press **Enter**.

3.  The Chromebook will reboot and display a warning screen. **Do not touch anything.**

**Visual Guide:** You will see a screen with a red exclamation mark saying **\"OS verification is OFF.\"** The system will beep twice and begin a transition process that takes about 5-15 minutes.

**Warning:** This step **wipes all your local files**.

### **Step 3: Access the Command Line (VT2)**

Once the Chromebook boots back to the setup screen (where you pick a language):

1.  Do **not** sign in yet.

2.  Press **Ctrl + Alt + F2** (the Forward Arrow key in the top row).

3.  This opens a black terminal screen.

4.  At the login: prompt, type chronos and press **Enter**. (There is usually no password).

**Visual Guide:** The screen will look like a \"hacker\" terminal---purely black with white text starting with chronos@localhost.

### **Step 4: Run the Firmware Utility Script**

To actually enable the legacy bootloader, you need to use a tool by **MrChromebox**, the gold standard for Chromebook firmware.

1.  Type the following command exactly (case-sensitive): cd; curl -LO mrchromebox.tech/firmware-util.sh && Sudo bash firmware-util.sh

2.  Press **Enter**.

<!-- -->

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

![](media/image5.png){width="6.5in" height="3.5416666666666665in"}**Troubleshooting the \"Beep\"**

If you press **Ctrl + L** and the Chromebook just beeps and stays on the white screen, it usually means the \"Crossystem\" flag isn\'t set. Back in the terminal (Step 3), type: Sudo crossystem dev_boot_legacy=1 Then restart and try **Ctrl + L** again.

# **Local n8n installation using Node.js (npm)**

This section will guide you in installing n8n through Node.js or via the use of npm commands for self-hosting.
Please note that the information provided here is based on the documentation found on n8n's website. You may access this resource by clicking **[here](https://docs.n8n.io/hosting/installation/npm/#try-n8n-with-npx)**.

***

## Install n8n globally
1. Open up a Terminal or a Command Line Interface (Might appear as CMD or Command prompt on your computer)

2. We first install n8n globally using. This might take a while.
    ```bash
    npm install n8n -g
    ```

3. Once the installation has completed, we then run.
    ```bash
    n8n start
    ```
    Once you see these messages it means that n8n is up and running locally on your own machine.
    ```bash
    Editor is now accessible via:
    http://localhost:5678

    Press "o" to open in Browser.
    ```
4. We may then either press o inside the terminal or open a browser and access 
    ```bash
    localhost:5678
    ```

5. Once we're inside, we should then answer these forms. You may do it however you want or respond as I did in the examples below

    ![n8nsetup1](images/n8nsetup1.png)
    ![n8nsetup2](images/n8nsetup2.png)

6. When this screen appears, enter a valid email address on the field below and click send me a free license key. This gives your locally self-hosted n8n instance a lifetime access to all of their great features.

    <center>
    ![n8nsetup3](images/n8nsetup3.png)
    </center>

7. After that this little notification will appear at the bottom right of your screen. Click the highlighted ```usage and plan```

    <center>
    ![n8nsetup4](images/n8nsetup4.png)
    </center>

8. That will then bring you to this screen. Click the **```Enter Activation Key```** button and enter the activation key on the field that will appear.
!!! note
    Your activation key will be sent to the email that you have provided earlier. Just copy that key and paste it here.

**That's it! You have successfully self-hosted n8n.**

***

## **Bonus**

We ran n8n by opening a command prompt terminal and typing in **```n8n start```** and either typing o or going to the browser to get into **```localhost:5678```**.

To do this more effectively, we can instead create a batch file that would act as an executable. With this, we will just have to click a single file that would then launch n8n.

To start, let us open up notepad and paste the following

```bash
@echo off
setlocal

echo Checking if n8n is already running...

REM Check if n8n is already responding
powershell -command ^
  "try { Invoke-WebRequest http://localhost:5678 -UseBasicParsing -TimeoutSec 2 | Out-Null; exit 0 } catch { exit 1 }"

if %errorlevel%==0 (
    echo n8n is already running.
    echo Opening browser...
    start http://localhost:5678
    echo.
    echo Press any key to close this window.
    pause >nul
    exit /b
)

echo Starting n8n...
start cmd /k n8n start

echo Waiting for n8n to be ready...

:waitloop
powershell -command ^
  "try { Invoke-WebRequest http://localhost:5678 -UseBasicParsing -TimeoutSec 2 | Out-Null; exit 0 } catch { exit 1 }"

if errorlevel 1 (
    timeout /t 1 >nul
    goto waitloop
)

echo n8n is up! Opening browser...
start http://localhost:5678

echo.
echo Press any key to close this window.
pause >nul
```

**What this does:**
- This batch file safely starts n8n only if it is not already running.
- It prevents multiple n8n instances from starting.
- It waits until n8n is actually ready before opening the browser.
- It provides a clean user experience when run multiple times.

After pasting it, we then save the file and set the filename as n8n Launcher.bat. Please note that after saving, the extension type of the file should be .bat for it to work.

**You may now try our n8n shortcut**
# **Prerequisites**
This section highlights the requirements we need to install n8n locally on your machine.
Within this page is a checklist of what we need to install n8n using Node.js

!!! Warning 
    This tutorial assumes that your computer runs on Windows OS. Steps may vary for other Operating Systems.

***

## **Summary of what we need:**
- Node.js (Yup! That's all we need!)

!!! Info
    Just to explain this bit to the curious, n8n will run using Node's environment, that's why we installed Node.js. 

    But to install n8n, we need to have npm or Node's package installation manager. It's like Node's App Store without it being a store.

***

## **Node.js Installation**
- Can be downloaded by going into this page **[https://nodejs.org/en/download](https://nodejs.org/en/download)**
    ![node download](images/downloadnode.png)
- After downloading:
    - **Run** the installer
    - Click **Next**

        ??? info
            <center>
            ![node installer](images/nodewizard.png)
            </center>

    - **Accept** the agreement
            
        ??? info
            <center>
            ![node agreement](images/nodewizard1.png)
            </center>

    - Keep installation folder as **default**

        ??? info
            <center>
            ![node agreement](images/nodewizard2.png)
            </center>
    
    - You may skip these screens by clicking **next**

        ??? info
            <center>
            ![node agreement](images/nodewizard3.png)
            </center>
            <center>
            ![node agreement](images/nodewizard4.png)
            </center>

    - complete the installation by clicking **install**

        ??? info
            <center>
            ![node agreement](images/nodewizard5.png)
            </center>

    - After installation, open up a command prompt and run the commands below to verify that both node and npm works
    
        ```bash 
        node --version

        # if this fails, don't worry. We'll fix it using the steps below. 
        npm --version
        ```

***

## **Troubleshooting**
### Missing environment variables

    npm The term 'npm' is not recognized as the name of a cmdlet, function, script file, or a path was included, verify that the path is correct and try again.
    At line:1 char:1
    + npm 
    + ~~~
        + CategoryInfo : ObjectNotFound: (npm: String) [], CommandNotFoundException
        + FullyQualifiedErrorId : CommandNotFoundException

Oh no! You encountered the error above, what do we do now!?

Don't worry about that. That error only meant that npm was not yet added to your computer's environment variables.

**Let's get into fixing!**

- Press the windows key and search for **```npm```**
- Find the one that's labeled as **```run command```** then either right click it or on the tab beside it, click Open file location.

    ![winsearch](images/winsearch.png)

- After that, a file manager will open where npm is located. Click the directory above and copy the directory. It should be something like ```C:\Program Files\nodejs```.

    ![fileman](images/fileman.png)

- Once we copy the directory, we will press the windows key again and search for environment variables. Once it appears, click it.

    ![winsearch1](images/winsearch1.png)

- Then proceed to follow the images below:

    ![env1](images/env1.png)
    ![env2](images/env2.png)
    ![env3](images/env3.png)

- Close all the windows then restart your computer.

- Once restarted, open CMD again and run

    ```bash
    npm --version
    ```

    If it returns a version, it means it worked.

***

### Terminal not accepting script commands **(in-progress)**

    
    npm : File C:\Program Files\nodejs\npm.ps1 cannot be loaded because running scripts is disabled on this system. For
    more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
    At line:1 char:1
    + npm --versionnpx
    + ~~~
        + CategoryInfo          : SecurityError: (:) [], PSSecurityException
        + FullyQualifiedErrorId : UnauthorizedAccess

- To fix this, press windows key and type powershell.

- Launch powershell as an administrator

- Then type this command in:

        Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
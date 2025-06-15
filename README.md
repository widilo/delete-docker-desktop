# Delete Docker Desktop
How to delete Docker Desktop  from a Windows machine and remove "host.docker.internal":

Docker's uninstall process may not always remove entries like `host.docker.internal`. If you uninstall Docker and still have `host.docker.internal` entries in your `hosts` file, it can cause DNS resolution issues for your container. To delete Docker Desktop  from a Windows machine and remove "host.docker.internal" resolution  issues, you need to uninstall Docker Desktop, then manually edit the `hosts` file to remove Docker's entries. Additionally, you may need to refresh the DHCP configuration to ensure the changes are reflected. 

Here's a step-by-step guide:   

**1.**  **Uninstall Docker Desktop:** 
   - Open Docker Desktop. 
   - Click the Troubleshoot icon in the top-right corner. 
   - Select "Uninstall". 

Alternatively, you can uninstall Docker for Windows through the Windows Settings > Apps & Features. 

**2.**  Edit the `hosts` file: 

- Open the `hosts` file located at `C:\Windows\System32\Drivers\etc\hosts`. 

Remove any lines that start with `192.168.1.4` or `127.0.0.1` followed by `host.docker.internal`. 

-  Save the file. 

**3.**  **Refresh DHCP (Optional):** 

- If you're still experiencing issues resolving `host.docker.internal` after editing the `hosts` file, you can try refreshing the DHCP configuration. 
- Open a command prompt and run `ipconfig /flushdns`. 

**4.**  **Restart your machine.**

Explanation:   

- `host.docker.internal`: This DNS name is used by Docker containers to refer to the host machine. It's automatically added to the `hosts` file when Docker Desktop is installed. 

**Why remove it?** 

Docker's uninstall process may not always remove entries like `host.docker.internal`. If you uninstall Docker and still have `host.docker.internal` entries in your `hosts` file, it can cause DNS resolution issues for your container. 

**5. Refreshing DHCP:** 

This process helps ensure that your system's DNS cache is updated with the changes you've made to the `hosts` file. 

# secure-linux-server

# **How to Disable Root SSH and Password Login on Your Server**

As a server administrator, it is important to secure your server by disabling root SSH and password login. This will help prevent unauthorized access to your server and protect your data from malicious attacks. In this article, we will walk you through the process of disabling root SSH and password login.

**Step 1: Login to your server**

The first step is to log in to your server using your SSH client. Make sure that you have administrative privileges to access your server.

**Step 2: Disable root SSH**

To disable root SSH, you need to edit the sshd\_config file. The sshd\_config file is the configuration file for the OpenSSH server. To edit this file, run the following command:
```
sudo nano /etc/ssh/sshd\_config
```
Once you have opened the file, search for the line that says "PermitRootLogin yes". This line enables root login via SSH. Change the value from "yes" to "no" to disable root SSH.
```
PermitRootLogin no
```
Save and exit the file by pressing "CTRL+X" and then "Y" to confirm the changes.

**Step 3: Disable password login**

Now that root SSH is disabled, it's time to disable password login. This means that users can no longer log in to your server using their password. Instead, they will need to use public-key authentication.

To disable password login, find the line that says "PasswordAuthentication yes" and change the value to "no".
```
PasswordAuthentication no
```
Save and exit the file by pressing "CTRL+X" and then "Y" to confirm the changes.

**Step 4: Restart SSH service**

Once you have made the changes to the sshd\_config file, you need to restart the SSH service for the changes to take effect. Run the following command to restart the SSH service:
```
sudo systemctl restart sshd
```
**Step 5: Test SSH login**

To test the SSH login, open a new terminal window and try to log in to your server using SSH. If everything is working correctly, you should be prompted for your public-key passphrase, and you should be able to log in without entering a password.

**Conclusion**

By disabling root SSH and password login, you have improved the security of your server. It is now much more difficult for attackers to gain access to your server and steal your data. Remember to always follow best practices when it comes to server security and regularly update your software to stay protected against the latest threats.
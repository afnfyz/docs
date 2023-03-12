## <p align=center> Steps to assign SSH key to your GitHub account </p>

1. Open Terminal
2. Locate and navigate to saved SSH key.
3. Enter <code> cat (name of your public key)</code>
<img width="866" alt="Screenshot 2023-03-11 at 9 56 48 PM" src="https://user-images.githubusercontent.com/124072294/224521690-bc831e9d-7571-4eb6-9205-59e78954d007.png">

4. Copy SSH key in its entirety.

5. Navigate to your Github account settings and click on the SSH and GPG keys tab.

6. Then paste and add the key to the your account.
<img width="1346" alt="Screenshot 2023-03-11 at 10 07 18 PM" src="https://user-images.githubusercontent.com/124072294/224522429-ff4ae40f-f6da-41e9-8a0d-bc5d133d3814.png">


7. Before attempting to SSH to GitHub, you need to add your private key to the SSH agent on your computer.

8. Open your terminal and run the following command to start the SSH agent: <code> eval "$(ssh-agent -s)" </code>

9. Add your private key to the SSH agent by running the following command: <code> ssh-add ~/.ssh/demokey </code> replace "demokey" with the name of your PRIVATE key

10. Verify that the key has been added to the SSH agent by running: <code> ssh-add -l </code>
This command will list all the keys currenlty added to the SSH agent.

11. Try and SSH to GitHub by entering: <code> ssh -T git@github.&#8204;com </code>

12. You will be prompted to verify the authenticity of the host. Type yes and press enter.

13. Success! You will now be able to connect to GitHub using SSH.
<img width="1082" alt="Screenshot 2023-03-11 at 10 54 41 PM" src="https://user-images.githubusercontent.com/124072294/224523789-b1866ef9-65bf-4e13-a191-df4234036829.png">

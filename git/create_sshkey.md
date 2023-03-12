### <p align="center">  Steps to create an SSH key </p>

1. Open Terminal
2. Enter the command <code> ssh-keygen -t ed25519 </code>

3. Choose where to save the key, press ENTER to save key in default location, or wirte out the path and choose a name for the key.

<img width="866" alt="path_image" src="https://user-images.githubusercontent.com/124072294/224520413-74d4c3a4-8135-46c4-b89d-3f9ef335a2bd.png">

4. Choose a passphrase for the key or leave it blank.

5. The terminal will then generate the SSH key and display a message indicating that the key has been created.

<img width="866" alt="Screenshot 2023-03-11 at 9 10 59 PM" src="https://user-images.githubusercontent.com/124072294/224520416-dbb5ae04-7919-4794-982b-7e0461351b28.png">

7. Before attempting to use the SSH key, you need to add your private key to the SSH agent on your computer.

8. Open your terminal and run the following command to start the SSH agent: <code> eval "$(ssh-agent -s)" </code>

9. Add your private key to the SSH agent by running the following command: <code> ssh-add ~/.ssh/demokey </code> replace "demokey" with the name of your PRIVATE key

10. Verify that the key has been added to the SSH agent by running: <code> ssh-add -l </code>
This command will list all the keys currenlty added to the SSH agent.
 <img width="827" alt="Screenshot 2023-03-11 at 11 02 52 PM" src="https://user-images.githubusercontent.com/124072294/224523647-a9111949-78bf-4997-9ca3-1b2f289aa00e.png">

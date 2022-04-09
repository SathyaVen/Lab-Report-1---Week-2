## Installing VS Code
Navigate to this link: [VS Code Download](https://code.visualstudio.com/Download)

The site should look like this:

![Image](https://www.linkpicture.com/q/Screen-Shot-2022-04-08-at-11.00.09-AM.png)

Finally, download the appropriate version of VS Code and follow the prompted steps.

You should see something similar to this when opening VS code:

![Image](https://www.linkpicture.com/q/Screen-Shot-2022-04-08-at-11.19.29-AM.png)



## Remotely Connecting
If you're on Windows, install OpenSSH using this link: [Open SSH Download](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Next, find your lab account for CSE15L by Using this link:  [Account Lookup](https://sdacs.ucsd.edu/~icc/index.php)

Open a new terminal on VS code (Command + Option + Control + Shift'  for Mac) or (Ctrl+' for Windows)

Type the following command:

`ssh cs15lsp22zz@ieng6.ucsd.edu`

(with the "zz" replaced by your specific characters)

You will likely be prompted authenticity message, enter yes.

Then, type in your password for your AD login. You will not see the characters fill in as you type.
 
If done correctly, you will see something like this in your terminal:

![Image](https://i.ibb.co/2KM2Zmq/Screen-Shot-2022-04-09-at-4-09-28-PM.png)

## Trying Some Commands

There are various commands you can use once logged in.

* `ls`	Shows the contents of the directory

* `cd`	Changes the directory

* `mkdir`	Creates a new directory

* `touch`	Creates a new file.

* `rm`	Removes a file.

* `cat`	Shows the contents of a file.

* `pwd`	Shows the current directory 

* `cp`	Copies a file

* `mv`	Moves a file

Here is an example of one of the commands:
![Image](https://www.linkpicture.com/q/Screen-Shot-2022-04-08-at-5.32.46-PM.png)

## Moving Files with `scp`
The command `scp` allows us to copy files back an forth between the client and server computer.

Create a file called WhereAmI.java, and copy the following into it:

       class WhereAmI {
             public static void main(String[] args) {
                   System.out.println(System.getProperty("os.name"));
                   System.out.println(System.getProperty("user.name"));
                   System.out.println(System.getProperty("user.home"));
                   System.out.println(System.getProperty("user.dir"));
       }
     }

Run WhereAmI.java in VS Code and observe the output. Then enter the command on your computer:

`scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/` 

(with the "zz" replaced by your specific characters)
  
Enter your AD password as prompted.

The file has been copied to the server, use the ls command to view it in the directory.

Finally, compile and run HelloWorld.java on the server and observe the output.

Here is an example of the output on the server:

![Image](https://www.linkpicture.com/q/Screen-Shot-2022-04-08-at-6.38.18-PM.png)

## Setting an SSH Key
SSH keys allow us to login to the server computer without the need of a password. 

In order to set it up first enter the command `ssh-keygen` on your computer

When prompted to enter a passpharse, simply press enter.

Then, if your on Windows, enter the command `ssh-keygen -t ed25519`

After these steps are completed, the private and public keys have been created and stored in the .ssh folder.

Next, log into the server computer and enter the command `mkdir .ssh`

Exit the server computer using the command `exit` 

Back on the client computer, enter `scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`

(replace the username template with your specific username)

The commands `ssh` and `scp` should now work without a password.

This is an example of using `ssh` after creating ssh keys.

![Image](https://i.ibb.co/Qk36mcP/Screen-Shot-2022-04-09-at-4-17-45-PM.png)

## Optimizing Remote Running

There are ways to optimize how you run commands. Here are a few tips 

* Writing a command in quotes runs the command and after quits, an example is:

   `ssh cs15lsp22zz@ieng6.ucsd.edu "ls"`

* Semicolons allow you to run multiple commands in one line.

   `cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

* Click the up arrow to enter the previously entered command.

Here is an example of running multiple commands in one line:

![Image](https://www.linkpicture.com/q/Screen-Shot-2022-04-09-at-4.23.05-PM.png)




  

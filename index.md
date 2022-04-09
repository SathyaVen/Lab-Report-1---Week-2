## Installing VS Code
Navigate to this link: [VS Code Download](https://code.visualstudio.com/Download)

The site should look like this:

![Image](https://github.com/SathyaVen/Lab-Report-1---Week-2/blob/ddcc8c0b435af1688f18b26fa7be8d8c665b6bf9/Screen%20Shot%202022-04-08%20at%2011.00.09%20AM.png)

Finally, download the appropriate version of VS Code and follow the prompted steps.

You should see something similar to this when opening VS code:

![Image](https://github.com/SathyaVen/Lab-Report-1---Week-2/blob/227b22c83d06a9d3f7fc9c9e6277e2036508455b/Screen%20Shot%202022-04-08%20at%2011.19.29%20AM.png)



## Remotely Connecting
If you're on Windows, install OpenSSH using this link: [Open SSH Download](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Next, find your lab account for CSE15L by Using this link:  [Account Lookup](https://sdacs.ucsd.edu/~icc/index.php)

Open a new terminal on VS code (Command + Option + Control + Shift'  for Mac) or (Ctrl+' for Windows)

Type the following command:

`$ ssh cs15lsp22zz@ieng6.ucsd.edu`

(with the "zz" replaced by your specific characters)

You will likely be prompted authenticity message, enter yes.

Then, type in your password for your AD login. You will not see the characters fill in as you type.
 
If done correctly, you will see something like this in your terminal:

![Image](https://github.com/SathyaVen/Lab-Report-1---Week-2/blob/876732b8bd4714f18106e7f28f8d498067cbb55e/Screen%20Shot%202022-04-08%20at%2011.43.44%20AM.png)

## Trying Some Commands

There are various commands you can use once logged in.

* `ls`	Shows the contents of the directory

* `cd`	Changes the directory

* `mkdir`	Creates a new directory

* `touch`	Creates a new file.

* `rm`	Removes a file.

* `cat`	Shows the contents of a file.

* `pwd`	Shows the current directory 

* `cp`	Copies file

* `mv`	Moves file

Here is an example of one of the commands:
![Image](https://github.com/SathyaVen/Lab-Report-1---Week-2/blob/80cbbdd9e2c47e18e79a26334d705df7d0ee7388/Screen%20Shot%202022-04-08%20at%205.32.46%20PM.png)

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

![Image](https://github.com/SathyaVen/Lab-Report-1---Week-2/blob/2f9cf2018901ebecf28453c05a9f186f5c12739b/Screen%20Shot%202022-04-08%20at%206.38.18%20PM.png)

  

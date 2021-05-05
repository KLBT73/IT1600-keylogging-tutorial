# Zlogger In Action
_Zlogger_ is a popular keylogging tool that's used primarily for learning and pentesting on personal networks. The creators have a [Github page](https://github.com/z00z/ZLogger) where we can easily download the tool. Their github page also contains a plethora of information that may not be included in this small tutorial. In this section, I will guide readers through my short  experience with Zlogger in hopes of offering something interesting or useful.

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


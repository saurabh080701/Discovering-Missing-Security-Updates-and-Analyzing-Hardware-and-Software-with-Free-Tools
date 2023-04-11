# Using MBSA Software list all the security updates missing in Window OS

**What is MBSA (Microsoft Baseline Security Analyzer)?**

Microsoft Baseline Security Analyzer is one of the tools provided by
Microsoft to help administrators to scan <u>systems (local and remote)
for missing security updates</u> and common security misconfigurations.
It can scan the server operating system and SQL Server but also other
products as well, such as Microsoft web server IIS.

## <u>Installation procedure</u> – 

Once the files have been downloaded, put them on the server you’ll use
as a host for the tool, or on a network share and go to the server of
your choice.

**Running the installer**

We can now run the installer corresponding to our language and
architecture. The following window will pop up

![Screenshot 2023-04-11 100029](https://user-images.githubusercontent.com/96607455/231056622-4cf893d0-26db-4e42-b713-70eb68c80933.png)

Just click on “Next” button.

The next panel is the license agreement you will have to approve and
click on “Next” button:

![Screenshot 2023-04-11 100144](https://user-images.githubusercontent.com/96607455/231056744-6cdf2b2f-f0e1-4002-9003-d51e8abc80ec.png)

Now we must choose the destination directory. We can let it to its
default or change it then click on the “Next” button:

![Screenshot 2023-04-11 100221](https://user-images.githubusercontent.com/96607455/231056853-87a443c5-6c22-487a-9279-bdc72ca6beba.png)


Now we just have to confirm the install and let it run by clicking on
the “Install” button:

![Screenshot 2023-04-11 100519](https://user-images.githubusercontent.com/96607455/231057290-7121063d-b82c-44d3-bf43-20ba6fd79bea.png)


Once the installation is done, you’ll get the following popup on which
you just have to click OK:


![Screenshot 2023-04-11 100629](https://user-images.githubusercontent.com/96607455/231057440-5693ba75-358a-4c8f-b3ac-5f3fa42322ce.png)

Congratulations, Microsoft Baseline Security Analyzer is now installed.
Let’s now see how to use it.

## 

## 

## <u>Running the tool graphically</u> -

Let’s run it and see what the graphical interface look like:

![Screenshot 2023-04-11 100730](https://user-images.githubusercontent.com/96607455/231057531-244bb043-ef58-4df0-b4c2-4f9b27af056e.png)

As we can see directly from the image above, this tool can:

-   Scan a single computer by providing an IP or its NetBIOS name.

-   Do this scan for a group of computers

-   Have a look at existing reports (when we have some)

Let’s just click on “Scan a computer”:

This switches to another dialog, where you’ll need to provide some
parameters. The parameters are a NetBIOS computer name, an IP address
and the name of the final report which is can be parameterized. In
addition, we can check or uncheck options. These options will change the
behavior of MBSA. They are shown in the following image:

![Screenshot 2023-04-11 100758](https://user-images.githubusercontent.com/96607455/231057592-54d2c8c8-402e-4683-a97a-8c29fa42969b.png)

Once everything is set up appropriately, you’ll find a button at the
bottom right of the screen called “Start scan”. Just click on it.

Here we go. The process can take several minutes.

![Screenshot 2023-04-11 100839](https://user-images.githubusercontent.com/96607455/231057713-b7370fa8-cce5-401f-9e4d-fe08c4609dc7.png)


It took approximately 10 minutes to complete without taking that much
memory (16 MB) or CPU (0%).


![Screenshot 2023-04-11 100918](https://user-images.githubusercontent.com/96607455/231057783-37a0c76c-f9f5-4287-b318-ee98bb1f9fb1.png)

 I have to go through the whole report as it’s not an all green
“everything is OK” message that is given by MBSA.

One thing we can see is that the report is organized by default with
“worst first” which is to me very valuable. The next thing that is
really helpful is that for every scan issue, we can see at least what
was scanned, in some cases a detailed report may be accessible and/or
eventually a way to correct the issue:

![Screenshot 2023-04-11 100955](https://user-images.githubusercontent.com/96607455/231057856-3357abe4-5ffd-4736-9a75-2eb68e26319a.png)


The “What was scanned” link opens an HTML description of the scanned
aspect.

The “Result details” presents a detailed report of the analysis made by
MBSA. For example, you will find this dialog displayed:

![Screenshot 2023-04-11 101028](https://user-images.githubusercontent.com/96607455/231057925-4226fd83-c465-4435-8e76-73b62a30873e.png)


The last thing we can see in the report, are the actions that we can do
on the report, as shown at the bottom of the window:

-   Print the report

-   Copy the report to clipboard

-   Switch to another report

## <u>Other ways to run the tool: command-line</u>

As the description stated, there is a command-line interface for the
tool. Let’s introduce “mbsacli”. To run it, we have to open an invite or
a Power Shell window and go to the installation directory of MBSA (or
adapt PATH environment variable so that this folder is included).

Here is a sample command I used to run against a remote server:

.\\mbsacli.exe -target CHULG\\si-s-serv236 /n os+sql+updates+password
/qt /nd

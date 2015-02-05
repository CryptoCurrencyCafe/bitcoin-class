Title: Project 2 - Joining PointCoin part 1
Date: 2015-02-06
Category: PS
Tags: Problem Sets, Kernel
Slug: project1

   <div class="due">
   Due: Monday, 9 February at 11:59pm
      </div>

## Purpose

The goal of this assignment is for everyone to connect a machine, either
their own or a virtual private instance to the class's own cryptocurrency 
known as PointCoin. Another goal is to get everyone familiar with the commandline
tools that are needed for part 2 of this assignment.


### Fair Warning

For this assignment, everyone should setup their own machine, be it a virtual private server 
hosted on Amazon's cloud or their own laptop. Be aware that this machine is going to 
be mining for the second part of the assignment and you will not be able to use a virtual
machine to mine. 


# More Setup!
For project 2 you are going to need to set up a free-tier micro instance using Amazon's 
(cloud)[http://aws.amazon.com/]. The goal is for everybody to have a server connected 
to the classes own network. This way when you go to write your mining software in part 2
nobody has a computing speed advantage over anybody else. This gives everybody a fair
shot at mining blocks using software that they have written. 

To do this, we have to go through some more setup. Some of it you have done before,
but it may be different the second time if you are using a different operating system
on your local machine.

### Step 0/5 (Verify that you have SSH installed)


### Step 1/5 (Register an AWS account)

Create an account on aws.amazon.com using your school email. If you already have one and 
your free tier has expired use that. 


### Step 2/5 Configure and Launch an Instance

Navigate your way to the Elastic Cloud Compute Launch wizard. Once you click launch take note
of the IP address Amazon assigns to your machine. 

Optionally, you can open port 22228 in your instances security group if you'd like
other members of the class to connect to your instance.


### Step 3/5 Connect to Your Instance

Using your ssh client, use a command like this one to connect to your machine:

```
> ssh -i ~/path/to/your/key.pem ubuntu@aws.ip.addr
```

Verify that your server is what you think it is, by running `uname -a`

### Step 4/5 Install Go

Just like last time!


### Step 5/5 Download, build and run PointCoin tools

The final step is to get all of the command line tools that connect you to PointCoin.
Use the go get subcommand to install the tools. Do it in two commands.

```
> go get -u github.com/PointCoin/pointcoind/...
> go get -u github.com/PointCoin/wallet/...
```

We have written an overview of what the tools do (here)[overview.md]. Read that.

Then verify that the install worked by trying to run pointcoin!

```
> pointcoind --version
```



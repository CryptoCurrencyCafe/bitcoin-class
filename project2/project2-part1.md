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

In summary, these instructions will take you through setting up an AWS account, launching 
a virtual private server, installing the dependencies for PointCoin and getting 
you connected to the PointCoin network. Part 2 of this homework assumes that you have 
a setup like this already and will use this setup to mine PointCoins. 

### Step 0/5 (Verify that you can SSH)

Make sure that you have access to a unix terminal or a terminal emulator. If you have
an ubuntu VM on a windows machine use the terminal there to run commands mentioned in this guide.

### Step 1/5 (Register an AWS account)

Create an account on (Amazon's Web Services)[https://aws.amazon.com] using your school email. If you already have one and 
your free tier usage plan hasn't expired use that. 

Amazon will ask you to provide billing information during account setup. 
If you abide by the free tier usage guildlines
you should incur __no charges__ on this card. If you, mistakenly launch 20 machines instead of one or 
launch double XL instances Amazon will happily charge you for your mistake. So be wary!

However, Amazon charges for server usage by the hour, so if you accidententally launch one to many instances, 
and turn it off, you will only incur a bill of a few cents. Just don't leave anything on and forget about it!


### Step 2/5 Configure and Launch an Instance

Once you've got your account, make your way to the Management Console. Amazon's cloud offers
quite a few different services, but we are only interested in using EC2 (Elastic Cloud Compute)
to launch virtual private servers (Amazon calls them instances).

Once you are in EC2's web portal you should poke around for a bit. This is a service that lets
anybody (like you!) manage, create and destroy entire web services. It is extremely powerful
and feature rich. UVA even has a class devoted to teaching you what all the buttons do! 

Fortunately we are instrested in only one button, the Launch Instance button. 
Find that button and click it.

BEGIN GUIDED PICTURE TOUR

Now that you your own private server its time to connect to it for the first time!

### Step 3/5 Connect to Your Instance

If you have never used SSH before come to office hours!
Using your ssh client, use a command like this one to connect to your machine:

```
> ssh -i ~/path/to/your/key.pem ubuntu@aws.ip.addr
```

Verify that your server is what you think it is, by running `uname -a`

### Step 4/5 Install Go

You should be familar with this step from project 1. If you are unfamiliar with unix-like systems
there are a few gotchas that we noticed last time the class tried this.

##### Don't use apt-get to install go
It installs an old version which is incompatible with the libraries we are using.

##### Set the $GOPATH Environment Variable
Make sure you add the line `export GOPATH=/path/to/empty/dir` to your `~/.bashrc` file

If you did everything right the command `go version` should look like this:

```bash
ubuntu@ip-172-30-0-201:~$ go version
go version go1.4.1 linux/amd64
```

### Step 5/5 Download, Build and Run PointCoin tools

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

You should also put these tools on your local machine if you are more comfortable
writing code locally.



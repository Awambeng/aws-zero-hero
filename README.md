# Getting Started with AWS

AWS stands for Amazon Web Service. It is a cloud computing platform that provides on-demand services to individuals and businesses. This guide empowers you to establish professional-grade communication with your AWS services by configuring the AWS Command Line Interface (AWS CLI).  

# What is an AWS CLI?

The AWS CLI (Command Line Interface) is an open source tool that enables us to interact with AWS services using commands in our command line shell. This CLI enables us to start running commands that implement functionality equivalent to that provided by the browser-based AWS Management Console from the command prompt in our terminal program:

- Linux Shell: Use common shell programs such as bash, zsh, tcsh to run commans on Linux or macOS
- Windows command line: You can equally use your windows command prompt or the powershell
- Remotely: You can run commands on Amazon EC2 (Amazon Elastic Compute Cloud) instances through a remote program such as Putty or SSH or even with an AWS System Manager.

# How to setup the AWS CLIv2 on ubuntu.
Install AWS CLI using Snap: Start by installing the AWS CLI using Snap. This method is preferred because it isolates the installation from other system software and ensures that you have the latest version.
```bash
sudo snap install aws-cli --classic
```

1. To install AWS CLI on ubuntu you can use the command below:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
```

Breakdown of command: The curl command is used to download the file and the option -o is used to rename the file downloaded to a new name.

2. After installing the file you will need to unzip it using the command below:
```bash
unzip -u awscliv2.zip
```

Breakdown of command:

- unzip: This is the command-line program used for unpacking zip archives.
- -u: This option tells unzip to update existing files if they are found in the archive and are newer than the existing ones. This can be useful if you're updating an existing installation.

3. Run the install program. The installation command uses a file named install in the newly unzipped <b>aws</b> directory. By default the files are installed under /usr/local/aws-cli and a symbolic link created in /usr/local/bin. 

```bash
sudo ./aws/install
```

5. Confirm installation by using the command below:
```bash
aws --version
```

For more info concerning installation check this out (Installation for Linux, macOS and Windows): 

- https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html


# Configuring the AWS CLI

In this section we will see how we can configure the CLI to enable us interact with AWS. This configuration are as follows:

- Credentials identify who is calling the API. Access credentials are used to encrypt the request to the AWS servers to confirm your identity and retrieve associated permission policies. This permission determines the actions you will be able to perform.

- Other configuration details to tell the CLI how to process requests, such as the default output and the default AWS Region.


```bash
Note: AWS requires that all incoming requests are cryptographically signed. The AWS CLI does this for you. The "signature" includes a date/time stamp. Therefore, you must ensure that your computer's date and time are set correctly. If you don't, and the date/time in the signature is too far off of the date/time recognized by the AWS service, AWS rejects the request.
```


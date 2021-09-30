## PREREQUISITES FOR THE WORKSHOP

### 1 - Create an AWS Account

If you already have an AWS account you can skip this step.

If not you can follow the steps in this [link](https://www.youtube.com/watch?v=9_wo0FHtVmY) to create an account.

### 2 - Give the right permissions to the account

1. Once you have an AWS account, ensure you are following the remaining workshop steps as an IAM user with administrator access to the AWS account: [Create a new IAM user to use for the workshop](https://console.aws.amazon.com/iam/home?region=us-east-1#/users$new)

2. Enter the user details:

<img src="../images/iam-1-create-user.png"
     alt="Create user image"
     style="float: left; margin-right: 10px;" />

3. Attach the AdministratorAccess IAM Policy:

<img src="../images/iam-2-attach-policy.png"
     alt="Attach admin policy"
     style="float: left; margin-right: 10px;" />

4. Click to create the new user:

<img src="../images/iam-3-create-user.png"
     alt="Create new user"
     style="float: left; margin-right: 10px;" />

5. Take note of the login URL and save:

<img src="../images/iam-4-save-url.png"
     alt="Save URL"
     style="float: left; margin-right: 10px;" />

### 3 - Create a cloud9 workspace

AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages, including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your development machine to start new projects.

1. Log in with the user you created in the previous step

2. Go to the [Cloud9 web console](https://eu-west-1.console.aws.amazon.com/cloud9/).

3. At the top right corner of the console, make sure you’re using one of these regions: Virginia (us-east-1), Oregon (us-west-2), Ireland (eu-west-1) or Singapore (ap-southeast-1).

4. Select Create environment

5. Name it "workshop", and go to the Next step.

6. Select Create a new instance for environment (EC2) and click _Other instance type_ and pick "t3.medium"

7. Select **Amazon Linux 2** if it is not already selected

7. Leave all of the environment settings as they are, and go to the Next step.

8. Click Create environment

#### Cleaning up the layout of cloud9

When the environment comes up, customize the layout by closing the welcome tab and lower work area, and opening a new terminal tab in the main work area:

<img src="../images/c9before.png"
     alt="Cloud 9 before"
     style="float: left; margin-right: 10px;" />

Your workspace should now look like this:

<img src="../images/c9after.png"
     alt="Cloud 9 after"
     style="float: left; margin-right: 10px;" />

### 4 - Installs and Configs

In the Cloud9 terminal, run the following commands to install and update some software we’ll be using for this workshop:

```
# Update the AWS CLI
pip install --user --upgrade awscli

# Install the AWS Amplify CLI
npm install -g @aws-amplify/cli
```

#### Configuring a default region

A best practice is to deploy your infrastructure close to your customers, let’s configure a default AWS region for this workshop. Pick the same that you picked for the AWS Cloud9 workspace.

```
# For setting up Virginia as your region
cat <<END > ~/.aws/config
[default]
region=us-east-1
END

# For setting up Ireland as your region
cat <<END > ~/.aws/config
[default]
region=eu-west-1
END

# For setting up Oregon as your region
cat <<END > ~/.aws/config
[default]
region=us-west-2
END

# For setting up Singapore as your region
cat <<END > ~/.aws/config
[default]
region=ap-southeast-1
END
```

## 5 - Clone this GitHub repo

Let's get the auxiliary code into our Cloud9 enviroment. We will download this project that contains a folder called base, this folder contains all the code you will use in your examples, so you don't need to type it.

For cloning the project, in your terminal

```
git clone https://github.com/mavi888/workshop-aws-getting-started-amplify.git
```

This command will download the project into a folder called "workshop-aws-getting-started-amplify", and inside there you can find a folder called base.

To make things easy to copy-paste the code, let's move the "base" folder to the root directory.

```
cp -r workshop-aws-getting-started-amplify/base/ base/
```

Now you should have a base folder in the root of your workshop directory, and inside you should see many files.

## 6- Making cloud9 environment bigger

The allocated storage for your Cloud9 environment is quite small for the size of all the dependencies that we are going to install.

We will run a simple script to give more storage capability to our workspace.

```
cd workshop-aws-getting-started-amplify/
cd utils
sh resize.sh 20
cd ..
```

### Next move to getting started

[Go to Getting started](getting-started.md)

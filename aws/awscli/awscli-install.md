Here are the general steps to set up AWS CLI:

1) Install Python first.

 AWS CLI requires Python 2 version 2.6.5+ or Python 3 version 3.3+. 

You can check the installed Python version by running the command:
 
    python --version

2) Install pip next (If not already installed). 

To check if pip is already installed you can run the command:

    which pip



If pip is not installed, download and install it using the instructions provided on the [official website](https://pip.pypa.io/en/stable/installation/).

**Note:** If you have both Python 2 and Python 3 installed on your system, you may need to use the command "python3" instead of "python"

3) Now you can install AWS CLI.

Run the following command to install AWS CLI: 

    pip install awscli

4) Now you have to configure your AWS CLI. 

To do so you will need your your AWS Access Key and Secret Access Key. 

Run the following command to start the configuration process:

    aws configure

You will be prompted to enter your AWS Access Key ID, Secret Access Key, default region name, and output format.

5) To verify that the installation has been successful you can run:

    aws --version


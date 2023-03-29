# <p align="center"> How to get iam policy documents from CLI </p>


### **You will need to first find:**

**- The policy arn**
**- The version id of the policy**

You can get your policy arn if you don't know it by listing the users.

Once you have the user arn you will need to use it to get the policy arn.

To do this you can run the command

    aws iam list-attached-user-policies --user-name <user_name>

This will list all the policies attached to the username you input.
This list will include the policy names that are attached aswell as the policy arn.

<img width="956" alt="image" src="https://user-images.githubusercontent.com/124072294/228667427-be49f55e-14b2-4168-9411-17ec720bc360.png">

Now that you have the policy arn you need to get the version id of the policy.

To do this you can run

    aws iam get-policy --policy-arn <policy_arn>

<img width="1118" alt="image" src="https://user-images.githubusercontent.com/124072294/228669068-00d7434f-494e-4432-94ac-957d7762d8e1.png">

Now that you have the version id aswell as the policy arn you can get the policy document by inputing this command.

    aws iam get-policy-version --policy-arn <policy_arn> --version-id <version_id>

<img width="1343" alt="image" src="https://user-images.githubusercontent.com/124072294/228669584-52a5788f-64c6-485d-a6f5-035898a69210.png">


This will output the policy document for the policy you specefied. 

You can output this to a .json file by addding
    
        > output.json

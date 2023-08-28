


## Useful Guides
- [Chapter 1. AWS Pinpoint Segment Data Recovery Guide](#AWS-pinpoint-segment-data-recovery-guide)


# AWS Pinpoint Segment Data Recovery Guide
- **Introduction :** Accidentally deleting a segment in AWS Pinpoint can be a frustrating experience,
but there is a way to recover the lost data. This guide outlines the steps to retrieve a deleted
segment effectively.

- **Method :**
 **1. Comment Out the Deleted Segment :**
 - Open the AWS CDK (Cloud Development Kit) code where the deleted segment was defined.
 - Locate the section of code responsible for defining the segment. In this example, we will refer to a segment named **"marketing"** defined in the **citypt-email-operations-stack.ts** file.
![Image of commented code](https://github.com/prasadm00/test1/blob/master/images/1_commentedImage.png)


 **2. Deploy the Code:**
 - Use the following command to deploy your CDK code:
   `cdk deploy`
 - Wait for the deployment to complete successfully.

 **3. Uncomment the Deleted Segment:**
 - Once the deployment is successful, go back to your CDK code.
 - Uncomment the code for the "marketing" segment or the segment you deleted earlier.
![Image of uncommented code](https://github.com/prasadm00/test1/blob/master/images/2_uncommentedImageimage%20(1).png)
 
**4. Deploy the Code Again:**
- Deploy your CDK code one more time to recover the deleted segment
   `cdk deploy`
- This will update your AWS Pinpoint configuration with the recovered segment.

**Understanding AWS Pinpoint Segments:**
- It's important to note that when you create a segment in AWS Pinpoint, it doesn't actually create any new records. Instead, it queries the existing endpoints and creates a virtual segment based on matching criteria.
For example, if you create a **marketing** segment, Pinpoint scans all endpoints and assembles a collection of endpoints that match the criteria specified for the marketing segment.



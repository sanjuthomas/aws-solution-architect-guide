#### IAM - Identity and Access Management

0. No cost / free service
1. A global service and globally resilience (read about availability zone(s), region(s), and global service(s). Another example of global service is s3)
2. There are three kinds of entities in IAM 
  2.1 User - humans or applications
  2.2 Group - a collection of related users. eg: could be, developer group and qa group
  2.3 Role - used to give access to AWS services or external account. Role is used when the 'thing' that login requires access to uncertain number of resource (tough to understand)
3. Policies - a template written in JSON
4. Identify Federation / Google, Facebook, LDAP, SAML, and so on. (Simple Assertion Markup Language)
5. MFA - multi factor authentication
6. Root user and other users 
7. IAM access key


Demo - user creation, group creation, assign group to user, login using new user

8. Command line and API access using access key (long term credential) - access keys are for a user and one user can have maximum two access keys
9. Access Key has two parts 1. access key id (public) 2. secret access key (private)
10. AWS CLI -  aws configure (us-east-1)


---------------------------------------- Basics Done ---------------------------------------

### Policy

collection of statements 

"Statement" : [

  {
    "Sid": "id of the statement",
    "Effect" : "Allow/Deny",
    "Action" : ["s3:*"],
    "Resource" : ["*"]
  }
  
]


By default everything is denied

ARS - Amazon Resource Name 

Resource examples - arn:aws:s3:{resourceName}, arn:aws:s3:{resourceName}/*

A policy can be applied to both user and group

Inline policy vs Managed Policies 

### User

Human - Principal use user name and password or access key to login 
once the user name and password is accepted, the user would become authenticated identity
We can have only 5000 (5K) in an account
A user can be a member of maximum 10 groups

### Group

A collection of users. No principal or credential - there is non concept of a group logging into the system


### Role

A user, application, or aws product/service like Lambda can assume a role temporarily. 
Support staff wanted an elevated access to do something during crisis. (Break Glass)
>5000 user scenario 
Corporate Directory based authentication. 
Federated/LDAP/Active Directory
Web Identity Federation/OpenAuth/Facebook/LinkedIn/Twitter and so on
Multi Account Access Scenario (Your account -> partner account)

You can attach two kinds of policies to a Role

1. Trust Policy 2. Permission Policy 

Trust Policy states who can assume a given role

sts:AssumeRole


### Organization

For large organization. It would help the corporations organize their AWS accounts as per the organization chart. 

Say for example, every business unit would get her own account.

There is concept of mater account for an organization.
Standard account joins the organization, after that its called member account.

You pick a regular/standard account, login using root account, and create an organization. There after, that account is called master account. 
Then you could invite other account join the organization. The root user of the other account can accept/decline your invite. 

AWS Organization helps with consolidate billing, and better user permission management. 
User would be allowed to switch from one account to another using switch account feature. (Role Switching User Interface)

Organization would have one master account and zero or many member account(s), and zero of many organization unit(s)

Billing - as soon as the member account is added, her billing is removed and master account would take charge her billing.

User Management - In general, users are removed from member accounts. All users would login via master account or a dedicated user management account. 
After the user land in the master or dedicated account, she can use the role switch interface to land in another account. 
That also means, the user would assume a role as long as she is in that account. 
#### IAM - Identity and Access Management

0. No cost / free service
1. A global service and globally resilience (read about availability zone(s), region(s), and global service(s). Another example of global serice is s3)
2. There are three kinds of entities in IAM 
  2.1 User - humans or applications
  2.2 Group - a collection of related users. eg: could be, developer group and qa group
  2.3 Role - used to give access to AWS services or external account. Role is used when the 'thing' that login requires access to uncertian number of resource (tough to understand)
3. Policies - a template writen in JSON
4. Identify Federation / Google, Facebook, LDAP, SAML, and so on. (Simple Assertion Markup Language)
5. MFA - multi factor authentication
6. Root user and other users 
7. IAM access key


Demo - user creation, group creation, assign group to user, login using new user

8. Command line and API access using access key (long term credential) - access keys are for a user and one user can have maximum two access keys
9. Access Key has two parts 1. access key id (public) 2. secret access key (private)
10. AWS CLI -  aws configure (us-east-1)


----------------------------------------Basics done-----------------------------------


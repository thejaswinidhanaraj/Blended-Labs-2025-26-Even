# Blended-Labs
## PROCEDURE:
### Task 1: Explore the Users and Groups
1. Log in to the AWS Management Console.
2. In the search box to the right of Services, type IAM and select it.
3. In the left navigation pane, choose Users.
The following IAM users are available:
user-1
user-2
user-3
4. Select user-1.
5. In the Permissions tab, observe that no permissions are assigned.
6. Click the Groups tab and confirm that user-1 is not a member of any group.
7. Click the Security credentials tab and verify that a console password is assigned.
8. In the left navigation pane, click User groups.
The following groups are available:
EC2-Admin
EC2-Support
S3-Support
9. Select EC2-Support group.
10. Open the Permissions tab.
Observe that the group has a Managed Policy attached:
AmazonEC2ReadOnlyAccess
11. Click the expand (+) option to view policy details.
  This policy allows:
  List and Describe EC2 resources
  View Load Balancers
  View CloudWatch
  View Auto Scaling
  IAM Policy Structure consists of:
  Effect (Allow or Deny)
  Action (API operations)
  Resource (Specific resource or *)
12. Close the policy details.
13. Go back to User groups.
14. Select S3-Support group.
15. Open the Permissions tab.
Observe that the Managed Policy attached is:
AmazonS3ReadOnlyAccess
16. Expand the policy to view details.
  This policy allows:
    List S3 buckets
    View S3 objects
17. Close the policy details.
18. Go back to User groups.
19. Select EC2-Admin group.
20. Open the Permissions tab.
    Observe that this group has an Inline Policy attached.
21. Expand the policy to view details.
 This policy allows:
  Describe EC2 instances
  Start EC2 instances
  Stop EC2 instances
22. Close the policy details.
#### Business Scenario:
| User   | Group       | Permissions                        |
| ------ | ----------- | ---------------------------------- |
| user-1 | S3-Support  | Read-only access to Amazon S3      |
| user-2 | EC2-Support | Read-only access to Amazon EC2     |
| user-3 | EC2-Admin   | View, Start and Stop EC2 instances |

### Task 2: Add Users to Groups
Add user-1 to S3-Support
23. Go to User groups.
24. Select S3-Support.
25. Click the Users tab.
26. Click Add users.
27. Select user-1 and click Add users.
    user-1 is now added to S3-Support group.

Add user-2 to EC2-Support
28. Select EC2-Support group.
29. Click Add users.
30. Select user-2 and click Add users.
    user-2 is now added to EC2-Support group.

Add user-3 to EC2-Admin    
31. Select EC2-Admin group.
32. Click Add users.
33. Select user-3 and click Add users.
    user-3 is now added to EC2-Admin group.
34. Verify that each group shows 1 user in the Users column.

### Task 3: Sign-In and Test Users

35. In IAM, select Dashboard.
36. Copy the IAM Sign-in URL.
37. Open a Private/Incognito browser window.
38. Paste the Sign-in URL into the address bar.

Test user-1 (S3 Support)
39. Login using:
    IAM user name: user-1
    Password: Lab-Password1
40. Open S3 service.
41. Verify that buckets can be viewed.
42. Open EC2 service.
Observation:
User is not authorized to access EC2.
Sign out user-1.

Test user-2 (EC2 Support)
43. Login using:
    IAM user name: user-2
    Password: Lab-Password2
44. Open EC2 → Instances.
45. Select instance named LabHost.
46. Attempt to Stop the instance.
Observation:
User receives "Not authorized" error.
47. Open S3 service.
Observation:
User does not have permission to list buckets.
Sign out user-2.

Test user-3 (EC2 Admin)
48. Login using:
    IAM user name: user-3
    Password: Lab-Password3
49. Open EC2 → Instances.
50. Select instance LabHost.
51. Click Stop instance.
52. Confirm Stop.
Observation:
Instance successfully enters stopping state.
53. Close the private browser window.

### Output:

### Result:
Thus, IAM Users and Groups were successfully explored in AWS. Role-based access control was implemented by assigning users to appropriate groups, and permissions were verified by testing access to Amazon S3 and Amazon EC2 services.

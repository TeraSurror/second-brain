### Users and Groups
- Root account is created by default. Should not be used or shared
- **Users** : people within you org. can be groups
- **Group** : Collection of users. Cannot contain groups. Multiple groups can have same user

### Permissions
- Users and Groups are assigned a JSON doc called **policies**
- Policies define the permissions of users/groups

A user is given permissions based on the **least privilege principle**. 
**It means, give only those permissions that are needed for the user and nothing more.**

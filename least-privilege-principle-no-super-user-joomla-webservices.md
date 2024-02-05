# Least Privilege Principle : Joomla Web Services Without Super-User
Super User is not mandatory anymore. 

We could instead follow this procedure to give the least permissions possible: 

1. Create custom Joomla Usergroup called **Web Service**. 
2. Add a specific user to it, let's say for example **api-read-only-001** 
3. Configure user token plugin and add **Web Services** Usergroup.
4. Configure **Web Services** Usergroup with **Api Login** permission. 
5. And for additional permissions, to mimic a RBAC (Role Based Access Control) system with Joomla, you can provide each additional permissions associated with a single group added to each user for whom we want to add this permission.(This was extensively shown in Randy CAREY talk at JWC 16 Joomla World Conference 2016 which is still relevant today https://www.youtube.com/watch?v=7Hy69ltVqzM)

In our example it would be user **api-read-only** in **Web Services** usergroup and Registered usergroup to be able to see it's token in their user profile. 
As at the moment there is no way to do it programmaticaly with for example POST /api/v2/auth/token API auth endpoint or CLI Console command user:auth:token to ask for example for a time-bound fined-grained token.

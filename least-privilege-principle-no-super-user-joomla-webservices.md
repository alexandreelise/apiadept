# Least Privilege Principle : Joomla Web Services Without SuperUser
SuperUser is not mandatory since 2020. According to this pull request from George Wilson [Pull request 29649](https://github.com/joomla/joomla-cms/pull/29649)

We could instead follow this procedure to give the least permissions possible: 

1. Create custom Joomla Usergroup called **Web Service**. 
2. Add a specific user to it, let's say for example **api-read-only-001** 
3. Configure user token plugin and add **Web Service** Usergroup.
4. Configure **Web Service** Usergroup with **Api Login** permission. 
5. And for additional permissions, to mimic a RBAC (Role Based Access Control) system with Joomla, you can provide each additional permissions associated with a single group added to each user for whom we want to add this permission.(This was extensively shown in Randy CAREY talk at JWC 16 Joomla World Conference 2016 which is still relevant today https://www.youtube.com/watch?v=7Hy69ltVqzM)
 
In our example it would be user **api-read-only** in **Web Service** Usergroup and **Registered** Usergroup to be able to login in Frontend and get it's **Joomla Api Token** in their user profile.

As at the moment, as far as I know, there is no way to do it programmaticaly with for example **POST /api/v2/auth/token** API auth route or CLI Console command **user:auth:token** to ask for example for a time-bound fined-grained token.


## VIDEO

> Video on **Api Adept** channel with **Mr Alexandre J-S William ELISÉ** presenting **Joomla! Api WITHOUT Super User : Least Privilege Principle**

[![Video on Api Adept channel with Mr Alexandre J-S William ELISÉ presenting Joomla! Api WITHOUT Super User : Least Privilege Principle](https://img.youtube.com/vi/STw0a7sOtEU/maxresdefault.jpg)](https://www.youtube.com/watch?v=STw0a7sOtEU)

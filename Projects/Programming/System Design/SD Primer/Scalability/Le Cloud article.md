Link: https://web.archive.org/web/20221030091841/http://www.lecloud.net/tagged/scalability/chrono

### Clones
Link: https://web.archive.org/web/20220530193911/https://www.lecloud.net/post/7295452622/scalability-for-dummies-part-1-clones
Every server should contain exactly the same codebase and does not store any user-related data, like sessions or profile pictures, on local disc or memory.

Sessions need to be stored in a centralized data store which is accessible to all your application servers. Can be external database or external persistence cache.

Tools can be used to make sure that code deployed to multiple servers remains the same.


### Database
Link: https://web.archive.org/web/20220602114024/https://www.lecloud.net/post/7994751381/scalability-for-dummies-part-2-database

Scaling databases can take 2 routes:
1. Use a SQL database. Do master-slave replication. Upgrade your master server by adding more resources to it.
2. Denormalize right from the start and include no more joins in any database query.
	1. We can use MySQL and use it as a NoSQL database or use a easy to scale NoSQL database.
	2. Joins are now done in the application code.


### Cache
A cache is a simple key-value store and it should reside as a buffering layer between your application and your data storage.

Patterns to caching data:
1. Cached Database queries:
	1. Whenever you do a query to the database, store the result dataset in the cache
	2. Hashed version of the query is the cache key
	3. Issue: when one piece of data changes, you need to delete all the cached queries who may include that table cell.
2. Cached Objects:
	1.  Let your class assemble a dataset from your database and then store the complete instance of the class or the assembed dataset in the cache. 
	2. You have, for example, a class called “Product” which has a property called “data”. It is an array containing prices, texts, pictures, and customer reviews of your product. The property “data” is filled by several methods in the class doing several database requests which are hard to cache, since many things relate to each other. 
	3. Now, do the following: when your class has finished the “assembling” of the data array, directly store the data array, or better yet the complete instance of the class, in the cache! 
	4. This allows you to easily get rid of the object whenever something did change and makes the overall operation of your code faster and more logical.

Some objects that can be cached:
1. user sessions
2. fully rendered blog articles
3. activity streams
4. user <-> friend relationships


### Asynchronism
ways to do async:
1. Do the time-consuming work in advance and serve the finished work with a low request time. The is used to turn dynamic content into static content. Page of a website, maybe built with a massive framework or CMS, are pre-rendered and locally stored as static HTML files on every change.
2. If a time-consuming task needs to be done and cannot be pre-computed, we can put that task in a queue. The job will then happen on the background.
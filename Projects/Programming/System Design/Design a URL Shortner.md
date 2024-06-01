Requirements:
- Highly available, scalable and fault tolerant
- 100 million URLs are generated per day
- URL has to be a combination of numbers (0-9) and characters (a-z and A-Z)
- No deleting or updating shortened URL

Back of envelope estimations:
- Write operations per day = 100 million
- Write operations per second = 100,000,000 / (24 * 3600) = approx 1160 write/sec
- Read operations:
	- Assume read to write ratio is 10 : 1
	- So, read ops = 1160 * 10 => 11600 read/sec
- Assume, URL must be kept for 10 years.
	- So, 100,000,000 * 365 * 10 = 365 billion records to store
- Assume URL size = 100 bytes
- Memory needed => 365 billion * 100 bytes => 36.5 Terabytes

High Level Design:
- We will make a REST API
- Service will consist of 2 endpoints:
	- /shorten -> POST request which takes the long URL as parameter and returns a short url
	- /redirect -> GET request which takes the short URL and redirects to the long URL
- In the /redirect request, we can either use 301 or 302 redirect. 
	- If we choose 301, the server caches the response and subsequent requests will directly redirect
	- If we choose 302, the server will not cache and all requests go through the tiny url service.
- The URL shortening will be done by a hash function
	- generated URL will be: https://tinyurl/<hashed_value_of_long_URL>
	- We need to create a hash function that does the above.

Deep Dive
- Data is stored in a relational data
	- each row will contain <id, shorturl, longurl>
	- we will not use a hash table as we need a lot of memory
- URL shortnenting:
	- Our hash can contain letters and numbers -> 10 + 26 + 26 -> 62 characters
	- To find length of hash value, we find n such that 62^n >= 365 billion (62 characters and we need to store 365 billion records). So, n is 7 in this case.
	- We can use two ways to create hash:
		- Hash + collision
		- Base 62 conversion
	- Check for details in the textbook.
	- We choose base 62 as it is easy
- URL redirect:
	- We use multiple servers for our service and have a load balancer front it. 
	- We store the values in a cache to reduce database calls.
	- Look for the diagram in the book
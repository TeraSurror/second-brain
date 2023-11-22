#### Overview
- CDN Network
- Uses caches on edge locations to reduce latency
- Origin: Think of it as servers where the requests would go if CDN does not have content
- 2 types of origin:
	- S3
	- Custom: Could be any http/https resource

#### Geo-restriction
-  Can restrict access to certain countries by editing allowlist and blocklist
- Allowlist: countries allowed to access cloud front.
- Blocklist: countries blocked from accessing cloud front.

#### Pricing
3 pricing models:
1. Price class All: every edge location is available
2. Price class 200: most locations, but not the most expensive ones
3. Price class 100: the least expensive 100 edge locations

#### Cache invalidation
We can partially or fully reset the cloudfront cache if we update our backend origin


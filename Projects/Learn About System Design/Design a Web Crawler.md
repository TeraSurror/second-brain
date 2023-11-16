Requirements:
1. 1 billion web pages are downloaded every month
2. HTML pages only
3. Used for search engine indexing
4. store for upto 5 years

Back of the envelope estimations:
1. Assume 1 billion web pages are downloaded every month.• QPS: 1,000,000,000 / 30 days / 24 hours / 3600 seconds = ~400 pages per second.
2. Peak QPS = 2 * QPS = 800
3. Assume the average web page size is 500k.
4. 1-billion-page x 500k = 500 TB storage per month. If you are unclear about digital
storage units, go through “Power of 2” section in Chapter 2 again.
5. Assuming data are stored for five years, 500 TB * 12 months * 5 years = 30 PB. A 30 PB
storage is needed to store five-year content.

High level design:
![[web_crawler.png]]


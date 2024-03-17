Following is the list of datatypes PostgreSQL supports
1. Boolean -> bool -> true and false values
2. Character -> `char, varchar, text`
	- CHAR(n): fixed character string. If values with lesser length are inserted, space is padded at the end.
	- VARCHAR(n): variable character string. We can store upto n chars.
	- TEXT: variable length. Theoretically it can have infinite length
1. Numeric types
	- Integers
		- SMALLINT: 2-byte signed
		- INT: 4-byte signed
		- Serial: same as INT, but PostgreSQL automatically generates these values.
	- Floating-points numbers
		- float(n): n <= precision <= 8 bytes
		- real or float8: 4-byte floating number
		- numeric or numeric(p, s): real number with p digits with s number after the decimal point
1. Temporal types -> `date, time, timestamp, interval`
	- DATE: stores date
	- TIME: stores time of the day
	- TIMESTAMP: stores date and time values
	- TIMESTAMPZ: timezone aware timestamp
	- INTERVAL: periods of time
1. UUID -> Universally Unique Identifiers
2. Array
3. JSON
4. hstore -> stores key-value pair
5. Special types like network address and geometric data
	- box: rectangular box
	- line: a set of points
	- point: a geometric pair of numbers
	- lseg: a line segment
	- polygon: a closed geometric
	- inet: IP4 address
	- macaddr: a MAC address


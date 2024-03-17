There are two ways to protect a user:

1. Password Policy:
	1. We can set password policies like minimum length, character types and so on
2. MFA:
	1. MFA = password *you know* + a device *you own*
	2. Device Options in AWS:
		1. Virtual MFA
			1. Google Authenticator
			2. Authy
		2. Universal 2nd Factor (U2F) Key: Support for multiple root and IAM users using a single security key (provided by YubiKey)
		3. Hardware key Fob MFA Device
		4. Hardware Key Fob MFA Device for AWS GovCloud (US)
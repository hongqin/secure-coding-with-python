# Secure Coding with Python.

## Chapter 2: SQL Injection
### Testing part 2
We could keep adding more cases to our fuzzer, or use external tools, like [sqlmap](http://sqlmap.org/), which are going to be limited by the test cases we can pass to them, we could also use a Static Application Security Testing, like [bandit](https://github.com/PyCQA/bandit/).

```text
(venv) > $ bandit marketplace/**/*.py
Test results:
>> Issue: [B608:hardcoded_sql_expressions] Possible SQL injection vector through string-based query construction.
   Severity: Medium   Confidence: Low
   Location: marketplace/listings.py:27
   More Info: https://bandit.readthedocs.io/en/latest/plugins/b608_hardcoded_sql_expressions.html
26	
27	        sql = "INSERT INTO listings (title, description) VALUES (E'%s', E'%s')" % (
28	            title.replace("'", "\\'"), description.replace("'", "\\'")
29	        )

--------------------------------------------------

Code scanned:
	Total lines of code: 28
	Total lines skipped (#nosec): 0

Run metrics:
	Total issues (by severity):
		Undefined: 0.0
		Low: 0.0
		Medium: 1.0
		High: 0.0
	Total issues (by confidence):
		Undefined: 0.0
		Low: 1.0
		Medium: 0.0
		High: 0.0
Files skipped (0):
```
As we can see, the tool doesn't like our sanitization strategies and flags our code as a possible source of SQL injection.

## Description
Welcome to the Secure coding with python course. In this repository you will find a series of branches for each step of the development of a sample marketplace application. In such a development, we will be making security mistakes and introducing vulnerabilities, we will add tests for them and finally fixing them.

The branches will have the following naming scheme for easier navigation: {Chapter number}-{Chapter Name}/{code|test|fix}. I encourage you to follow the chapters in order, but you can also skip to the specific one you wish to review. 

For this course we will be using Python3, Flask and PostgreSQL.

**Proceed to [next section](https://github.com/nxvl/secure-coding-with-python/tree/2.2-sql-injection/fix)**

## Index
### 1. Vulnerable Components
* [1-vulnerable-components/code](https://github.com/nxvl/secure-coding-with-python/tree/1-vulnerable-components/code) 
* [1-vulnerable-components/test](https://github.com/nxvl/secure-coding-with-python/tree/1-vulnerable-components/test)
* [1-vulnerable-components/fix](https://github.com/nxvl/secure-coding-with-python/tree/1-vulnerable-components/fix)

### 2. SQL Injection
* [2.1-sql-injection/code](https://github.com/nxvl/secure-coding-with-python/tree/2.1-sql-injection/code) 
* [2.1-sql-injection/test](https://github.com/nxvl/secure-coding-with-python/tree/2.1-sql-injection/test)
* [2.1-sql-injection/fix](https://github.com/nxvl/secure-coding-with-python/tree/2.1-sql-injection/fix)
* [2.2-sql-injection/test](https://github.com/nxvl/secure-coding-with-python/tree/2.2-sql-injection/test)
* [2.2-sql-injection/fix](https://github.com/nxvl/secure-coding-with-python/tree/2.2-sql-injection/fix)
* [2.3-sql-injection/fix](https://github.com/nxvl/secure-coding-with-python/tree/2.3-sql-injection/fix)

### 3. Weak password storage
* [3.1-weak-password-storage/code](https://github.com/nxvl/secure-coding-with-python/tree/3.1-weak-password-storage/code) 
* [3.1-weak-password-storage/fix](https://github.com/nxvl/secure-coding-with-python/tree/3.1-weak-password-storage/fix)
* [3.2-weak-password-storage/test](https://github.com/nxvl/secure-coding-with-python/tree/3.2-weak-password-storage/test)
* [3.2-weak-password-storage/fix](https://github.com/nxvl/secure-coding-with-python/tree/3.2-weak-password-storage/fix)

### 4. Weak account secrets
* [4-weak-account-secrets/code](https://github.com/nxvl/secure-coding-with-python/tree/4-weak-account-secrets/code) 
* [4-weak-account-secrets/fix](https://github.com/nxvl/secure-coding-with-python/tree/4-weak-account-secrets/fix)

### 5. Broken Authentication
* [5.1-broken-authentication/code](https://github.com/nxvl/secure-coding-with-python/tree/5.1-broken-authentication/code) 
* [5.1-broken-authentication/fix](https://github.com/nxvl/secure-coding-with-python/tree/5.1-broken-authentication/fix)
* [5.2-broken-authentication/fix](https://github.com/nxvl/secure-coding-with-python/tree/5.2-broken-authentication/fix)

### 6. Broken Deauthentication
* [6.1-broken-deauthentication/code](https://github.com/nxvl/secure-coding-with-python/tree/6.1-broken-deauthentication/code) 
* [6.1-broken-deauthentication/test](https://github.com/nxvl/secure-coding-with-python/tree/6.1-broken-deauthentication/test)
* [6.1-broken-deauthentication/fix](https://github.com/nxvl/secure-coding-with-python/tree/6.1-broken-deauthentication/fix)
* [6.2-broken-deauthentication/code](https://github.com/nxvl/secure-coding-with-python/tree/6.2-broken-deauthentication/code) 
* [6.2-broken-deauthentication/test](https://github.com/nxvl/secure-coding-with-python/tree/6.2-broken-deauthentication/test)
* [6.2-broken-deauthentication/fix](https://github.com/nxvl/secure-coding-with-python/tree/6.2-broken-deauthentication/fix)
* [6.3-broken-deauthentication/code](https://github.com/nxvl/secure-coding-with-python/tree/6.3-broken-deauthentication/code) 
* [6.3-broken-deauthentication/test](https://github.com/nxvl/secure-coding-with-python/tree/6.3-broken-deauthentication/test)
* [6.3-broken-deauthentication/fix](https://github.com/nxvl/secure-coding-with-python/tree/6.3-broken-deauthentication/fix)

### 7. Cross-Site Scripting (xss)
* [7-xss/code](https://github.com/nxvl/secure-coding-with-python/tree/7-xss/code) 
* [7-xss/test](https://github.com/nxvl/secure-coding-with-python/tree/7-xss/test)
* [7-xss/fix](https://github.com/nxvl/secure-coding-with-python/tree/7-xss/fix)

### 8. Broken Access Control
* [8-broken-access-control/code](https://github.com/nxvl/secure-coding-with-python/tree/8-broken-access-control/code) 
* [8-broken-access-control/test](https://github.com/nxvl/secure-coding-with-python/tree/8-broken-access-control/test)
* [8-broken-access-control/fix](https://github.com/nxvl/secure-coding-with-python/tree/8-broken-access-control/fix)

### 9. XML External Entities (XXE)
* [9-xxe/code](https://github.com/nxvl/secure-coding-with-python/tree/9-xxe/code) 
* [9-xxe/test](https://github.com/nxvl/secure-coding-with-python/tree/9-xxe/test)
* [9-xxe/fix](https://github.com/nxvl/secure-coding-with-python/tree/9-xxe/fix)

### 10. Sensitive Data Exposure
* [10-sensitive-data-exposure/code](https://github.com/nxvl/secure-coding-with-python/tree/10-sensitive-data-exposure/code) 
* [10-sensitive-data-exposure/test](https://github.com/nxvl/secure-coding-with-python/tree/10-sensitive-data-exposure/test)
* [10-sensitive-data-exposure/fix](https://github.com/nxvl/secure-coding-with-python/tree/10-sensitive-data-exposure/fix)

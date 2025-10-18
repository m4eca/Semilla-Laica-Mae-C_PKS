## Definition

**SQL Injection (SQLi)** is a vulnerability where an attacker inserts malicious SQL into an application's database queries via user input. It can expose, change, or delete data and may lead to bigger compromises.

---

## How It Works

1. The app accepts input (form, URL param, API, etc.).  
2. The input is directly combined into an SQL query without proper checks.  
3. An attacker crafts input containing SQL syntax to change the query logic.  
4. The database runs the altered query and returns results or performs actions the developer didn't intend.

**Example (unsafe PHP + MySQL):**
```php
$user = $_GET['user'];
$query = "SELECT * FROM users WHERE username = '$user'";
$result = mysqli_query($conn, $query);
If user = ' OR '1'='1, the query becomes:
```
If user = ' OR '1'='1, the query becomes:
```sql
SELECT * FROM users WHERE username = '' OR '1'='1'
```
which returns all rows.

## Types of SQL Injection
- **In-band (Classic)**
Error-based: uses DB error messages to learn about the database.
Union-based: uses UNION to combine attacker-controlled results with real query results.

- **Blind SQL Injection**
Boolean-based: infers data by true/false responses.
Time-based: uses delays (e.g., SLEEP()) to infer data from response times.

- **Out-of-band**
Uses separate channels (DNS, HTTP callbacks) to retrieve data when direct responses aren’t available.



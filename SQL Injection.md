## **Definition**  
SQL Injection is a code injection technique that allows an attacker to interfere with the queries an application makes to its database. It occurs when untrusted input is inserted directly into a SQL query without proper validation or escaping.

## **Impact**  
- Allows attackers to **read, modify, or delete** sensitive data  
- Can lead to **authentication bypass**, data leakage, or full database compromise  
- May enable **remote code execution** or access to the underlying operating system in severe cases

## **Risk Factors**  
- Concatenating **user input directly into SQL queries**  
- Lack of **input validation or escaping**  
- Use of outdated or insecure database drivers  
- Applications with **elevated database privileges**

## **Prevention Strategies**  
- **Use parameterized queries** or prepared statements  
- **Validate and sanitize input**: enforce strict data types and formats  
- **Limit database privileges**: follow the principle of least privilege  
- **Employ ORM frameworks** that abstract query construction  
- **Monitor and log** suspicious query patterns for early detection

--- 

## Reflection

I learned that mixing user input directly with SQL queries can lead to serious problems. Attackers can use it to access or change data in the database without permission. Using prepared statements and checking input properly helps keep the system safe. It also reminded me that even basic forms like login or search need to be handled carefully to avoid these kinds of issues.

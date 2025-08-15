# SQL Developer Internship - Task: Stored Procedures and Functions

## Objective
Learn to create reusable SQL logic in MySQL using **Stored Procedures** and **Stored Functions**.  
This helps in modularizing SQL operations, handling NULLs, and making the code reusable.

## Database Used
**Database:** `library_management_system`  
**Tables Used:** `Books`, `Readers`  
Sample data was already inserted for testing the procedures and functions.

## Tasks Completed

 Stored Procedure: CountBooksInCategory
 
Purpose: Count the number of books in a given category.  
- **IN parameter:** `categoryName`  
- **OUT parameter:** `totalBooks`  
- **Safety:** Returns 0 if category does not exist.  

**Usage Example:**
```sql
CALL CountBooksInCategory('Programming', @count);
SELECT @count AS Programming_Book_Count;
CALL CountBooksInCategory('Education', @count);
SELECT @count AS Education_Book_Count;
CALL CountBooksInCategory('fiction', @count);
SELECT @count AS fiction_Book_Count;

Stored Function: CalculateLateFee
Purpose: Calculate late fee for overdue books at Rs. 2.50 per day.
Input: daysLate
Output: Fee amount
SELECT CalculateLateFee(5) AS LateFee;
SELECT CalculateLateFee(0) AS LateFee;
SELECT CalculateLateFee(10) AS LateFee;

Stored Function: GetReaderFullName
Purpose: Get full name of a reader using reader_id.
Returns 'Reader Not Found' if reader does not exist.
SELECT GetReaderFullName(3) AS ReaderName;

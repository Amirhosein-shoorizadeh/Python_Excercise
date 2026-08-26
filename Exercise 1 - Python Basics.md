# تمرین‌های Python — دوره کامل

---

## بخش ۱ — مقدمات: اعداد، رشته‌ها، متغیرها

این بخش مفاهیم اولیه‌ای مثل انواع داده، عملیات روی اعداد و رشته‌ها را تمرین می‌کند.

**تمرین ۱ — محاسبات عددی**
```python
# 1. Calculate the area of a circle with radius 7
# 2. Convert temperature: 100Fahrenheit → Celsius
#    Formula: C = (F - 32) * 5/9
# 3. Compute compound interest:
#    principal = 1000, rate = 0.05, years = 10
#    Formula: A = P * (1 + r) ** n
# 4. Find the hypotenuse of a right triangle
#    with legs a=3, b=4 (use **0.5 for square root)

# Print each result formatted to 2 decimal places
# Expected: area = 153.94, temp = 37.78, ...
```

**تمرین ۲ — رشته‌ها و فرمت‌بندی**
```python
full_name = "python programming language"

# 1. Capitalize each word → "Python Programming Language"
# 2. Count how many times the letter 'p' appears (case-insensitive)
# 3. Replace 'language' with 'course'
# 4. Reverse the entire string
# 5. Check if it's a palindrome

sentence = "A man a plan a canal Panama"
# 6. Remove all spaces and check if palindrome (case-insensitive)

# Print each result with a descriptive label using f-strings
```

**تمرین ۳ — Indexing و Slicing**
```python
data = "2024-07-13:ERROR:Database connection failed at line 42"

# Using only slicing and string methods (no split() for parts1-3):
# 1. Extract the date: "2024-07-13"
# 2. Extract the log level: "ERROR"
# 3. Extract the message after the second colon
# 4. Now use split(':') — how does it compare?
# 5. Extract just the number42 and convert it to int
```

---

## بخش ۲ — ساختارهای داده: لیست، دیکشنری، تاپل، مجموعه

این بخش رویساختارهای داده اصلی پایتون تمرکز دارد.

**تمرین ۴ — لیست و عملیات روی آن**
```python
temperatures = [22, 35, 18, 40, 28, 15, 33, 27, 19, 38, 25, 30]

# Without using built-in max/min/sum functions:
# 1. Find the maximum and minimum manually
# 2. Calculate the average
# 3. Count how many days were above average
# 4. Separate into two lists: hot (>= 30) and cool (< 30)
# 5. Sort the list using bubble sort (implement it yourself)
# 6. Find the median (middle value of sorted list)
```

**تمرین ۵ — دیکشنری**

دیکشنری‌ها برای نگهداری داده‌های key-value کاربرد فراوانی دارند. در تمرین‌های بعدی با JSON آشنا می‌شوی که در واقع همان دیکشنری‌های پایتون هستند.

```python
employees = {
    "E001": {"name": "Ali Ahmadi","dept": "IT",      "salary": 5000, "years": 3},
    "E002": {"name": "Sara Hoseini", "dept": "Finance",  "salary": 6200, "years": 7},
    "E003": {"name": "Reza Karimi",  "dept": "IT",       "salary": 4800, "years": 2},
    "E004": {"name": "Mina Tehrani", "dept": "HR",       "salary": 5500, "years": 5},
    "E005": {"name": "Kamran Jali",  "dept": "Finance",  "salary": 7000, "years": 9},
}

# 1. Find the employee with the highest salary
# 2. Group employees by department: {"IT": [...], "Finance": [...], "HR": [...]}
# 3. Calculate average salary per department
# 4. Give a10% raise to employees with more than 5 years of experience
# 5. Create a new dict: {employee_id: name} for all employees
# 6. Find departments that have more than one employee
```

**تمرین ۶ — تاپل و مجموعه**
```python
transactions = [
    ("T001", "Ali","purchase", 250),
    ("T002", "Sara",  "refund",   100),
    ("T003", "Ali",   "purchase", 350),
    ("T004", "Reza",  "purchase", 180),
    ("T005", "Sara",  "purchase", 420),
    ("T006", "Ali",   "refund",    50),
]

# Tuples are immutable — good for records you shouldn't accidentally modify
# 1. Unpack each tuple and print: "Ali made a purchase of $250"
# 2. Find all unique customers using a set
# 3. Find total spent by each customer (purchases - refunds)
# 4. Find customers who made both purchases AND refunds (set intersection logic)
# 5. Why would using tuples here be safer than lists?
#    (Write your answer as a comment)
```

---

## بخش ۳ — File I/O، JSON و Excel

**مفهوم پارس کردن:**
پارس کردن (Parsing) یعنی خواندن داده‌ای با یک فرمت خاص و تبدیل آن به ساختاری که پایتون بتواند با آن کار کند. وقتی یک فایل JSON می‌خوانی، `json.load()` متن خام را پارس می‌کند و به دیکشنری/لیست پایتون تبدیل می‌کند.

**تمرین ۷ — File I/O پایه**
```python
# Step 1: Create a file called "log.txt" with this content (write it with Python):
log_entries = """2024-01-15 09:00:01 INFOUser'ali' logged in
2024-01-15 09:05:23 ERROR Database connection timeout
2024-01-15 09:06:01 INFO  Connection restored
2024-01-15 09:10:44 WARNING Memory usage at 85%
2024-01-15 09:15:02 ERROR Null pointer in module auth.py line 42
2024-01-15 09:20:00 INFO  Backup completed successfully
"""

# Step 2: Read the file back and:
# 1. Count lines for each level: INFO, WARNING, ERROR
# 2. Extract only ERROR lines and save to "errors.txt"
# 3. Print a summary: {"INFO": 3, "WARNING": 1, "ERROR": 2}

# Use'with open(...)' — always preferred over open() without context manager
```

**تمرین ۸ — پارس JSON**

JSON (JavaScript Object Notation) یک فرمت استاندارد برای تبادل داده است. ساختار آن عیناً شبیه دیکشنری‌های پایتون است.ماژول `json` پایتون این تبدیل را انجام می‌دهد.

```python
# Step 1: Create "users.json" with this content (save it manually or write with Python)
# [
#   {"id": 1, "name": "Ali Ahmadi","age": 28, "email": "ali@test.com","active": true,"score": 85},
#   {"id": 2, "name": "Sara Hoseini",  "age": 17, "email": "sara@test.com", "active": true,  "score": 92},
#   {"id": 3, "name": "Reza Karimi",   "age": 35, "email": "bad-email","active": false, "score": 70},
#   {"id": 4, "name": "Mina Tehrani",  "age": 29, "email": "mina@test.com", "active": true,  "score": null},
#   {"id": 5, "name": "Kamran Jalili", "age": 22, "email": "kam@test.com",  "active": true,  "score": 88}
# ]

import json

# Step 2: Read and parse the file
with open("users.json", "r") as f:
    users = json.load(f)# json.load() parses the file → gives us a Python list

# Now'users' is a regular Python list of dicts — work with it like any dict:
# 1. Print name and score of each user
# 2. Filter: keep only active=True, age>=18, score is not null
# 3. Validate email: must contain '@' and '.'
# 4. Save valid users to "valid_users.json"
# 5. Save rejected users with a reason:
#    [{"id": 2, "name": "Sara", "reason": "underage"}, ...]
#    Save to "rejected_users.json"

# Step 3: Save results
with open("valid_users.json", "w") as f:
    json.dump(valid_users, f, indent=2, ensure_ascii=False)# indent=2 → pretty-print with indentation
    # ensure_ascii=False → allows Persian/non-ASCII characters
```

**تمرین ۹ — JSON تودرتو (Nested JSON)**

داده‌های واقعی معمولاً تودرتو هستند. مثلاً یک سفارش شامل اطلاعات مشتری و یک لیست از محصولات است. پارس این نوع داده مهارت کلیدی است.

```python
# Create "orders.json":
# [
#   {
#     "order_id": "A001",
#     "customer": {"name": "Ali", "city": "Tehran"},
#     "items": [
#       {"product": "Laptop","qty": 1, "price": 5000},
#       {"product": "Mouse",    "qty": 2, "price": 200}
#     ],
#     "status": "delivered"
#   },
#   {
#     "order_id": "A002",
#     "customer": {"name": "Sara", "city": "Mashhad"},
#     "items": [
#       {"product": "Keyboard", "qty": 1, "price": 500}
#     ],
#     "status": "pending"
#   },
#   {
#     "order_id": "A003",
#     "customer": {"name": "Reza", "city": "Tehran"},
#     "items": [
#       {"product": "Monitor",  "qty": 2, "price": 3000},
#       {"product": "Mouse",    "qty": 1, "price": 200}
#     ],
#     "status": "delivered"
#   }
# ]

import json

with open("orders.json", "r") as f:
    orders = json.load(f)

# Notice: orders is a list of dicts, and each dict has nested dicts/lists
# To access Ali's city:orders[0]["customer"]["city"]
# To access first item:   orders[0]["items"][0]["product"]

# Tasks:
# 1. Calculate total price of each order (sum of qty * price for all items)
# 2. Filter only "delivered" orders
# 3. Find customers from "Tehran"
# 4. Find the most ordered product (by total quantity across all orders)
# 5. Build and save "summary.json":
#    {
#      "total_orders": 3,
#      "delivered_count": 2,
#      "top_product": "Mouse",
#      "orders": [{"order_id": "A001", "customer": "Ali", "total": 5400}, ...]
#    }
```

**تمرین ۱۰ — خواندن فایل Excel با openpyxl**

اکسل یکی از رایج‌ترین فرمت‌های داده در محیط کار است. کتابخانه `openpyxl` به ما اجازه می‌دهد فایل‌های `.xlsx` را بخوانیم و بنویسیم.

```python
# First install: pip install openpyxl

# Create "students.xlsx" manually in Excel with these columns:
# | Name| Age | Math | Science | English | City|
# | Ali    |  17 |   85 |      90 |      78 | Tehran  |
# | Sara   |  18 |   92 |      88 |      95 | Isfahan |
# | Reza   |  16 |   70 |      65 |      80 | Tehran  |
# | Mina   |  19 |   95 |      98 |     100 | Mashhad |
# | Kamran |  17 |   60 |      55 |      70 | Tehran  |

import openpyxl

# Opening the workbook
wb = openpyxl.load_workbook("students.xlsx")
ws = wb.active   # get the active (first) sheet

# Reading rows:
# ws[1] → first row (the header)
# ws.iter_rows(min_row=2) → all rows starting from row 2 (skipping header)
# Each cell has a .value property

# Step 1: Read all rows into a list of dicts
#         Use the first row as keys (headers)
headers = [cell.value for cell in ws[1]]
students = []
for row in ws.iter_rows(min_row=2, values_only=True):
    student = dict(zip(headers, row))
    students.append(student)

# Step 2: Calculate average score for each student (Math + Science + English) / 3
# Step 3: Find the best student per city
# Step 4: Save results to "results.json"

# Step 5: Write results back to a new sheet in the same Excel file
ws2 = wb.create_sheet(title="Results")
ws2.append(["Name", "City", "Average"])# header row
for s in students:
    avg = round((s["Math"] + s["Science"] + s["English"]) / 3, 1)
    ws2.append([s["Name"], s["City"], avg])

wb.save("students.xlsx")
print("New sheet'Results' added to students.xlsx")
```

---

## بخش ۴ — ساختارهای کنترلی: شرط‌ها، حلقه‌ها، Comprehensions

**تمرین ۱۱ — شرط‌ها و حلقه‌ها روی داده JSON**
```python
# Load users.json from Exercise 8
import json

with open("users.json", "r") as f:
    users = json.load(f)

# 1. For each user, print their grade:
#    score >= 90 → "A", >= 80 → "B", >= 70 → "C", < 70 → "D", null → "N/A"

# 2. While loop: keep asking the user to enter a city name
#    print all users from that city (add city field to users.json first)
#    type "exit" to stop

# 3. List comprehension — rewrite each of these as a one-liner:
active_users = []
for u in users:
    if u["active"]:
        active_users.append(u["name"])

high_scores = []
for u in users:
    if u["score"] and u["score"] > 85:
        high_scores.append(u["score"])

# 4. Dict comprehension: {name: score} for all users with non-null scores
# 5. Nested comprehension: flatten this list of lists into one list
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

**تمرین ۱۲ — پردازش Excel با حلقه و شرط**
```python
# Load students.xlsx using the method from Exercise 10
# 1. Print only students with average >= 80 (using if inside for loop)
# 2. Create a grade dictionary:
#    {"Ali": "B", "Sara": "A", ...}
# 3. Count students per grade using a dict (without Counter yet)
# 4. Find students below average using list comprehension
# 5. Sort students by average using sorted() with a lambda key
students_sorted = sorted(students, key=lambda s: (s["Math"] + s["Science"] + s["English"]) / 3, reverse=True)
```

---

## بخش ۵ — توابع: def، args/kwargs، Lambda

**تمرین ۱۳ — توابع برای پارس JSON**

طراحی خوب توابع یعنی هر تابع یک کار مشخص انجام دهد. این توابع را می‌توانی در همه پروژه‌های بعدی استفاده کنی.

```python
import json
import csv

def load_json(filepath):
    """
    Load and parse a JSON file.
    Returns the parsed data, or None if file not found or invalid JSON.
    """
    pass

def save_json(data, filepath, indent=2):
    """
    Save data as a formatted JSON file.
    ensure_ascii=False to support non-English characters.
    """
    pass

def load_csv(filepath):
    """
    Load a CSV file using csv.DictReader.
    Returns a list of dicts (one per row).
    """
    pass

def filter_records(records, field, value):
    """
    Return records where records[field] == value.
    Example: filter_records(users, "active", True)
    """
    pass

def get_field_values(records, field):
    """
    Return a list of all values for the given field.
    Skip records where field is missing or None.
    Example: get_field_values(users, "score") → [85, 70, 88]
    """
    pass

def summarize(records, numeric_field):
    """
    Return a dict with basic stats for a numeric field:
    {"count": n, "min": x, "max": y, "average": z}
    """
    pass

# Test all functions with users.json and products.csv
```

**تمرین ۱۴ — *args، **kwargs و Lambda**
```python
# Part A: *args and **kwargs
def generate_report(*records, **options):
    """
    records : any number of dicts
    options:- title(str): report title
      - fields  (list) : which fields to display
      - sort_by (str)  : field name to sort by
      - limit   (int)  : max number of records to show
    
    Example usage:
      generate_report(*users,title="Top Users",
                      fields=["name", "score"],
                      sort_by="score",
                      limit=3)
    """
    pass

# Part B: Lambda, map, filter
import json

with open("users.json") as f:
    users = json.load(f)

# 1. Use map() to add a 'grade' key to each user (A/B/C/D based on score)
# 2. Use filter() to keep only active users with non-null scores
# 3. Use sorted() with lambda to sort by score descending
# 4. Chain them: filter → sort → add grade → save to "graded_users.json"

# Part C: Scope question
x = 10

def outer():
    x = 20
    def inner():
        x = 30
        print("inner x:", x)   # what prints here?
    inner()
    print("outer x:", x)       # what prints here?

outer()
print("global x:", x)          # what prints here?
# Predict the output, then run it. Were you right?
```

---

## Milestone Project 1 — بازی حدس عدد

یک بازی حدس عدد با رابط کاربری کنسول بنویس که:
- عدد تصادفی بین۱ تا ۱۰۰ انتخاب کند
- سه سطح دشواری داشته باشد (آسان: ۱۰ شانس، متوسط: ۷، سخت: ۵)
- راهنمایی بدهد (بالاتر/پایین‌تر)
- بازی‌های قبلی را در یک فایل `highscores.json` ذخیره کند
- در پایان بهترین امتیازها را نمایش دهد

```python
import random
import json
from datetime import datetime

# Required functions (implement each one):

def get_difficulty():
    """Ask user for difficulty level, return number of allowed guesses."""
    pass

def get_guess(low, high):
    """
    Keep asking until user enters a valid integer between low and high.
    Handle ValueError if user types a non-integer.
    """
    pass

def check_guess(guess, secret):
    """Return'correct', 'too_high', or 'too_low'."""
    pass

def calculate_score(guesses_used, max_guesses):
    """
    Score formula: (max_guesses - guesses_used + 1) * 100Minimum score is 0.
    """
    pass

def load_highscores(filepath="highscores.json"):
    """Load existing highscores, return empty list if file not found."""
    pass

def save_highscore(name, score, difficulty, filepath="highscores.json"):
    """Append new score entry and save. Entry format:
    {"name": "Ali", "score": 700, "difficulty": "hard", "date": "2024-01-15"}
    """
    pass

def show_highscores(filepath="highscores.json"):
    """Print top 5 scores sorted by score descending."""
    pass

def play_game():
    """Main game loop — ties everything together."""
    pass

if __name__ == "__main__":
    play_game()
```

---

## بخش ۶ — OOP

**تمرین ۱۵ — کلاس DataFile**

حالا توابع تمرین۱۳ را در قالب یک کلاس منسجم پیاده‌سازی می‌کنیم. مزیت OOP این است که داده (`self.data`) و رفتار (متدها) کنار هم هستند.

```python
import json
import csv

class DataFile:
    """
    Base class for reading, filtering, and saving data files.
    Subclasses will handle specific formats (JSON, CSV, Excel).
    """

    def __init__(self, filepath):
        self.filepath = filepath
        self.data = []# will hold list of dicts after loading

    def load(self):
        """Must be implemented by subclasses."""
        raise NotImplementedError("Subclass must implement load()")

    def save(self, output_path, data=None):
        """Must be implemented by subclasses."""
        raise NotImplementedError("Subclass must implement save()")

    def filter(self, field, value):
        """Return records where record[field] == value. Does NOT modify self.data."""
        return [r for r in self.data if r.get(field) == value]

    def get_values(self, field):
        """Return list of values for a given field (skip None/missing)."""
        return [r[field] for r in self.data if r.get(field) is not None]

    def summary(self):
        """Print record count and available fields."""
        if not self.data:
            print("No data loaded.")
            return
        print(f"File: {self.filepath}")
        print(f"Records: {len(self.data)}")
        print(f"Fields : {list(self.data[0].keys())}")

    def __len__(self):
        return len(self.data)

    def __repr__(self):
        return f"{self.__class__.__name__}('{self.filepath}', {len(self.data)} records)"


class JSONFile(DataFile):
    """Handles reading and writing JSON files."""

    def load(self):
        with open(self.filepath, "r", encoding="utf-8") as f:
            self.data = json.load(f)
        print(f"Loaded {len(self.data)} records from {self.filepath}")

    def save(self, output_path, data=None):
        to_save = data if data is not None else self.data
        with open(output_path, "w", encoding="utf-8") as f:
            json.dump(to_save, f, indent=2, ensure_ascii=False)
        print(f"Saved {len(to_save)} records to {output_path}")


class CSVFile(DataFile):
    """Handles reading and writing CSV files."""

    def load(self):
        # csv.DictReader uses the first row as field names automatically
        with open(self.filepath, "r", encoding="utf-8") as f:
            reader = csv.DictReader(f)
            self.data = [dict(row) for row in reader]
        print(f"Loaded {len(self.data)} records from {self.filepath}")

    def save(self, output_path, data=None):
        to_save = data if data is not None else self.data
        if not to_save:
            return
        with open(output_path, "w", newline="", encoding="utf-8") as f:
            writer = csv.DictWriter(f, fieldnames=to_save[0].keys())
            writer.writeheader()
            writer.writerows(to_save)


class ExcelFile(DataFile):
    """Handles reading and writing Excel (.xlsx) files using openpyxl."""

    def load(self):
        import openpyxl
        wb = openpyxl.load_workbook(self.filepath)
        ws = wb.active
        headers = [cell.value for cell in ws[1]]
        self.data = []
        for row in ws.iter_rows(min_row=2, values_only=True):
            self.data.append(dict(zip(headers, row)))
        print(f"Loaded {len(self.data)} records from {self.filepath}")

    def save(self, output_path, data=None):
        # Implement: write self.data (or given data) to a new xlsx file
        pass


# Test all three classes:
jf = JSONFile
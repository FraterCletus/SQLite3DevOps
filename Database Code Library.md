# Order of Operations
## Day 1
The Day begins with 4 person team. The following procedures are completed and provisioned:
- [ ] Temp Email creation using [InstAddr - Instant Email Address](https://m.kuku.lu/en.php)
- [ ] Provision Temp Discord Account using temp email
- [ ] Communications Check
- [ ] Polices Write up
	- [ ] Open Door Policy
	- [ ] No Retaliation for Reporting
	- [ ] Feedback Loops
	- [ ] Data Retention
	- [ ] Internet Traffic Monitoring
	- [ ] Ticketing Escalations Policy
	- [ ] Fair Employment Practices
- [ ] **Management Specific Objectives and Policies**
	- [ ] **Objectives**
		- [ ] Completion of all data to build entire database cluster; with exception to future operations dependent tables. 
			- [ ] **Supporting Policies**
				- [ ] Allocation of temporary group focus is necessary at all times to complete a task. Do not be afraid to assign people to a task to complete the Database Objective.
		- [ ]  Maintain Order of Operations
		- [ ] Maintain oversight of all objectives for all teams. Reporting is required **hourly.**
			- [ ] **Supporting Policies**
				- [ ] New policies are a tool for meeting all objectives.
				- [ ] All ticket holders must document to completion.
				- [ ] All situation report documents are completed using 5 paragraph order. (Situation, Mission, Execution, Admin/Logistics, Command/Signals)
- [ ] Onboarding Media
	- [ ] Discord Chat
		- [ ] Raise Tickets
		- [ ] Communications Specialist Duties
		- [ ] New Policies and Network Flow Updates
	- [ ] Policy Reinforcement
	- [ ] Designated Workstations
	- [ ] Stay Flexible and don't take anything personal
## **Order of Operations**
1. Multiple tickets (+/-4 tickets) can become projects.
	1. All tickets that appear to require more than 20 minutes take back seat priority
	2. Tickets assigned at random by management team.
	3. All ticket holders must document to completion.
2. Projects designation determines if a policy/investigation is required
3. A policy designation is required to determine if HR or IT, etc. holds the policy.
4. The fastest way to close out a ticket is log in the appropriate values for an appropriate table. This is what the knowledge database is for.

#### Phase 0 — Bootstrapping (System Identity)

* [ ] Fill in your own personnel record (root owner)
* [ ] Define department structure
* [ ] Define policy framework (ownership + escalation rules)
* [ ] Define ticket categories (intake taxonomy)

#### Phase 1 — Core Knowledge + Communication Layer

* [ ] Knowledge base setup
* [ ] Event documentation structure
* [ ] Ticketing / comms system live
* [ ] Policy escalation paths defined

#### Phase 2 — Operational Layer (Controlled Teams)

* [ ] Personnel expansion (additional users onboarded)
* [ ] Asset management system enabled
* [ ] Project management system enabled
* [ ] Team-based ticket assignment active
* [ ] Script execution boundaries defined (who can run/modify what)

#### Phase 3 — System Expansion (Higher Risk Domains)

* [ ] Accounting module
* [ ] Inventory module
* [ ] Vendor / supplier handling
* [ ] External dependency tracking

#### Phase 4 — Executive Control (You Only)

* [ ] Global policy override authority
* [ ] Emergency escalation control
* [ ] System audit review
* [ ] Final approval gate for structural changes

### Data Inspection Workflow
```
## Document Name:
### Data Inspection Checklist

1. **Schema Validation**
- [ ]  Check that all expected columns are present (e.g., column names, data types).
- [ ]  Ensure consistent delimiters (e.g., commas, tabs) across all records.

2. **Row Count**
- [ ]  Verify total number of rows and compare against expected volume.
- [ ]  Check for unexpected empty rows or outliers.

3. **Null and Missing Values**
- [ ]  Identify missing or null values in each column.
- [ ]  Determine if they are acceptable or need imputation.

4. **Data Range Check**
- [ ]  Validate numeric columns against expected ranges (e.g., no negative values where not expected).
- [ ]  Check date fields for correct formats and ranges.

5. **Duplicate Detection**
- [ ]  Check for duplicate rows or unexpected repeating records.
- [ ]  Identify primary keys or unique identifiers and ensure uniqueness.

6. **Character Encoding**
- [ ]  Confirm all text fields are using the expected encoding (e.g., UTF-8).
- [ ]  Check for special characters or invisible control codes.

7. **Outlier Identification**
- [ ]  Scan for unusually high or low values in each column.
- [ ]  Check for unexpected patterns or anomalies that could indicate errors.

8. **Cross-Column Consistency**
- [ ]  Verify logical relationships (e.g., if column A is always greater than column B).
- [ ]  Check for mutually exclusive or dependent fields.

9. **Sample Preview**
- [ ]  Select a random sample of rows and manually review them for structural integrity.
- [ ]  Confirm that the sample data aligns with expected patterns.

10. **Document Findings**
- [ ]  Record any issues, anomalies, or columns flagged for deeper review.
- [ ]  Update a log or checklist so it’s traceable for later stages.

```
## 1. Data Ingestion Loops and Notation Documentation
```python

company = {
    "staff_table_csv": ["personnel", "staff_table", "StaffID","FirstName","LastName","Email","DepartmentID","DateOfBirth","Gender","MaritalStatus","Phone","HireDate","SeparationDate"],
    "department_csv": ["personnel", "department", "DepartmentID", "DepartmentName", "ManagerID"],
    "staff_address_csv": ["personnel", "staff_address", "AddressID", "StaffID", "StreetAddress", "City", "State", "PostalCode", "Country"],
    "emergency_contact_csv": ["personnel", "emergency_contact", "ContactID", "StaffID", "ContactName", "Relationship ", "Phone", "Email"],
    "job_history_csv": ["personnel", "job_history", "HistoryID", "StaffID", "Title", "Department ", "StartDate", "EndDate"],
    "salary_csv": ["personnel", "salary", "SalaryID", "StaffID", "Amount", "Currency", "EffectiveDate"],
    "training_csv": ["personnel", "training", "TrainingID", "StaffID", "TrainingName", "Certification", "CompletionDate"],
    "rating_csv": ["personnel", "rating", "ReviewID", "StaffID", "ReviewDate", "Rating", "Comments"],
    "asset_attributes_csv": ["asset_management", "asset_attributes", "AssetID", "Type", "Model", "OS", "SerialNumber", "Status"],
    "software_csv": ["asset_management", "software", "SoftwareID", "Name", "LicenseKey", "ExpirationDate", "Usage"],
    "software_assigned_csv": ["asset_management", "software_assigned", "AssignmentID", "AssetID", "SoftwareID", "AssignmentDate"],
    "scripts_csv": ["asset_management", "scripts", "ScriptID", "ScriptName", "Description", "Path", "LastUpdated"],
    "config_doc_csv": ["asset_management", "config_doc", "ConfigID", "Title", "Description", "Path", "LastUpdated"],
    "security_note_csv": ["asset_management", "security_note", "SecurityID", "AssetID", "Note", "Date"],
    "product_csv": ["inventory", "product", "ProductID", "Name", "Description", "Category", "Quantity", "UnitPrice", "LastUpdated"],
    "supplier_csv": ["inventory", "supplier", "SupplierID", "Name", "ContactName", "Phone", "Email", "Address"],
    "orders_csv": ["inventory", "orders", "OrderID", "ProductID", "SupplierID", "Quantity" "OrderDate", "Status"],
    "customer_csv": ["inventory", "customer", "CustomerID", "Name", "ContactName", "Phone", "Email", "Address"],
    "sale_csv": ["inventory", "sale", "SaleID", "ProductID", "CustomerID", "Quantity", "SaleDate", "TotalAmount"],
    "budget_csv": ["accounting", "budget", "BudgetID ", "Year ", "Department ", "Amount ", "LastUpdated"],
    "expense_csv": ["accounting", "expense", "ExpenseID ", "Date ", "Category ", "Description ", "Amount ", "Payee ", "Method ", "Notes ", "LastUpdated"],
    "invoice_csv": ["accounting", "invoice", "InvoiceID ", "Date ", "Customer ", "Amount ", "DueDate ", "Status ", "Notes ", "LastUpdated"],
    "transaction_csv": ["accounting", "transaction", "TransactionID ", "Date ", "EmployeeID ", "Amount ", "Type", "Notes ", "LastUpdated"],
    "ticket_csv": ["crm", "ticket", "TicketID", "Subject", "Description", "Priority", "Status", "CategoryID", "AssigneeID", "CreatedDate", "UpdatedDate", "ClosedDate"],
    "customer_csv": ["crm", "customer", "CustomerID", "FirstName", "LastName", "Email", "DateOfBirth", "Gender", "StreetAddress", "City", "State", "PostalCode", "Country"],
    "category_csv": ["crm", "category", "CategoryID", "CategoryName", "ParentCategoryID"],
    "staff_csv": ["crm", "staff", "CategoryID", "CategoryName", "ParentCategoryID"],
    "ticket_history_csv": ["crm", "ticket_history", "StaffID", "FirstName", "LastName", "Email", "DepartmentID"],
    "tick_upload_csv": ["crm", "tick_upload", "AttachmentID", "TicketID", "FileName", "FilePath", "UploadedBy", "UploadDate"],
    "article_csv": ["knowledge", "article", "article_id", "title", "content", "author_id", "vote"],
    "authors_csv": ["knowledge", "authors", "author_id", "name", "email"],
    "categories_csv": ["knowledge", "categories", "category_id", "name"],
    "tags_csv": ["knowledge", "tags", "tag_id", "name"],
    "article_tags_csv": ["knowledge", "article_tags", "article_id", "tag_id"],
    "comments_csv": ["knowledge", "comments", "comment_id", "article_id", "content"],
    "attachment_csv": ["knowledge", "attachment", "attachment_id", "article_id", "file_path"],
    "project_csv": ["projects_management", "project", "project_id", "task_id", "name", "description", "status", "StaffID", "start_date", "due_date"],
    "project_resources_csv": ["projects_management", "project_resources"],
    "task_csv": ["projects_management", "task", "task_id", "project_id", "task_name", "description", "StaffID", "status", "start_date", "due_date"],
    "event_csv": ["event_management", "event", "event_id", "event_name", "description", "start_datetime", "end_datetime", "location", "organizer_id", "budget", "event_type", "target_audience", "registration_deadline", "website", "status"],
    "attendeees_csv": ["event_management", "attendeees" , "event_id", "attendee_id", "name", "email", "phone_number", "registration_date", "ticket_type", "company", "job_title", "check_in_status", "dietary_restrictions"],
    "logistics_csv": ["event_management", "logistics", "event_id", "resource_id", "name", "description", "type", "quantity", "cost", "supplier", "delivery_date", "setup_time", "breakdown_time", "location_within_venue", "contact_person"],
    "documentation_csv": ["event_management", "documentation", "social_media_engagement", "venue_relations", "regulations", "vendors", "speakers", "event_timeline", "event_layout", "marketing_materials", "sponsorships", "insurance", "emergency_plan", "staffing", "technical_requirements", "transportation", "accommodations", "post_event_report"],
    "procedure_csv": ["backup", "procedure", "procedure_id", "description"],
    "schedule_csv": ["backup", "schedule", "schedule_id", "procedure_id", "backup_type", "frequency"],
    "location_csv": ["backup", "location", "location_id", "location_name", "address"],
    "log_csv": ["backup", "log", "log_id", "schedule_id", "location_id", "timestamp", "status"],
    "policy_csv": ["policy", "policy", "PolicyID", "PolicyName", "TypeID", "Description", "CreationDate"],
    "policy_type_csv": ["policy", "policy_type", "TypeID", "TypeName", "Description", "tags"],
    "policy_owner_csv": ["policy", "policy_owner", "OwnerID", "PolicyID", "OwnerName", "DepartmentID"],
    "policy_document_csv": ["policy", "policy_document", "DocumentID", "PolicyID", "DocumentName", "DocumentType", "Location"],
    "policy_revision_csv": ["policy", "policy_revision", "RevisionID", "PolicyID", "RevisionDate", "VersionNumber", "ChangesMade"],
    "policy_compliance_csv": ["policy", "policy_compliance", "ComplianceID", "PolicyID", "ComplianceStatus", "AssessmentDate", "IssuesFound"],
    "policy_approval_csv": ["policy", "policy_approval", "ApprovalID", "PolicyID", "ApproverName", "ApprovalDate"],
    "policy_research_csv": ["policy", "policy_research", "RelatedDocID", "PolicyID", "RelatedDocName", "DocType", "Location"],
    "policy_training_csv": ["policy", "policy_training", "TrainingID", "PolicyID", "EmployeeName", "TrainingDate"],
    "policy_config_azure_csv": ["policy", "policy_training", "ConfigID", "ResourceName", "ResourceType", "ConfigurationType", "ConfigurationDetails", "CreatedBy", "CreatedDate", "LastModifiedBy", "LastModifiedDate", "Notes"]
}

### Use to build metadata catalogue of db cluster
#### The purpose of this entire setup to help the user/administrator correlate data relationships and consider how best to utilize the schema.
print("""#!/bin/bash""")
# Turn into a metadata catalog:
for key, value in company.items():
    cluster = value[0]
    table = value[1]
    print(f"mkdir -p {cluster}")
    print(f"""cat << EOF > {cluster}/{table}-meta.md""")
    tags = " ".join(f"#{c}" for c in value)
    print(tags)
    for connector in value:
	    print(f"[[{connector}]]")
    c_cnt = len(value[2:])
    print(f"Total Columns: [[{c_cnt}]]")
    if c_cnt > 4:
        print("""#awk_hawk""")
    print(f"EOF\n")


# Building Data Ingession Pipeline Scripts!
## Data Intake
for key, value in company.items():
    cluster = value[0]
    table = value[1]
    schema = value[2:]
    print(f"""cat << EOF > {cluster}/{table}/{table}.py
import csv
import os

# This script by Matthew Thomasson, created May 2026, was produced to lay the foundation of data aggregation
contents = {schema}
definitions = []

# Input definitions for each term in contents
for term in contents:

    define = input(f"Definition of '{{term}}': ")
    confirm = input(f"You entered: '{{define}}'. Confirm? (y/n): ").lower()
    if confirm == "y":
        definitions.append(define)
    else:
        print("[X] Please define the correct term, or if you are unsure, write ticket number.")
        define = input(f"Definition of '{{term}}': ")
        definitions.append(define)
        flsf = input("A bit of caution. Slow is smooth. Smooth is fast. Press any button to begin.") #Prevents confusion

df = dict(zip(contents, definitions))
print(f"\n\nPlease review the contents of your input.")
for key, value in df.items():
    print(f"{{key}}: {{value}}") # Troubleshooting Logic. If user needs to write a ticket, they can cut and paste the dictionary output, fix whatever and send with ticket.

## Confirmation of full entry.
print(f"=======================================================\n=============== VALIDATION STEP. LAST ENTRY!! =========\n=======================================================")
confirm = input("Is the information you are submitting correct? (y/n) ").lower()
print(f"=======================================================\n=======================================================")
if confirm != "y":
    print("Data Entry Rejected. Please refresh Page")
    exit()
    # Continue to rest of 
print("Thank you for your input. Please refresh your page.")


# Converts output from dictionary maker to new variable
python_dict = df 
csv_file_path = "{table}.csv"

# Check if the CSV file exists
file_exists = os.path.exists(csv_file_path)

# Open the CSV file in append mode or write mode based on existence
with open(csv_file_path, "a" if file_exists else "w", newline="") as csv_file:
    # Create a CSV writer
    csv_writer = csv.writer(csv_file)

    # If the file does not exist, add a header row
    if not file_exists:
        csv_writer.writerow(python_dict.keys())

    # Write the data
    csv_writer.writerow(python_dict.values())

print(f"CSV data has been {{'appended to' if file_exists else 'created at'}} {{csv_file_path}}")
########################################
EOF

echo "[X] {table}.py Created!
    """)

```
## 2. Parsing and Analytics
### AWKhawk.py
```python
## This program was written to break up longer tables into (x,y,z) axis for ad-hoc table cosntruction. The evolution of this pattern will be used to produce matplotlib graphics for data anlytics. Group lists of tables with same column number for faster processing.
start = 1
rg = 8 # Manually Declare the columns to consider.
a = []
b = []
c = []
d = []
e = []
f = []
g = []
while start < rg:
    a.append(start)
    start = start + 1 
b = a
c = a # Creating index of all capabilities
for x in a:
    delta = (f"print ${x}")
    d.append(delta)
    csvop = (f"_{x}.csv")
    g.append(csvop)
for x in a:
    for y in b:
        if x < y:
            echo = (f"print ${x},${y}")
            e.append(echo)
            csvop = (f"_{x}_{y}.csv")
            g.append(csvop)
for x in a:
    for y in b:
        for z in c:
            if x < y:
                if y < z:
                    fox = (f"print ${x},${y}, ${z}")
                    f.append(fox)
                    csvop = (f"_{x}_{y}_{z}.csv")
                    g.append(csvop)
d.extend(e)
d.extend(f)
e = ("""awk -F',' 'BEGIN{OFS=","} {""")
f = ("}' example_raw.csv > example")
for op in d:
        for idob in g:
            print(f"""{e}{op}{f}{idob}""")
```

## 3. SQLite3 Database Builders
While the `AWKhawk.py` script is built primarily for parsing on a vertical level, These SQLite3 Scripts, intended for DB Browser or similar software for further analytics. From the python scripts written from the beginning, these **completed** scripts generate the business infrastructure needed.
### Employee SQLite3 DB
```python
import sqlite3
import csv
# Create or connect to the SQLite3 database
conn = sqlite3.connect('employee_data.db')
cursor = conn.cursor()

cursor.execute('''CREATE TABLE IF NOT EXISTS department (
    DepartmentID TEXT PRIMARY KEY,
    DepartmentName TEXT,
    ManagerID TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS staff_table (
    StaffID TEXT PRIMARY KEY,
    FirstName TEXT,
    LastName TEXT,
    Email TEXT,
    DepartmentID TEXT,
    DateOfBirth TEXT,
    Gender TEXT,
    MaritalStatus TEXT,
    Phone TEXT,
    HireDate TEXT,
    SeparationDate TEXT,
    FOREIGN KEY (DepartmentID) REFERENCES department(DepartmentID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS staff_address (
    AddressID TEXT PRIMARY KEY,
    StaffID TEXT,
    StreetAddress TEXT,
    City TEXT,
    State TEXT,
    PostalCode TEXT,
    Country TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS emergency_contact (
    ContactID TEXT PRIMARY KEY,
    StaffID TEXT,
    ContactName TEXT,
    Relationship TEXT,
    Phone TEXT,
    Email TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS job_history (
    HistoryID TEXT PRIMARY KEY,
    StaffID TEXT,
    Title TEXT,
    DepartmentID TEXT,
    StartDate TEXT,
    EndDate TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID),
    FOREIGN KEY (DepartmentID) REFERENCES department(DepartmentID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS salary (
    SalaryID TEXT PRIMARY KEY,
    StaffID TEXT,
    Amount TEXT,
    Currency TEXT,
    EffectiveDate TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS training (
    TrainingID TEXT PRIMARY KEY,
    StaffID TEXT,
    TrainingName TEXT,
    Certification TEXT,
    CompletionDate TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS rating (
    ReviewID TEXT PRIMARY KEY,
    StaffID TEXT,
    ReviewDate TEXT,
    Rating TEXT,
    Comments TEXT,
    FOREIGN KEY (StaffID) REFERENCES staff_table(StaffID)
)''')



# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('staff.csv', 'staff')
load_csv_to_table('employee_address.csv', 'employee_address')
load_csv_to_table('emergencycontact.csv', 'emergency_contact')
load_csv_to_table('department.csv', 'department')
load_csv_to_table('job_history.csv', 'job_history')
load_csv_to_table('training.csv', 'training')
load_csv_to_table('rating.csv', 'rating')
load_csv_to_table('salary.csv', 'salary')

# Commit changes and close connection
conn.commit()
conn.close()

print("Database created and data inserted successfully.")
```
### Asset Management SQLite3 DB
```python
import sqlite3
import csv
conn = sqlite3.connect('asset_management.db')
cursor = conn.cursor()

cursor.execute('''CREATE TABLE IF NOT EXISTS asset_attributes (
    AssetID TEXT PRIMARY KEY,
    Type TEXT,
    Model TEXT,
    OS TEXT,
    SerialNumber TEXT,
    Status TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS software (
    SoftwareID TEXT PRIMARY KEY,
    Name TEXT,
    LicenseKey TEXT,
    ExpirationDate TEXT,
    Usage TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS software_assigned (
    AssignmentID TEXT PRIMARY KEY,
    AssetID TEXT,
    SoftwareID TEXT,
    AssignmentDate TEXT,
    FOREIGN KEY (AssetID) REFERENCES asset_attributes(AssetID),
    FOREIGN KEY (SoftwareID) REFERENCES software(SoftwareID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS scripts (
    ScriptID TEXT PRIMARY KEY,
    ScriptName TEXT,
    Description TEXT,
    Path TEXT,
    LastUpdated TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS config_doc (
    ConfigID TEXT PRIMARY KEY,
    Title TEXT,
    Description TEXT,
    Path TEXT,
    LastUpdated TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS security_note (
    SecurityID TEXT PRIMARY KEY,
    AssetID TEXT,
    Note TEXT,
    Date TEXT,
    FOREIGN KEY (AssetID) REFERENCES asset_attributes(AssetID)
)''')
# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('asset_attributes.csv', 'asset_attributes')
load_csv_to_table('software.csv', 'software')
load_csv_to_table('software_assigned.csv', 'software_assigned')
load_csv_to_table('scripts.csv', 'scripts')
load_csv_to_table('config_doc.csv', 'config_doc')
load_csv_to_table('security_note.csv', 'security_note')

print("Database created and data inserted successfully.")
```
### Inventory Management SQLite3 DB
```python
# Connect to the SQLite3 database
import sqlite3
import csv
conn = sqlite3.connect('inventory_data.db')
cursor = conn.cursor()

cursor.execute('''CREATE TABLE IF NOT EXISTS product (
    ProductID TEXT PRIMARY KEY,
    Name TEXT,
    Description TEXT,
    Category TEXT,
    Quantity INTEGER,
    UnitPrice REAL,
    LastUpdated DATE
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS supplier (
    SupplierID TEXT PRIMARY KEY,
    Name TEXT,
    ContactName TEXT,
    Phone TEXT,
    Email TEXT,
    Address TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS orders (
    OrderID TEXT PRIMARY KEY,
    ProductID TEXT,
    SupplierID TEXT,
    Quantity INTEGER,
    OrderDate DATE,
    Status TEXT,
    FOREIGN KEY (ProductID) REFERENCES product(ProductID),
    FOREIGN KEY (SupplierID) REFERENCES supplier(SupplierID)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS customer (
    CustomerID TEXT PRIMARY KEY,
    Name TEXT,
    ContactName TEXT,
    Phone TEXT,
    Email TEXT,
    Address TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS sale (
    SaleID TEXT PRIMARY KEY,
    ProductID TEXT,
    CustomerID TEXT,
    Quantity INTEGER,
    SaleDate DATE,
    TotalAmount REAL,
    FOREIGN KEY (ProductID) REFERENCES product(ProductID),
    FOREIGN KEY (CustomerID) REFERENCES customer(CustomerID)
)''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('product.csv', 'product')
load_csv_to_table('supplier.csv', 'supplier')
load_csv_to_table('order.csv', 'order')
load_csv_to_table('customer.csv', 'customer')
load_csv_to_table('sale.csv', 'sale')

# Commit changes and close connection
conn.commit()
conn.close()

print("Inventory management tables created successfully.")
```
### Accounting SQLite3 DB
```python
import sqlite3
import csv

# Connect to the SQLite3 database (or create if it doesn't exist)
conn = sqlite3.connect('financial.db')
cursor = conn.cursor()

# Create Budgets table
cursor.execute('''CREATE TABLE IF NOT EXISTS budgets (
                    BudgetID INTEGER PRIMARY KEY,
                    Year INTEGER,
                    Department TEXT,
                    Amount REAL,
                    LastUpdated TEXT
              )''')

# Create Expenses table
cursor.execute('''CREATE TABLE IF NOT EXISTS expenses (
                    ExpenseID INTEGER PRIMARY KEY,
                    Date TEXT,
                    Category TEXT,
                    Description TEXT,
                    Amount REAL,
                    Payee TEXT,
                    Method TEXT,
                    Notes TEXT,
                    LastUpdated TEXT
                )''')

# Create Invoices table
cursor.execute('''CREATE TABLE IF NOT EXISTS invoices (
                    InvoiceID INTEGER PRIMARY KEY,
                    Date TEXT,
                    Customer TEXT,
                    Amount REAL,
                    DueDate TEXT,
                    Status TEXT,
                    Notes TEXT,
                    LastUpdated TEXT
                )''')

# Create Payroll table
cursor.execute('''CREATE TABLE IF NOT EXISTS transactions (
                    TransactionID INTEGER PRIMARY KEY,
                    Date TEXT,
                    EmployeeID TEXT,
                    Amount REAL,
                    Type TEXT,
                    Notes TEXT,
                    LastUpdated TEXT
                )''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('budget.csv', 'budget')
load_csv_to_table('expense.csv', 'expense')
load_csv_to_table('invoice.csv', 'invoices')
load_csv_to_table('transaction.csv', 'transaction')

# Commit changes and close connection
conn.commit()
conn.close()
print("Database created and data inserted successfully.")
```
### Ticketing SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (creates if not exists)
conn = sqlite3.connect('helpdesk_tickets.db')
cursor = conn.cursor()

# Create Ticket table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Ticket (
    TicketID INTEGER PRIMARY KEY,
    Subject TEXT,
    Description TEXT,
    Priority TEXT,
    Status TEXT,
    CategoryID INTEGER,
    AssigneeID INTEGER,
    CreatedDate TEXT,
    UpdatedDate TEXT,
    ClosedDate TEXT
)
''')
# Create Customer Database
cursor.execute('''
CREATE TABLE IF NOT EXISTS Customer (
	CustomerID TEXT PRIMARY KEY,
	FirstName TEXT,
	LastName TEXT,
	Email TEXT,
	DateOfBirth TEXT,
	Gender TEXT,
	StreetAddress TEXT,
	City TEXT,
	State TEXT,
	PostalCode TEXT,
	Country TEXT,
)
''')
# Create Category table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Category (
    CategoryID INTEGER PRIMARY KEY,
    CategoryName TEXT,
    ParentCategoryID INTEGER
    Email TEXT,
    DepartmentID TEXT
)
''')

# Create Staff table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Staff (
    StaffID INTEGER PRIMARY KEY,
    FirstName TEXT,
    LastName TEXT,
    Email TEXT,
    DepartmentID INTEGER
)
''')

# Create Department table
cursor.execute('''
CREATE TABLE IF NOT EXISTS Department (
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT
)
''')

# Create TicketHistory table
cursor.execute('''
CREATE TABLE IF NOT EXISTS TicketHistory (
    HistoryID INTEGER PRIMARY KEY,
    TicketID INTEGER,
    Action TEXT,
    StaffID INTEGER,
    Note TEXT,
    HistoryDate TEXT
)
''')

# Create TicketAttachment table
cursor.execute('''
CREATE TABLE IF NOT EXISTS TicketAttachment (
    AttachmentID INTEGER PRIMARY KEY,
    TicketID TEXT,
    FileName TEXT,
    FilePath TEXT,
    UploadedBy TEXT,
    UploadDate TEXT
)
''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('ticket.csv', 'ticket')
load_csv_to_table('customer.csv', 'customer')
load_csv_to_table('category.csv', 'category')
load_csv_to_table('staff.csv', 'staff')
load_csv_to_table('dept.csv', 'dept')
load_csv_to_table('ticket_history.csv', 'ticket_history')
load_csv_to_table('tick_upload.csv', 'tick_upload')
# Commit changes and close connection
conn.commit()
conn.close()

print("Database and tables created successfully!")
```
### Knowledge SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (if not exists, a new database will be created)
conn = sqlite3.connect('knowledge_base.db')
cursor = conn.cursor()

# Create the Articles table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Articles (
        article_id TEXT PRIMARY KEY,
        title TEXT NOT NULL,
        content TEXT NOT NULL,
        author_id INTEGER,
        vote TEXT,
        FOREIGN KEY (author_id) REFERENCES Authors(author_id)
    )
''')

# Create the Authors table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Authors (
        author_id INTEGER PRIMARY KEY,
        name TEXT NOT NULL,
        email TEXT
    )
''')

# Create the Categories table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Categories (
        category_id INTEGER PRIMARY KEY,
        name TEXT
    )
''')

# Create the Tags table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Tags (
        tag_id INTEGER PRIMARY KEY,
        name TEXT NOT NULL
    )
''')

# Create the Article_Tags table (for many-to-many relationship)
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Article_Tags (
        article_id INTEGER,
        tag_id INTEGER,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id),
        FOREIGN KEY (tag_id) REFERENCES Tags(tag_id),
        PRIMARY KEY (article_id, tag_id)
    )
''')

# Create the Comments table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Comments (
        comment_id INTEGER PRIMARY KEY AUTOINCREMENT,
        article_id INTEGER,
        content TEXT NOT NULL,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id)
    )
''')

# Create the Attachments table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Attachments (
        attachment_id INTEGER PRIMARY KEY,
        article_id TEXT,
        file_path TEXT,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id)
    )
''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('article.csv', 'article')
load_csv_to_table('authors.csv', 'authors')
load_csv_to_table('categories.csv', 'categories')
load_csv_to_table('tags.csv', 'tags')
load_csv_to_table('article_tags.csv', 'article_tags')
load_csv_to_table('comments.csv', 'comments')
load_csv_to_table('attachment.csv', 'attachment')



# Commit the changes and close the connection
conn.commit()
conn.close()

print("Database created successfully.")
```
### Projects SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (if not exists, a new database will be created)
conn = sqlite3.connect('knowledge_base.db')
cursor = conn.cursor()

# Create the Articles table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Articles (
        article_id TEXT PRIMARY KEY,
        title TEXT NOT NULL,
        content TEXT NOT NULL,
        author_id INTEGER,
        vote TEXT,
        FOREIGN KEY (author_id) REFERENCES Authors(author_id)
    )
''')

# Create the Authors table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Authors (
        author_id INTEGER PRIMARY KEY,
        name TEXT NOT NULL,
        email TEXT
    )
''')

# Create the Categories table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Categories (
        category_id INTEGER PRIMARY KEY,
        name TEXT
    )
''')

# Create the Tags table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Tags (
        tag_id INTEGER PRIMARY KEY,
        name TEXT NOT NULL
    )
''')

# Create the Article_Tags table (for many-to-many relationship)
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Article_Tags (
        article_id INTEGER,
        tag_id INTEGER,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id),
        FOREIGN KEY (tag_id) REFERENCES Tags(tag_id),
        PRIMARY KEY (article_id, tag_id)
    )
''')

# Create the Comments table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Comments (
        comment_id INTEGER PRIMARY KEY AUTOINCREMENT,
        article_id INTEGER,
        content TEXT NOT NULL,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id)
    )
''')

# Create the Attachments table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Attachments (
        attachment_id INTEGER PRIMARY KEY,
        article_id TEXT,
        file_path TEXT,
        FOREIGN KEY (article_id) REFERENCES Articles(article_id)
    )
''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('article.csv', 'article')
load_csv_to_table('authors.csv', 'authors')
load_csv_to_table('categories.csv', 'categories')
load_csv_to_table('tags.csv', 'tags')
load_csv_to_table('article_tags.csv', 'article_tags')
load_csv_to_table('comments.csv', 'comments')
load_csv_to_table('attachment.csv', 'attachment')



# Commit the changes and close the connection
conn.commit()
conn.close()

print("Database created successfully.")
```
### Event Management SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (if not exists, a new database will be created)
conn = sqlite3.connect('event_management.db')
cursor = conn.cursor()

cursor.execute('''CREATE TABLE IF NOT EXISTS event (
    event_id TEXT PRIMARY KEY,
    event_name TEXT,
    description TEXT,
    start_datetime TEXT,
    end_datetime TEXT,
    location TEXT,
    organizer_id TEXT,
    budget TEXT,
    event_type TEXT,
    target_audience TEXT,
    registration_deadline TEXT,
    website TEXT,
    status TEXT
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS attendees (
    attendee_id TEXT PRIMARY KEY,
    event_id TEXT,
    name TEXT,
    email TEXT,
    phone_number TEXT,
    registration_date TEXT,
    ticket_type TEXT,
    company TEXT,
    job_title TEXT,
    check_in_status TEXT,
    dietary_restrictions TEXT,
    FOREIGN KEY (event_id) REFERENCES event(event_id)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS logistics (
    resource_id TEXT PRIMARY KEY,
    event_id TEXT,
    name TEXT,
    description TEXT,
    type TEXT,
    quantity TEXT,
    cost TEXT,
    supplier TEXT,
    delivery_date TEXT,
    setup_time TEXT,
    breakdown_time TEXT,
    location_within_venue TEXT,
    contact_person TEXT,
    FOREIGN KEY (event_id) REFERENCES event(event_id)
)''')

cursor.execute('''CREATE TABLE IF NOT EXISTS documentation (
    doc_id TEXT PRIMARY KEY,
    event_id TEXT,
    social_media_engagement TEXT,
    venue_relations TEXT,
    regulations TEXT,
    vendors TEXT,
    speakers TEXT,
    event_timeline TEXT,
    event_layout TEXT,
    marketing_materials TEXT,
    sponsorships TEXT,
    insurance TEXT,
    emergency_plan TEXT,
    staffing TEXT,
    technical_requirements TEXT,
    transportation TEXT,
    accommodations TEXT,
    post_event_report TEXT,
    FOREIGN KEY (event_id) REFERENCES event(event_id)
)''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('event.csv', 'event')
load_csv_to_table('attendees.csv', 'attendees')
load_csv_to_table('logistics.csv', 'logistics')
load_csv_to_table('documentation.csv', 'documentation')

# Commit the changes and close the connection
conn.commit()
conn.close()

print("Database created successfully.")
```
### Backup and Recover SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (if not exists, a new database will be created)
conn = sqlite3.connect('backup_recovery.db')
cursor = conn.cursor()

# Create the Backup_Schedule table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Backup_Schedule (
        schedule_id INTEGER PRIMARY KEY AUTOINCREMENT,
        backup_type TEXT,
        frequency TEXT
    )
''')

# Create the Storage_Location table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Storage_Location (
        location_id INTEGER PRIMARY KEY AUTOINCREMENT,
        location_name TEXT,
        address TEXT
    )
''')

# Create the Recovery_Procedure table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Recovery_Procedure (
        procedure_id INTEGER PRIMARY KEY AUTOINCREMENT,
        description TEXT
    )
''')

# Create the Backup_Log table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Backup_Log (
        log_id INTEGER PRIMARY KEY AUTOINCREMENT,
        schedule_id INTEGER,
        location_id INTEGER,
        timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
        status TEXT,
        FOREIGN KEY (schedule_id) REFERENCES Backup_Schedule(schedule_id),
        FOREIGN KEY (location_id) REFERENCES Storage_Location(location_id)
    )
''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('procedure.csv', 'procedure')
load_csv_to_table('schedule.csv', 'schedule')
load_csv_to_table('location.csv', 'location')
load_csv_to_table('log.csv', 'log')
# Commit the changes and close the connection
conn.commit()
conn.close()

print("Backup and Recovery Database created successfully.")
```
### Policy SQLite3 DB
```python
import sqlite3

# Connect to the SQLite database (if not exists, a new database will be created)
conn = sqlite3.connect('policy_management.db')
cursor = conn.cursor()

# Create the Policy table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy (
        PolicyID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyName TEXT,
        TypeID INTEGER,
        Description TEXT,
        CreationDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        FOREIGN KEY (TypeID) REFERENCES Policy_Type(TypeID)
    )
''')

# Create the Policy_Type table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Type (
        TypeID INTEGER PRIMARY KEY AUTOINCREMENT,
        TypeName TEXT,
        Description TEXT,
        tags TEXT
    )
''')

# Create the Policy_Owner table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Owner (
        OwnerID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        OwnerName TEXT,
        DepartmentID TEXT,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Document table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Document (
        DocumentID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        DocumentName TEXT,
        DocumentType TEXT,
        Location TEXT,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Revision table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Revision (
        RevisionID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        RevisionDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        VersionNumber TEXT,
        ChangesMade TEXT,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Compliance table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Compliance (
        ComplianceID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        ComplianceStatus TEXT,
        AssessmentDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        IssuesFound TEXT,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Approval table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Approval (
        ApprovalID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        ApproverName TEXT,
        ApprovalDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Research table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Research (
        RelatedDocID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        RelatedDocName TEXT,
        DocType TEXT,
        Location TEXT,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Training table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Training (
        TrainingID INTEGER PRIMARY KEY AUTOINCREMENT,
        PolicyID INTEGER,
        EmployeeName TEXT,
        TrainingDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        FOREIGN KEY (PolicyID) REFERENCES Policy(PolicyID)
    )
''')

# Create the Policy_Config_Azure table
cursor.execute('''
    CREATE TABLE IF NOT EXISTS Policy_Config_Azure (
        ConfigID INTEGER PRIMARY KEY AUTOINCREMENT,
        ResourceName TEXT,
        ResourceType TEXT,
        ConfigurationType TEXT,
        ConfigurationDetails TEXT,
        CreatedBy TEXT,
        CreatedDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        LastModifiedBy TEXT,
        LastModifiedDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        Notes TEXT
    )
''')

# Function to load data from a CSV file into a specified table
def load_csv_to_table(csv_file, table_name):
    with open(csv_file, 'r') as f:
        reader = csv.reader(f)
        columns = next(reader)  # Get the column names from the first row
        query = f'INSERT INTO {table_name} ({",".join(columns)}) VALUES ({",".join("?" for _ in columns)})'
        for data in reader:
            cursor.execute(query, data)
    conn.commit()

# Load data from CSV files into tables
load_csv_to_table('policy.csv', 'Policy')
load_csv_to_table('policy_type.csv', 'Policy_Type')
load_csv_to_table('policy_owner.csv', 'Policy_Owner')
load_csv_to_table('policy_document.csv', 'Policy_Document')
load_csv_to_table('policy_revision.csv', 'Policy_Revision')
load_csv_to_table('policy_compliance.csv', 'Policy_Compliance')
load_csv_to_table('policy_approval.csv', 'Policy_Approval')
load_csv_to_table('policy_research.csv', 'Policy_Research')
load_csv_to_table('policy_training.csv', 'Policy_Training')
load_csv_to_table('policy_config_azure.csv', 'Policy_Config_Azure')

# Commit the changes and close the connection
conn.commit()
conn.close()

print("Policy Management Database created successfully.")
```

## 4. Flat File Generation
Using a git repository, CSVs host operational data for documents, such as letterheads, invoices, etc. This is a pre-software development phase of operations where the aesthetics are built to maintain legitimacy of brand.
## 5. Software Development
Splitting the git repository into a software development branch allows for further development of operations.
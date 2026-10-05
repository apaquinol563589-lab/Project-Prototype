# Personal Inventory Management System

## 1. Project Title

### Personal Inventory Management System

## 2. Project Description

The Inventory Management System is a desktop application designed to
help users manage and organize inventory items. The system allows users
to add, view, update, and delete inventory items, organize items into
customizable categories, and calculate inventory values.

The system addresses the problem of manually tracking inventory, which
can become difficult when there are many items to manage. By using a
graphical interface and SQLite3 database, the system provides a more
organized way to store, retrieve, and manage inventory information.

## 3. Project Objectives

The main objectives of the project are:

-   To create a functional inventory management system.
-   To allow users to perform CRUD operations on inventory items.
-   To organize inventory items using customizable categories.
-   To permanently store inventory data using SQLite3.
-   To provide calculated inventory values.
-   To demonstrate object-oriented and modular programming in Python.
-   To provide a simple graphical user interface.

## 4. Features

### Inventory Management

Allows users to:

-   Add items
-   View items
-   Update items
-   Delete items
-   Assign items to categories
-   Calculate the total value of an item

### Category Management

Allows users to:

-   Create categories
-   View categories
-   Count items under each category
-   Delete unused categories

### Inventory Calculations

The system calculates:

**Total Value = Quantity × Price**

It also displays:

-   Total number of items
-   Total quantity
-   Total inventory value

### Data Persistence

Inventory and category information is stored permanently in an SQLite3
database.

## 5. Technologies Used

### Programming Language

Python

### GUI Framework

PyQt6

### Database

SQLite3

### Other Tools and Libraries

-   Python `dataclasses`
-   Python `sqlite3`
-   PyCharm / VS Code
-   Git (if applicable)

## 6. Project Structure

``` text
PythonProject/
│
├── Database/
│   ├── __init__.py
│   └── database.py
│
├── Features/
│   ├── Calculate/
│   │   ├── __init__.py
│   │   ├── model.py
│   │   ├── repository.py
│   │   ├── service.py
│   │   └── view.py
│   │
│   ├── Category/
│   │   ├── __init__.py
│   │   ├── model.py
│   │   ├── repository.py
│   │   ├── service.py
│   │   └── view.py
│   │
│   ├── Control/
│   │   ├── __init__.py
│   │   ├── controller.py
│   │   └── view.py
│   │
│   └── Management/
│       ├── __init__.py
│       ├── model.py
│       ├── repository.py
│       ├── service.py
│       └── view.py
│
├── main.py
└── README.md
```

### Database/

Contains the SQLite3 database configuration.

`database.py` creates the database connection and creates the required
database tables.

### Management/

Handles inventory items.

-   `model.py` --- Defines the Item data model.
-   `repository.py` --- Performs database operations on inventory items.
-   `service.py` --- Handles validation and inventory business rules.
-   `view.py` --- Displays the inventory table.

### Category/

Handles inventory categories.

-   `model.py` --- Defines the Category data model.
-   `repository.py` --- Performs category database operations.
-   `service.py` --- Handles category rules and validation.
-   `view.py` --- Displays the category management interface.

### Control/

Handles inventory controls.

-   `controller.py` --- Processes Add, Update, and Delete operations.
-   `view.py` --- Provides the inventory control panel.

### Calculate/

Handles inventory calculations.

-   `model.py` --- Defines calculation data models.
-   `repository.py` --- Retrieves inventory data for calculations.
-   `service.py` --- Handles calculation operations.
-   `view.py` --- Displays calculation results.

### main.py

Starts the application and connects the different components.

## 7. Installation and Setup

### Requirements

-   Python 3.11 or newer
-   PyQt6

### Step 1 --- Install Python

Install Python and make sure Python is available in the system PATH.

### Step 2 --- Install PyQt6

Open a terminal in the project directory and run:

``` bash
pip install PyQt6
```

SQLite3 is included with Python and normally does not require a separate
installation.

### Step 3 --- Open the Project

Open the project folder in PyCharm, VS Code, or another Python IDE.

### Step 4 --- Run the Application

Open the terminal in the project directory and run:

``` bash
python main.py
```

The application will automatically create the SQLite database and
required tables.

## 8. How to Use the System

### Inventory Management

1.  Open the application.
2.  Select **Inventory Management**.
3.  Enter the item name.
4.  Enter the quantity.
5.  Enter the price.
6.  Select a category.
7.  Click **Add**.
8.  The item will appear in the inventory table.

To update an item:

1.  Select an item from the table.
2.  Modify its information.
3.  Click **Update**.

To delete an item:

1.  Select an item.
2.  Click **Delete**.

### Category Manager

1.  Open **Category Manager**.
2.  Enter a category name.
3.  Add the category.
4.  The category becomes available in the inventory Control Panel.

### Calculations

Open **Calculations** to view:

-   Individual item values
-   Total quantity
-   Total number of items
-   Total inventory value

## 9. OOP Implementation

The project uses object-oriented programming through classes and
objects.

### Important Classes

-   `Database`
-   `Item`
-   `Category`
-   `ManagementRepository`
-   `ManagementService`
-   `ManagementView`
-   `CategoryRepository`
-   `CategoryService`
-   `CategoryView`
-   `ControlPanelController`
-   `ControlPanelView`
-   `CalculateRepository`
-   `CalculateService`
-   `CalculateView`

### Encapsulation

Encapsulation is applied by keeping data and operations inside their
respective classes. For example, database operations are contained
inside repository classes instead of being directly performed by the
GUI.

### Inheritance

PyQt6 classes are extended by application classes.

For example:

``` python
class ManagementView(QWidget):
```

`ManagementView` inherits from `QWidget`.

Other GUI classes also inherit from PyQt6 widgets.

### Polymorphism

Polymorphism is used through inherited PyQt6 methods and signals/slots,
where different application widgets can provide their own behavior while
following the interfaces provided by the PyQt6 framework.

## 10. Database

The system uses SQLite3 for persistent data storage.

The database file is:

``` text
Database/inventory.db
```

### Tables

#### items

  Column     Type      Description
  ---------- --------- -------------------
  id         INTEGER   Unique item ID
  name       TEXT      Item name
  quantity   INTEGER   Number of items
  price      REAL      Price of one item
  category   TEXT      Item category

#### categories

  Column   Type      Description
  -------- --------- --------------------
  id       INTEGER   Unique category ID
  name     TEXT      Category name

### Database Operations

The system performs the following operations:

**Create** --- Adds new inventory items and categories.

**Read** --- Retrieves inventory items and categories from SQLite3.

**Update** --- Modifies existing inventory item information.

**Delete** --- Removes inventory items and categories when allowed.

**Search / Retrieval** --- Retrieves categories and inventory records
and can locate a category by name.

## 11. Screenshots

Screenshots of the working application should be placed in this section.

### Main Menu

Shows the main application menu and provides access to the different
features.

### Inventory Management

Shows the Control Panel and inventory table in the same window.

### Category Manager

Shows the available categories and the number of items assigned to each
category.

### Calculations

Shows individual inventory values and overall inventory statistics.

> Add actual screenshots of the completed application to this section.

## 12. Testing

The system was tested by performing common inventory operations and
checking whether the actual results matched the expected results.

  Test                               Expected Result                     Actual Result
  ---------------------------------- ----------------------------------- ---------------
  Add valid item                     Item appears in inventory           Passed
  Add empty item name                Error message appears               Passed
  Add negative quantity              Error message appears               Passed
  Add negative price                 Error message appears               Passed
  Update item                        Item information changes            Passed
  Delete item                        Item disappears from inventory      Passed
  Create category                    Category appears in category list   Passed
  Create duplicate category          Error message appears               Passed
  Delete category containing items   Deletion is prevented               Passed
  Calculate item value               Quantity × Price is displayed       Passed
  Restart application                Saved data remains available        Passed

## 13. Known Issues / Limitations

-   The system currently focuses on basic inventory management.
-   There is no user authentication or account system.
-   Inventory search and advanced filtering are not currently
    implemented.
-   The system does not currently generate printable reports.
-   The interface is designed for desktop use.
-   The database is intended for local use rather than multi-user
    network access.
-   The system does not currently include automatic low-stock
    notifications.

## 14. Author

**Name:** Allen James A. Paquinol

**Section:** CS26/L (3580)

**Project:** Personal Inventory Management System

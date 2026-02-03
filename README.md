# Homework 9: Basics of Working with Classes

## 📌 Description

This homework focuses on practicing the fundamentals of **Object-Oriented Programming (OOP)** in Python by building the core logic for a **CLI-based Address Book** application.

The goal is to design and implement a system of classes that manage contacts, their names, and phone numbers. This logic will later be integrated into a command-line assistant in the next homework.

---

## 🎯 Learning Objectives

By completing this homework, you will gain experience in:

- Understanding the basics of Object-Oriented Programming (OOP)
- Working with classes and objects
- Implementing and using class methods
- Validating and managing structured data

---

## 🗂️ Project Structure

The project implements the following main entities:

- **Field** – Base class for record fields
- **Name** – Class for storing a contact's name (required field)
- **Phone** – Class for storing a phone number (must contain exactly 10 digits)
- **Record** – Class that represents a contact and stores a name and a list of phone numbers
- **AddressBook** – Class for storing and managing records (inherits from `UserDict`)

---

## ⚙️ Functionality

### AddressBook

- Add a new contact record
- Find a record by contact name
- Delete a record by contact name

### Record

- Add a phone number
- Remove a phone number
- Edit an existing phone number
- Find a phone number

### Phone

- Validates that the phone number consists of exactly **10 digits**

---

## ▶️ Usage Example

```python
# Create a new address book
book = AddressBook()

# Create a record for John
john_record = Record("John")
john_record.add_phone("1234567890")
john_record.add_phone("5555555555")

# Add John's record to the address book
book.add_record(john_record)

# Create and add a record for Jane
jane_record = Record("Jane")
jane_record.add_phone("9876543210")
book.add_record(jane_record)

# Print all records
for name, record in book.data.items():
    print(record)

# Edit John's phone number
john = book.find("John")
john.edit_phone("1234567890", "1112223333")
print(john)

# Find a specific phone number
found_phone = john.find_phone("5555555555")
print(f"{john.name}: {found_phone}")

# Delete Jane's record
book.delete("Jane")
```

---

## 📦 Submission Requirements

- Upload the solution files to the repository **`goit-pycore-hw-06`**
- Attach links to the repository in your homework submission
- Upload the repository as a **ZIP archive**

---

## ✅ Evaluation Criteria

### AddressBook

- `add_record` method adds a record to `self.data`
- `find` method searches for a record by name
- `delete` method removes a record by name

### Record

- Stores a `Name` object in a separate attribute
- Stores a list of `Phone` objects
- Implements methods:
  - `add_phone`
  - `remove_phone`
  - `edit_phone`
  - `find_phone`

### Phone

- Implements phone number validation (exactly 10 digits)

---

🚀 _This homework builds the foundation for extending the CLI assistant with full functionality in the next assignment._

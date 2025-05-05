# Pharmacy Management System

A **Terminal-based Pharmacy Inventory & Sales Management System** built using `bash` and `whiptail` for a user-friendly text-based GUI.

## Features

- 🏥 **Inventory Management**
  - Add, update, and display medicine entries
  - Remove expired medicines
  - View low stock items
  - Search by medicine name or category

- 💰 **Sales Management**
  - Process sales and update stock
  - Log transactions with total price
  - Maintain customer purchase history

- 📊 **Reporting**
  - Generate sales report by date range
  - View top K medicines by sales quantity
  - Display expired medicines

## File Structure

| File                    | Description                          |
|-------------------------|--------------------------------------|
| `inventory.txt`         | Stores medicine details              |
| `sales.txt`             | Logs of all sales transactions       |
| `customers.txt`         | Records customer purchase history    |
| `expired_medicines.txt` | Tracks expired medicines             |
| `error.txt`             | Error logs for validation issues     |

## Data Formats

- **Inventory**: `name,quantity,price,expiry,category`
- **Sales**: `date,medicine_name,quantity,total_price`
- **Customer History**: `customer_name,contact,(date - medicine - quantity - total)`

## Validation Rules

- **Date**: Must be in `YYYY-MM-DD` format.
- **Price**: Must be a positive float or integer (e.g., `5`, `5.99`).
- **Quantity**: Must be a positive integer only.
- Duplicate medicine names are not allowed in the inventory.

---

## ✅ Validation Functions

To maintain data accuracy, the script uses built-in functions to validate user input before storing it.

### `validate_date()`
- **Purpose**: Ensures the date is in the format `YYYY-MM-DD`.
- **Used in**: Adding medicines, generating sales reports.
- **Logic**: Uses regular expressions to match correct date pattern.
- **Example**:  
  ✅ `2025-12-31`  
  ❌ `31/12/2025`

---

### `validate_price()`
- **Purpose**: Ensures the price entered is a valid number (integer or decimal).
- **Used in**: Adding or updating medicine prices.
- **Logic**: Accepts inputs like `10`, `0.99`, `5.5`.
- **Example**:  
  ✅ `12.50`  
  ❌ `abc` or `-1.25`

---

### `validate_quantity()`
- **Purpose**: Ensures that quantity values are valid non-negative integers.
- **Used in**: Adding/updating medicines and processing sales.
- **Logic**: Accepts inputs like `10`, `0`, but rejects decimals or negative numbers.
- **Example**:  
  ✅ `20`  
  ❌ `-5`, `2.5`, `abc`

---
## 🧭 Main Menu Navigation

When you run the script (`./PMS.sh`), a **Main Menu** appears using a terminal-based GUI built with `whiptail`. This menu offers access to all core features of the system.

### 📋 Menu Options

| Option Number | Feature                      | Description                                                      |
|---------------|------------------------------|------------------------------------------------------------------|
| 1             | Add Medicine                 | Add a new medicine to the inventory. Requires all details.       |
| 2             | Update Medicine              | Change quantity or price of an existing medicine.                |
| 3             | Remove Expired Medicines     | Automatically removes medicines past their expiry date.          |
| 4             | Display Inventory            | Shows the current list of all available medicines.               |
| 5             | Process Sale                 | Logs a sale and updates inventory and customer history.          |
| 6             | Display Low Stock Medicines  | Lists medicines below a user-specified quantity threshold.       |
| 7             | Show Expired Medicines       | Displays medicines marked as expired and stored in a log file.   |
| 8             | Generate Sales Report        | Creates a report of sales between two selected dates.            |
| 9             | Top K Medicines              | Lists the top-selling medicines based on quantity sold.          |
| 10            | Search Medicine              | Search by medicine name or category.                             |
| 11            | Customer Purchase History    | View purchase records for a specific customer.                   |
| 12            | Exit                         | Exits the program safely.                                        |

### 🔁 Looping Behavior

The menu reappears after each action, allowing you to perform multiple operations without restarting the script.

---

This menu makes the system interactive and user-friendly, even for users with limited command-line experience.

## Example Use Cases
## Main Menu
![image](https://github.com/user-attachments/assets/6c35f08a-3b08-4d4b-877c-374ffb43a96e)

## Add medicine
![image](https://github.com/user-attachments/assets/99f68c93-3782-409a-926e-2584aa041eed)
![image](https://github.com/user-attachments/assets/db79d84e-6fa5-4f16-aecc-93423819154b)
![image](https://github.com/user-attachments/assets/41daa7c5-c934-4116-8fd3-cc40557a9f45)
![image](https://github.com/user-attachments/assets/3d284289-a238-4d0d-aac9-270839334bfa)
![image](https://github.com/user-attachments/assets/e7801f62-35a0-43eb-83fc-3fec179947bd)
![image](https://github.com/user-attachments/assets/6ec96ef4-46e6-4cf8-85d1-26cae483bedf)


## Update Medicine
![image](https://github.com/user-attachments/assets/6bd8ec94-d4c7-4bae-9520-ea4348558611)
![image](https://github.com/user-attachments/assets/3b9ead90-ed7d-4cd9-b855-75f2ebc3856e)

## Remove Expired Medicine 
![image](https://github.com/user-attachments/assets/8dbd5435-0101-4552-9781-41f52707ef34)

## Display Invemtory
![image](https://github.com/user-attachments/assets/40553dbb-87b2-4ada-88ee-db35619739c1)

## Process Sale
![image](https://github.com/user-attachments/assets/68d14aa6-2402-405a-ad5b-37fa8ab37d43)
![image](https://github.com/user-attachments/assets/24ca3b65-a0ed-44ab-a087-10b6a567b987)
![image](https://github.com/user-attachments/assets/a51b49f4-ef1c-4473-9309-e05411183861)
![image](https://github.com/user-attachments/assets/7b0a4760-5668-4377-99bf-6d957b0c6a04)
![image](https://github.com/user-attachments/assets/d88468cf-c659-4782-92f2-ecd7d91777b6)

## Display Low Stock Medicines
![image](https://github.com/user-attachments/assets/fc783a03-e789-4301-9276-75c377b68d5c)
![image](https://github.com/user-attachments/assets/df1a7796-7324-4eed-ad10-cbb2aa3d461f)
![image](https://github.com/user-attachments/assets/169ba3a1-bcb8-4699-a595-6bd377fbb782)


## Show Expired Medicines 
![image](https://github.com/user-attachments/assets/7da28f47-9dd4-404e-b294-ef566f8a462b)

## Generate Sales Report
![image](https://github.com/user-attachments/assets/26c72a7e-f8f2-4196-b209-0c3672b5ee8f)
![image](https://github.com/user-attachments/assets/bdec901b-5d07-4f41-a550-f97d43579d7f)
![image](https://github.com/user-attachments/assets/b80f9e10-bf26-41bb-a194-8b52a9bc3b8a)

## Top K Medicines
![image](https://github.com/user-attachments/assets/33d1ff55-6eea-43e6-b633-3925f31acedb)
![image](https://github.com/user-attachments/assets/1a2eb27d-0ca2-4428-b8f4-a0bf401a42fa)

## Search Medicine
![image](https://github.com/user-attachments/assets/fc25b517-36b5-4b4b-8369-3f1c7e478858)
![image](https://github.com/user-attachments/assets/6a92e9a1-11bb-4249-8a0b-405780a0a9b2)
![image](https://github.com/user-attachments/assets/4c9a53ea-b63f-427c-8da1-9a2c4df38960)

## Customer Purchase History
![image](https://github.com/user-attachments/assets/536eeaee-19d7-4a05-9fab-0a37c28b1e81)
![image](https://github.com/user-attachments/assets/e5f77e28-223c-4ab0-9931-7f142a2fdb28)

## Exit  
![image](https://github.com/user-attachments/assets/8bb3ede3-451b-48e3-ac2a-8d81622ce9f4)



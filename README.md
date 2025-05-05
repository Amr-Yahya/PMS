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

| File                  | Description                          |
|-----------------------|--------------------------------------|
| `inventory.txt`       | Stores medicine details              |
| `sales.txt`           | Logs of all sales transactions       |
| `customers.txt`       | Records customer purchase history    |
| `expired_medicines.txt` | Tracks expired medicines           |
| `error.txt`           | Error logs for validation issues     |

## Data Formats

- **Inventory**: `name,quantity,price,expiry,category`
- **Sales**: `date,medicine_name,quantity,total_price`
- **Customer History**: `customer_name,contact,(date - medicine - quantity - total)`

## Validation Rules

- **Date**: `YYYY-MM-DD` format
- **Price**: Positive float or integer (e.g. `5`, `5.99`)
- **Quantity**: Positive integer only
- Duplicate medicine names are not allowed in the inventory.

## Requirements

- `bash` shell
- `whiptail` (for terminal dialogs)

Install `whiptail` on Debian/Ubuntu-based systems:
```bash
sudo apt-get install whiptail

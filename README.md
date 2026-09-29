# Personal Expense Tracker

A simple command-line application to add, view, delete, and summarize your personal expenses. All data is saved in a CSV file, so your records are still there the next time you run the program.

## Features

- **Add expenses** with category, amount, and short description (the date is recorded itself)
- **View all expenses** in a neat table
- **Delete an expense** by its ID
- **View a summary** showing total spending and a category-wise breakdown, sorted from highest to lowest
- **Local storage** in a plain CSV file that you can also open in Excel or Google Sheets
- **Input validation** for amounts and choices in menu
  

## Requirements

- Python 3.6 or higher
- No external libraries needed (uses only the built-in `csv`, `os`, and `datetime` modules)

## Getting Started

1. Save the code as `expense_tracker.py` (or download this repository).
2. Open a terminal in the project folder.
3. Run:

```bash
python expense_tracker.py
```

On some systems you may need to use `python3` instead of `python`.

The file `expenses.csv` is created automatically the first time you run the program.

## Usage

When the program starts, you will see this menu:

```
=== Personal Expense Tracker ===
1. Add Expense
2. View Expenses
3. Delete Expense
4. View Summary
5. Exit
Choose an option (1-5):
```

| Option | What it does |
|--------|--------------|
| 1 | Asks for a category, amount, and description, then saves the expense with today's date |
| 2 | Shows all saved expenses in a table |
| 3 | Shows all expenses, then asks for the ID of the one to delete |
| 4 | Shows total spending and spending per category |
| 5 | Exits the program |

### Example

```
Choose an option (1-5): 1
Enter category (e.g., Food, Travel, Bills): Food
Enter amount: 250
Enter a short description: Lunch with friends
Expense added successfully! (ID: 1)
```

Viewing expenses:

```
ID   Date        Category       Amount    Description
------------------------------------------------------------
1    2026-09-29  Food           250.0     Lunch with friends
```

Viewing the summary:

```
--- Expense Summary ---
Food           : 250.00
-------------------------
Total          : 250.00
```

## Data Storage

Expenses are stored in `expenses.csv` in the same folder where you run the program, with these columns:

| Column | Description |
|--------|-------------|
| ID | Unique number for each expense |
| Date | Date the expense was added (`YYYY-MM-DD`) |
| Category | Category you entered (e.g., Food, Travel, Bills) |
| Amount | Amount spent |
| Description | Short note about the expense |

To back up your data, simply copy `expenses.csv`. To start fresh, delete the file and it will be recreated on the next run.

## Project Structure

```
.
├── expense_tracker.py   # Main program
├── expenses.csv         # Created automatically to store your data
└── README.md
```

## Known Limitations

- Category names are case-sensitive, so `Food` and `food` are treated as different categories in the summary.
- The next ID is based on the last row in the file, so if you delete the most recent expense, its ID will be reused.
- The date is always today's date; you cannot enter a past date.
- Currency is not specified; amounts are shown as plain numbers.

## Future Ideas

- Edit an existing expense
- Filter or search by date range or category
- Monthly reports
- Export summaries to a file

## License

This project is open source and free to use. Add a license of your choice (for example, MIT) if you plan to share it publicly.

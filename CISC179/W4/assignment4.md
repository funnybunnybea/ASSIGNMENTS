# Patient Vaccine Record System

```python
patient = {}

record_number = 1

def insert():
    global record_number

    first_name = input("Enter patient's first name: ")
    last_name = input("Enter patient's last name: ")
    birth_month = int(input("Enter birth month when vaccine was administered (1-12): "))

    patient[record_number] = {
        "first_name": first_name,
        "last_name": last_name,
        "birth_month": birth_month
    }

    print("Record", record_number, "added successfully.\n")

    record_number += 1


while True:
    insert()  

    again = input("Add another patient? (Y/N): ")
    if again.upper() != "Y":
        break

print("\nAll patient records:")
for rec_num, details in patient.items():
    print("Record", rec_num, ":", details)
```

**Sample output:**
```
Enter patient's first name: John
Enter patient's last name: Smith
Enter birth month when vaccine was administered (1-12): 5
Record 1 added successfully.

Add another patient? (Y/N): Y
Enter patient's first name: Jane
Enter patient's last name: Doe
Enter birth month when vaccine was administered (1-12): 9
Record 2 added successfully.

Add another patient? (Y/N): N

All patient records:
Record 1 : {'first_name': 'John', 'last_name': 'Smith', 'birth_month': 5}
Record 2 : {'first_name': 'Jane', 'last_name': 'Doe', 'birth_month': 9}
```

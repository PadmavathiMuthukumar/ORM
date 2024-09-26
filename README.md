# Ex02 Django ORM Web Application
## Date: 26-09-24

## AIM
To develop a Django application to store and retrieve data from a Bank database using Object Relational Mapping(ORM).

## Entity Relationship Diagram
![image](https://github.com/user-attachments/assets/dd52d20a-87bd-4a4e-9006-ab5dfeb9da22)


## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 customers.

## PROGRAM
## Models
```
from django.db import models
from django.contrib import admin
class Bank(models.Model):
    customer_id = models.IntegerField(primary_key=True)
    customer_name = models.CharField(max_length=50)
    account_type = models.CharField(max_length=50)
    loan_amount = models.DecimalField(max_digits=10, decimal_places=2)  
    monthly_interest = models.DecimalField(max_digits=5, decimal_places=2)  
    due_date = models.DateField()

    def __str__(self):
        return self.customer_name  # Optional, for better representation in admin or shell

class BankAdmin(admin.ModelAdmin):
    list_display = ('customer_id', 'customer_name', 'account_type', 'loan_amount', 'monthly_interest', 'due_date')
admin.site.register(Bank, BankAdmin)
```
## Admin
```
from django.contrib import admin
from .models import Bank, Loandetails

admin.site.register(Bank)
admin.site.register(Loandetails)
```
## OUTPUT

![image](https://github.com/user-attachments/assets/e8997ce2-4e68-4689-bfe9-83e1556cf5e9)
![image](https://github.com/user-attachments/assets/040b062c-45cb-4bae-8d18-27aa03a148d7)


## RESULT
Thus the program for creating a database using ORM hass been executed successfully

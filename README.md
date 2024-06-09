# 1.06_Individual-task-Pyhton

```py
import datetime

class Client:
    number_of_clients = 0

    def __init__(self, name):
        self.name = name
        self.transactions = []
        Client.number_of_clients += 1

    def add_transaction(self, transaction):
        self.transactions.append(transaction)

class Item:
    def __init__(self, clothingType, price):
        self.clothingType = clothingType
        self.price = price

class Transaction:
    def __init__(self, client, items):
        self.client = client
        self.items = items
        self.time_stamp = datetime.datetime.now()

# Adding clients to a list
clients = []
clients.append(Client('Julie'))
clients.append(Client('Mari'))
clients.append(Client('Nelli'))

# Creating some items
items = [
    Item("Dress", 200),
    Item("Jeans", 500),
    Item("Jacket", 300),
    Item("Shoes", 250),
    Item("Hat", 80)
]

# Creating some transactions
transaction1 = Transaction(clients[0], [items[0], items[1], items[4]])
transaction2 = Transaction(clients[1], [items[2], items[3]])
transaction3 = Transaction(clients[2], [items[2], items[1], items[3]])

# Adding transactions to clients
clients[0].add_transaction(transaction1)
clients[2].add_transaction(transaction3)
clients[1].add_transaction(transaction2)

# Printing clients
print(f'We have the following clients:')
for client in clients:
    print(f'{client.name}')

# Print all transactions of each client
for client in clients:
    print(f"\nTransactions for {client.name}:")
    for transaction in client.transactions:
        print(f"  Transaction at {transaction.time_stamp}:")
        for item in transaction.items:
            print(f"    Item: {item.clothingType}, Price: {item.price}")
```

# Python-Inventory-App-
Python Inventory App - I’m working towards building an inventory of books, apparel, and merchandise.

STEP 1 — Define Scope & Responsibility

(Mental setup)

In plain English

“My Python app owns inventory correctness. Humans only submit transactions.”

Decisions

Inventory is never edited directly

Transactions are the only input

Google Sheets is a datastore + dashboard

STEP 2 — Model the Domain (START HERE)

Your first actual code

In plain English

“I define what inventory is before worrying about where it lives.”

You create:

InventoryItem

Transaction

TransactionType (SALE, RESTOCK, ADJUSTMENT)

No Sheets.
No APIs.

STEP 3 — Business Rules Layer

The brain

In plain English

“These rules apply no matter where data comes from.”

Rules like:

No negative inventory

Every change must have a reason

Inventory is derived from transactions

You implement:

InventoryService

STEP 4 — Repository Interface

Abstraction layer

In plain English

“I don’t care how inventory is stored.”

You define:

InventoryRepository (interface)

No Google Sheets yet.

STEP 5 — In-Memory Repository

Practice + testing

In plain English

“I fake storage so I can prove logic works.”

Use dicts + lists

Fast iteration

Zero external dependencies

STEP 6 — Tests

Confidence & correctness

In plain English

“I know exactly what happens when a transaction is processed.”

Test:

Sale reduces inventory

Restock increases inventory

Invalid transactions fail

STEP 7 — Google Sheets Repository

First real integration

In plain English

“Same logic, real storage.”

Read inventory sheet

Append transactions

Never edit inventory manually

STEP 8 — Transaction Ingestion

How transactions enter the system

In plain English

“Humans submit data, Python decides if it’s valid.”

Sources:

Google Form → Sheet

CSV file

New rows in a PendingTransactions sheet

Python:

Scans for unprocessed rows

Validates

Applies

Marks processed

STEP 9 — Automation & Safety

Make it reliable

In plain English

“The system protects itself.”

Idempotency (don’t double-process)

Logging

Low-stock alerts

Daily reconciliation

STEP 10 — Project Polish

Career-level finish

In plain English

“This looks like a real internal tool.”

README

Architecture diagram

Sample data

Clear setup steps

---
title: "Finding every GST registration under one PAN, and why it matters"
description: "How PAN and GSTIN relate, why one business can have many GSTINs, and how to reconcile suppliers across states."
---

# Finding every GST registration under one PAN, and why it matters

A business has one PAN but can hold many GST registrations: one or more in each state where it operates. If you buy from, sell to or audit a multi-state business, knowing all its GSTINs prevents mismatched invoices, missed input tax credit and payments to the wrong entity.

## How PAN and GSTIN relate

Every GSTIN has 15 characters, and the PAN is built into it. Take the example GSTIN `27AAOCM9194L2ZF`:

| Characters | Example | Meaning |
|---|---|---|
| 1 to 2 | 27 | State code (27 is Maharashtra) |
| 3 to 12 | AAOCM9194L | PAN of the business |
| 13 | 2 | Entity number: the 2nd registration for this PAN in this state |
| 14 | Z | Z by default |
| 15 | F | Check character computed from the first 14 |

The 4th letter of the PAN tells you the holder type: C for company, P for individual, F for firm or LLP, H for HUF, T for trust, A for AOP and G for government.

## Why one PAN has many GSTINs

- **Multi-state operations.** GST is registered state by state, so a company with offices or warehouses in five states usually has at least five GSTINs, each starting with a different state code.
- **Multiple registrations in one state.** A business can hold more than one registration in the same state, for example for separate business verticals. The 13th character counts them: 1 for the first, 2 for the second, and so on, then letters after 9.
- **Special registrations.** Some entities hold registrations for specific purposes, such as tax deduction at source.

## Why it matters

**Reconciling suppliers.** A supplier's invoice must carry the GSTIN of the registration that actually supplied the goods. If your vendor master holds only one GSTIN for a multi-state supplier, invoices from its other states may be booked against the wrong record.

**Input tax credit.** Credit depends on the supplier's return for the right GSTIN. Mixing up registrations is a common cause of mismatches.

**Spotting cancelled registrations.** A business can have an active GSTIN in one state and a cancelled one in another. Paying against a cancelled GSTIN creates problems at reconciliation time. Check status, not just existence.

**Group view.** For due diligence, seeing every registration under a PAN shows where a business really operates.

## A simple reconciliation routine

1. Extract the PAN (characters 3 to 12) from each supplier GSTIN in your vendor master.
2. Group suppliers by PAN to find the same business recorded several times.
3. For each PAN, list every GSTIN and its state and status.
4. Flag cancelled or suspended registrations and confirm with the supplier.
5. Repeat quarterly, or before large payments.

## Automating the check

Checking a handful of suppliers by hand is fine. For hundreds, use an API. IndiaCos explains each part of the number in its [GSTIN format guide](https://indiacos.com/gstin-format), lets you decode and validate any number with [GSTIN search](https://indiacos.com/gstin-search), and offers an [API](https://indiacos.com/api) for running the same checks in bulk from your own systems.

---
[Back to the IndiaCos guide](./)

---
id: minus
summary: An Android budget tracker that turns one budget into a daily, weekly, biweekly or monthly allowance, with a calculator-style numpad, recurring expenses and subscriptions, credit card reminders, CSV backup and a Wear OS companion.
category: personal-finance
tags: [budgeting, expense-tracker, android, wear-os]
authors:
  - name: Isaac Serrano
    url: https://github.com/isaacsa51
license: Apache-2.0
languages: [en, bg, de, el, es, es-MX, fa, fr, hi, it, ja, ko, pt, ru, zh]
limitations:
  - "There are no accounts: everything is kept on the phone, and it leaves the phone only when the person exports a CSV file, picks a sync folder or pairs a watch."
  - "One budget period runs at a time, in one currency chosen for it; amounts are never converted between currencies."
  - "Recurring expenses repeat weekly, every two weeks or monthly; there is no yearly or custom cycle."
  - "A spend reminder only suggests a charge it read in another app's notification; nothing is recorded until the person saves it."
  - "The watch keeps no budget of its own: it shows what the paired phone last sent and hands every expense to the phone."
references:
  - kind: doc
    role: intent
    target: README.md
    title: README
  - kind: doc
    role: context
    target: PROJECT_OVERVIEW.md
    title: Project overview
  - kind: doc
    role: context
    target: CONTRIBUTING.md
    title: Contributing guidelines
---

# Minus

Minus is an Android budget tracker for one person. They set a budget period: a total amount, a
start and finish date and a currency, and Minus breaks it down into what they can spend each day,
week, two weeks or month. Expenses go in through a calculator-style numpad, a leading `+` adds
income and a leading `-` deducts from the budget, and every expense can carry a category, an extra
note and a credit card mark. Recurring expenses and subscriptions are charged on their due dates,
with reminders before and on the day, and can be marked as paid or skipped. When a period ends,
or the person finalizes it early, Minus asks or decides what happens to the money left over and
keeps the period among the past periods. Analytics, a subscriptions overview, home-screen widgets,
CSV backup and folder sync, spend reminders read from bank notifications and a Wear OS companion
app complete the product.

## Intent

"Your money, minus the guesswork": an easy to use and powerful budget tracking app that lets
anyone "register, calculate and make reminders for your recurring expenses alongside credit card
due dates". Mimicking a calculator keeps recording daily spending quick and familiar, and the
budget period lets people "configure your budget to match how you actually think about money".

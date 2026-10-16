---
layout: post
title: Bank Marketing Campaign Analysis (Power BI)
image: "/posts/bank-marketing-hero.png"
tags: [Power BI, DAX, Marketing Analytics]
---

In this project I built a three-page Power BI report on a public bank-marketing dataset of 41,188 phone campaign contacts. The question: where did the campaign's effort go, and where did it actually pay off?

Overall, about 5,000 of the contacts converted, a rate of 11.3%. The interesting part is how unevenly that rate is spread across months, customer groups and contact methods.

---

## Where the effort went

I wrote DAX measures for contacts, conversions and conversion rate, then compared each month's share of all contacts with its conversion rate.

![Share of contacts and conversion rate by month](/img/posts/bank-marketing-hero.png)

May took about a third of all contacts but converted at only 6.4%. The strongest months converted at around 46% on roughly 5% of the volume. In other words, most of the effort went to the weakest part of the calendar.

---

## Who converts

The second page breaks conversion down by age, job and education.

![Conversion by age band, job and education](/img/posts/bank-marketing-segments.png)

- Customers aged 65+ converted at 47.2%, and under-25s at 24.0%. The 35 to 54 age bands were the lowest, at 8.7%.
- Students (31.4%) and retirees (25.2%) converted best; blue-collar customers were lowest at 6.9%.
- Some education groups are tiny, so I flagged groups under 100 contacts as unreliable rather than reading anything into them.

---

## How the contact was made

![Conversion by number of contacts, previous outcome and contact method](/img/posts/bank-marketing-contact-and-recommendations.png)

- Conversion fell with every extra contact, from about 13% on the first call to roughly 4 to 6% by the eighth and ninth.
- Customers with a previous success converted at about 65%.
- Cellular contacts converted nearly three times as often as telephone contacts.

---

## What I would test

1. Shift volume from May and landline telephone toward cellular, as a pilot first.
2. Cap repeat contacts at about 3 to 5 per customer.
3. Prioritize previous-success customers and the high-converting groups (students, 65+, retired).

These are ideas to test, not proven causes. The data is observational: the bank chose who to call and when, so some of these patterns may reflect who was called rather than how.

---

**Tools:** Power BI, DAX measures, slicers and charts.

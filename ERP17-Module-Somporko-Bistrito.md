# ERP17 — মডিউলগুলোর মধ্যে সম্পর্ক (বিস্তারিত)

> এই ডকুমেন্টে ERP17-এর **সব মডিউল একে অপরের সাথে কীভাবে জড়িত** — কোন ডেটা কোথা থেকে আসে, কোথায় যায়, কোন মডিউল ছাড়া কোনটা চলে না — সব বিস্তারিত বাংলায় ব্যাখ্যা করা হয়েছে।

**সম্পর্কিত ডক:** [ERP17-Kivabe-Kaj-Kore.md](./ERP17-Kivabe-Kaj-Kore.md) | [ERP17-Features-Documentation.md](./ERP17-Features-Documentation.md)

---

## সূচিপত্র

1. [মূল নীতি — ERP17 কীভাবে জড়িত](#১-মূল-নীতি--erp17-কীভাবে-জড়িত)
2. [Settings — সব মডিউলের ভিত্তি](#২-settings--সব-মডিউলের-ভিত্তি)
3. [শেয়ারড ডেটা — কোন তথ্য কোথায় ব্যবহার হয়](#৩-শেয়ারড-ডেটা--কোন-তথ্য-কোথায়-ব্যবহার-হয়)
4. [মডিউল সম্পর্ক ম্যাট্রিক্স](#৪-মডিউল-সম্পর্ক-ম্যাট্রিক্স)
5. [প্রতিটি মডিউলের সম্পর্ক (এক থেকে অনেক)](#৫-প্রতিটি-মডিউলের-সম্পর্ক-এক-থেকে-অনেক)
6. [আর্থিক প্রবাহ — টাকা কোথা থেকে কোথায়](#৬-আর্থিক-প্রবাহ--টাকা-কোথা-থেকে-কোথায়)
7. [স্টক প্রবাহ — পণ্য কোথা থেকে কোথায়](#৭-স্টক-প্রবাহ--পণ্য-কোথা-থেকে-কোথায়)
8. [মানবসম্পদ শৃঙ্খল (HRM Chain)](#৮-মানবসম্পদ-শৃঙ্খল-hrm-chain)
9. [গ্রাহক যাত্রা (Customer Journey)](#৯-গ্রাহক-যাত্রা-customer-journey)
10. [যোগাযোগ শৃঙ্খল — SMS ও Emails](#১০-যোগাযোগ-শৃঙ্খল--sms-ও-emails)
11. [ব্রাঞ্চ ও মাল্টি-লোকেশন](#১১-ব্রাঞ্চ-ও-মাল্টি-লোকেশন)
12. [সম্মিলিত ব্যবসায়িক সিনারিও](#১২-সম্মিলিত-ব্যবসায়িক-সিনারিও)
13. [নির্ভরতা তালিকা — কোনটা আগে সেটআপ করতে হবে](#১৩-নির্ভরতা-তালিকা--কোনটা-আগে-সেটআপ-করতে-হবে)

---

## ১. মূল নীতি — ERP17 কীভাবে জড়িত

ERP17 একটি **একীভূত (Integrated) ERP**। এর মানে:

| নীতি | ব্যাখ্যা |
|------|----------|
| **একটি ডেটাবেস** | সব মডিউল একই সিস্টেমে — পণ্য, গ্রাহক, কর্মচারী বারবার যোগ করতে হয় না |
| **শেয়ারড মাস্টার ডেটা** | Settings-এ একবার সেটআপ → সব মডিউলে ব্যবহার |
| **স্বয়ংক্রিয় প্রভাব** | POS-এ বিক্রি → Inventory স্টক কমে → VAT-এ entry → Accounts-এ আয় |
| **ব্রাঞ্চ ভিত্তিক** | halishahar, Dhaka two — প্রতিটি ব্রাঞ্চে আলাদা স্টক/বিক্রি/হিসাব |
| **রোল ভিত্তিক অ্যাক্সেস** | Settings → Roles দিয়ে কে কোন মডিউল দেখবে নিয়ন্ত্রণ |

```
┌─────────────────────────────────────────────────────────────┐
│                    ERP17 Core Platform                       │
│  (Organization, Branch, Users, Roles, Permissions)          │
└──────────────────────────┬──────────────────────────────────┘
                           │
     ┌─────────────────────┼─────────────────────┐
     │                     │                     │
  Master Data          Operations            Finance
  (Settings)           (বিক্রি/ক্রয়)         (Accounts/VAT)
     │                     │                     │
  HRM, Inventory      POS, Ecommerce,       Journal, Invoice
  CRM setup           Hotel, Game Zone       Bill, Payment
```

---

## ২. Settings — সব মডিউলের ভিত্তি

**Settings ছাড়া কোনো মডিউল সঠিকভাবে চলে না।** প্রতিটি মডিউলের Settings-এর সাথে সম্পর্ক:

| Settings বিভাগ | কোন মডিউলে যায় | কী কাজে লাগে |
|----------------|-----------------|--------------|
| **Authentication → Users, Roles** | সব মডিউল | লগইন, অনুমতি, কে কী দেখবে |
| **Organization → Org, Company, Branches** | সব মডিউল | মাল্টি-ব্রাঞ্চ, কোম্পানি স্ট্রাকচার |
| **HRM → Department, Designation, Shift** | HRM, Attendance, Payroll | কর্মচারী তথ্য, উপস্থিতি, বেতন |
| **Payroll → Pay Scales, Payment Types** | Payroll | বেতন স্কেল ও প্রদানের ধরন |
| **Attendance → Leave Types, Holidays, Devices** | Attendance, HRM | ছুটি, ছুটির দিন, biometric |
| **Accounting → Account Settings** | Accounts, VAT | হিসাবের নিয়ম, COA লিংক |
| **Inventory → Purchase Settings, Branch Transfer** | Inventory, Accounts | ক্রয় ওয়ার্কফ্লো, ব্রাঞ্চ ট্রান্সফার |
| **CRM → Lead Sources, Status, Industries** | CRM | লিড পাইপলাইন |
| **POS → Pos Settings** | POS, Restaurant | কাউন্টার, রসিদ, পেমেন্ট |
| **Ecommerce → Shipping, Payment Gateways** | Ecommerce | ডেলিভারি চার্জ, bKash/Card |
| **Hotel → Booking Settings** | Hotel | বুকিং নিয়ম, চেক-ইন/আউট |
| **Game Zone → Food Counter, Ticket Counter** | Game Zone | কাউন্টার সেটআপ |
| **SMS → Settings** | SMS, Game Zone, CRM | SMS gateway |

**উদাহরণ:** Settings-এ Department না থাকলে HRM-এ কর্মচারী যোগ করা যায় না → Attendance-এ সেই কর্মচারী দেখা যায় না → Payroll-এ বেতন হিসাব হয় না।

---

## ৩. শেয়ারড ডেটা — কোন তথ্য কোথায় ব্যবহার হয়

### ৩.১ পণ্য (Products) — Inventory কেন্দ্রিক

Inventory-তে তৈরি পণ্য **৬টি মডিউলে** একই ডেটা ব্যবহার হয়:

| মডিউল | কীভাবে ব্যবহার করে |
|--------|-------------------|
| **Inventory** | মূল ক্যাটালগ — ক্রয়, স্টক, ট্রান্সফার |
| **POS** | কাউন্টারে বিক্রি, barcode স্ক্যান |
| **Ecommerce** | ওয়েবসাইটে পণ্য দেখানো, অর্ডার |
| **Restaurant** | মেনু আইটেম (খাবার) |
| **Game Zone** | Food Counter-এ খাবার/পণ্য বিক্রি |
| **Accounts** | Invoice/Bill-এ লাইন আইটেম |

**স্টক প্রভাব:**
```
Inventory (মূল স্টক)
    ├── POS বিক্রি          → স্টক কমে
    ├── Ecommerce অর্ডার    → স্টক কমে (confirm হলে)
    ├── Restaurant POS      → স্টক কমে (উপকরণ)
    ├── Game Zone Food      → স্টক কমে
    ├── Branch Transfer     → এক ব্রাঞ্চ কমে, অন্যটি বাড়ে
    ├── Purchase Receipt    → স্টক বাড়ে
    ├── Damage              → স্টক কমে
    └── Production Batch    → কাঁচামাল কমে, তৈরি পণ্য বাড়ে
```

---

### ৩.২ গ্রাহক (Customers) — একাধিক জায়গায়

| মডিউল | গ্রাহক টেবিল/ফিচার | সম্পর্ক |
|--------|-------------------|--------|
| **CRM → Leads** | সম্ভাব্য গ্রাহক | এখনো কিনেনি |
| **CRM → Clients** | নিশ্চিত ক্লায়েন্ট | Lead convert হলে |
| **Accounts → Customers** | হিসাবের গ্রাহক | Invoice, Payment Receive |
| **Accounts → Persons / Contact Persons** | যোগাযোগকারী | B2B যোগাযোগ |
| **POS → Customers** | কাউন্টার গ্রাহক | বাকি/ডিউ ট্র্যাকিং |
| **Ecommerce → Customers** | অনলাইন ক্রেতা | ওয়েব অর্ডার |
| **Parking → Customers** | নিয়মিত পার্কার | মাসিক পার্কিং |
| **Hotel** | গেস্ট (বুকিংয়ে) | Room Booking-এ |
| **Game Zone → Membership** | মেম্বার | প্যাকেজ ক্রয় |

**গ্রাহক যাত্রার প্রবাহ:**
```
Facebook/Website
      ↓
  CRM (Lead) ──convert──▶ CRM (Client)
                              ↓
                    Accounts (Customer)
                              ↓
              ┌───────────────┼───────────────┐
              ↓               ↓               ↓
         Invoice         POS Sale      Ecommerce Order
```

---

### ৩.৩ কর্মচারী (Employees) — HRM কেন্দ্রিক

| মডিউল | সম্পর্ক |
|--------|---------|
| **HRM** | মূল কর্মচারী রেকর্ড (নাম, NID, বিভাগ, পদবী) |
| **Attendance** | HRM-এর কর্মচারীদের উপস্থিতি |
| **Payroll** | HRM-এর কর্মচারীদের বেতন |
| **HRM → Leave Applications** | HRM + Attendance Settings (Leave Types) |
| **POS → Salesman Report** | কোন কর্মচারী কত বিক্রি করেছে |
| **CRM → Tasks** | কর্মচারীকে টাস্ক assign |
| **Projects → Tasks** | প্রজেক্টে কর্মচারী assign |
| **Accounts → Expenses** | কর্মচারী-সম্পর্কিত খরচ |

---

### ৩.৪ সাপ্লায়ার/ভেন্ডর (Vendors)

| মডিউল | সম্পর্ক |
|--------|---------|
| **Accounts → Vendors** | মূল ভেন্ডর তালিকা |
| **Inventory → Purchase** | Purchase Order-এ সাপ্লায়ার |
| **Accounts → Bills, Payments Made** | ভেন্ডর বিল ও পেমেন্ট |
| **Inventory → Manufacturers** | পণ্য প্রস্তুতকারক (আলাদা টেবিল) |

---

### ৩.৫ কুপন/অফার (Coupons & Offers)

| উৎস | ব্যবহার |
|-----|---------|
| **Inventory → Coupons** | POS, Ecommerce-এ ডিসকাউন্ট |
| **Game Zone → Coupon** | Game Zone বিক্রিতে |
| **Ecommerce → Offers** | ওয়েবসাইট প্রমোশন |

---

### ৩.৬ ট্যাক্স ও VAT

| উৎস | ব্যবহার |
|-----|---------|
| **Inventory → Tax Rates** | পণ্যের উপর ট্যাক্স |
| **Accounts → Tax Settings** | বিক্রি/ক্রয় ট্যাক্স নিয়ম |
| **VAT → Transaction** | সব বিক্রি/ক্রয়ের VAT entry |
| **POS, Accounts, Ecommerce** | বিক্রিতে VAT অটো ক্যালকুলেট → VAT মডিউলে |

---

## ৪. মডিউল সম্পর্ক ম্যাট্রিক্স

নিচের টেবিলে **✅ = সরাসরি সম্পর্ক**, **🔗 = পরোক্ষ সম্পর্ক**, **— = সরাসরি নেই**

|  | HRM | Att | Pay | Inv | Acc | CRM | POS | GZ | Hotel | Ecom | Rest | CW | Park | SMS | VAT | Email | Proj |
|--|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **HRM** | — | ✅ | ✅ | — | 🔗 | 🔗 | 🔗 | — | — | — | — | — | — | — | — | — | ✅ |
| **Attendance** | ✅ | — | ✅ | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| **Payroll** | ✅ | ✅ | — | — | ✅ | — | — | — | — | — | — | — | — | — | — | — | — |
| **Inventory** | — | — | — | — | ✅ | — | ✅ | 🔗 | 🔗 | ✅ | ✅ | — | — | — | ✅ | — | — |
| **Accounts** | 🔗 | — | ✅ | ✅ | — | ✅ | 🔗 | 🔗 | ✅ | ✅ | 🔗 | 🔗 | 🔗 | — | ✅ | 🔗 | ✅ |
| **CRM** | 🔗 | — | — | — | ✅ | — | — | — | 🔗 | 🔗 | — | — | — | ✅ | — | ✅ | ✅ |
| **POS** | 🔗 | — | — | ✅ | 🔗 | — | — | — | — | — | ✅ | — | — | — | ✅ | — | — |
| **Game Zone** | — | — | — | 🔗 | 🔗 | — | — | — | — | — | — | — | — | ✅ | 🔗 | — | — |
| **Hotel** | — | — | — | 🔗 | ✅ | 🔗 | — | — | — | — | 🔗 | — | — | — | ✅ | 🔗 | — |
| **Ecommerce** | — | — | — | ✅ | ✅ | 🔗 | — | — | — | — | — | — | — | 🔗 | ✅ | ✅ | — |
| **Restaurant** | — | — | — | ✅ | 🔗 | — | ✅ | — | 🔗 | — | — | — | — | — | 🔗 | — | — |
| **Car Wash** | — | — | — | — | 🔗 | 🔗 | — | — | — | — | — | — | — | — | — | — | — |
| **Parking** | — | — | — | — | 🔗 | — | — | — | — | — | — | — | — | — | — | — | — |
| **SMS** | — | — | — | — | — | ✅ | — | ✅ | — | 🔗 | — | — | — | — | — | — | — |
| **VAT** | — | — | — | ✅ | ✅ | — | ✅ | 🔗 | ✅ | ✅ | 🔗 | — | — | — | — | — | — |
| **Emails** | — | — | — | — | — | ✅ | — | — | 🔗 | ✅ | — | — | — | — | — | — | — |
| **Projects** | ✅ | — | — | — | ✅ | ✅ | — | — | — | — | — | — | — | — | — | — | — |

**সংক্ষিপ্ত:**
- **সবচেয়ে বেশি সম্পর্ক:** Inventory (৮+), Accounts (৮+), Settings (সব)
- **সবচেয়ে কম সম্পর্ক:** Parking, Car Wash (মূলত স্বতন্ত্র, শুধু Accounts-এ আয়)

---

## ৫. প্রতিটি মডিউলের সম্পর্ক (এক থেকে অনেক)

### HRM ↔ অন্যান্য

| যায় | আসে |
|-----|-----|
| → **Attendance:** কর্মচারী ID, বিভাগ, শিফট | ← **Settings:** Department, Designation, Shift |
| → **Payroll:** কর্মচারী, বেতন কাঠামো | ← **Settings:** Emp Categories, Job Types |
| → **Projects:** টাস্কে assign | ← **Attendance:** Leave Applications (ছুটি) |
| → **CRM:** Tasks assign | |
| → **POS:** Salesman (বিক্রয়কর্মী) | |

---

### Inventory ↔ অন্যান্য

| যায় | আসে |
|-----|-----|
| → **POS:** পণ্য, দাম, স্টক, barcode | ← **Settings:** Units, Tax Rates, Purchase Settings |
| → **Ecommerce:** পণ্য ক্যাটালগ | ← **Accounts:** Purchase Order/Bill (ক্রয়) |
| → **Restaurant:** মেনু/উপকরণ | |
| → **Game Zone:** Food Counter পণ্য | |
| → **Accounts:** Invoice লাইন আইটেম, Bill | |
| → **VAT:** পণ্য ট্যাক্স রেট | |
| ← **POS/Ecommerce/Restaurant:** বিক্রিতে স্টক কাটা | |
| ← **Accounts:** Purchase থেকে স্টক বাড়া | |

**Inventory Purchase ↔ Accounts Purchase পার্থক্য:**

| Inventory Purchase | Accounts Purchase |
|-------------------|-------------------|
| Requisition → Order → Receipt | Purchase Order → Bill |
| **ফিজিক্যাল স্টক** বাড়ে | **আর্থিক দায়** রেকর্ড |
| গুদামে মাল এলো | সাপ্লায়ারকে টাকা দিতে হবে |
| দুটো একসাথে লিংক হতে পারে | Payments Made দিয়ে টাকা দেওয়া |

---

### Accounts ↔ অন্যান্য

Accounts হলো **আর্থিক কেন্দ্র** — সব মডিউল থেকে টাকার প্রবাহ এখানে:

| উৎস মডিউল | Accounts-এ কী হয় |
|-----------|------------------|
| **POS** | Sales → Daily Income; Due → Receivable |
| **Ecommerce** | Order → Invoice → Payment Receive |
| **CRM → Client** | Customer → Invoice |
| **Inventory Purchase** | Bill → Payments Made |
| **Payroll** | Salary → Expense/Journal |
| **Hotel** | Room Booking → Invoice |
| **Game Zone** | Ticket/Membership → Income |
| **Car Wash / Parking** | Service Fee → Income |
| **VAT** | VAT Transaction → Journal |
| **Projects** | Project-wise Invoice/Expense |

**Accounts-এর অভ্যন্তরীণ সম্পর্ক:**
```
Customers ──▶ Sale Orders ──▶ Invoices ──▶ Payment Receives
                                    ↓
                              Credit Notes (ফেরত)

Vendors ──▶ Purchase Orders ──▶ Bills ──▶ Payments Made
                                    ↓
                              Vendor Credits

Chart of Accounts ◀── Journals ◀── Journal Templates
                         ▲
              Recurring Journals (স্বয়ংক্রিয়)
```

---

### POS ↔ অন্যান্য

| সম্পর্ক | বিস্তারিত |
|---------|----------|
| **Inventory** | পণ্য ও স্টক সরাসরি; বিক্রিতে স্টক অটো কাটে |
| **Accounts** | ফর্মাল Invoice না, কিন্তু Daily Income Report; Due Collection → Receivable |
| **Restaurant** | একই POS ইঞ্জিন, রেস্টুরেন্ট মোড |
| **VAT** | বিক্রিতে VAT ক্যালকুলেট |
| **Inventory → Coupons** | POS-এ কুপন প্রয়োগ |
| **HRM** | Salesman Report-এ কর্মচারী |
| **CRM** | POS Customer ↔ CRM Client (ম্যানুয়াল লিংক সম্ভব) |

**POS vs Accounts — কখন কোনটা:**

| পরিস্থিতি | ব্যবহার করুন |
|-----------|-------------|
| দোকানে দ্রুত বিক্রি, ক্যাশ/কার্ড | **POS** |
| কোম্পানিকে Invoice পাঠাতে হবে | **Accounts → Invoices** |
| গ্রাহকের বাকি টাকা ট্র্যাক | **POS → Due** অথবা **Accounts → Payment Receives** |
| মাসিক হিসাব, Audit | **Accounts → Reports** |
| দৈনিক কাউন্টার বিক্রি দেখা | **POS → Sales Report** |

---

### CRM ↔ অন্যান্য

| সম্পর্ক | বিস্তারিত |
|---------|----------|
| **Accounts** | Lead → Client → Customer → Invoice (পূর্ণ বিক্রয় চক্র) |
| **Emails** | Campaign, Marketing email পাঠানো |
| **SMS** | Promotional SMS, Lead follow-up |
| **Ecommerce** | Online lead → CRM Lead |
| **Projects** | Client-এর প্রজেক্ট |
| **HRM** | Tasks-এ কর্মচারী assign |
| **Hotel** | গেস্ট/ক্লায়েন্ট তথ্য |

**CRM পাইপলাইন ও অন্য মডিউল:**
```
Lead (CRM)
  │ Meeting, Task (CRM)
  │ Email/SMS (Emails, SMS)
  ▼
Client (CRM)
  ▼
Customer (Accounts) ──▶ Quoto ──▶ Sale Order ──▶ Invoice
  │
  └──▶ Project (Projects) ──▶ Project Invoice (Accounts)
```

---

### Game Zone ↔ অন্যান্য

| সম্পর্ক | বিস্তারিত |
|---------|----------|
| **Inventory** | Food Counter-এ খাবার/পণ্য (Inventory Products) |
| **SMS** | Member SMS, Promotional SMS |
| **Accounts** | Ticket/Membership আয়, Expenses |
| **Inventory → Coupons** | Game Zone Coupon |
| **Settings** | Food Counter, Ticket Counter সেটআপ |
| **VAT** | বিক্রিতে VAT |

---

### Hotel ↔ অন্যান্য

| সম্পর্ক | বিস্তারিত |
|---------|----------|
| **Accounts** | Room Booking বিল, Payment |
| **Restaurant** | Room Service-এ খাবার অর্ডার |
| **Inventory** | Room Service/upkeep সরবরাহ |
| **CRM** | গেস্ট প্রোফাইল, repeat guest |
| **Emails** | Booking confirmation |
| **VAT** | Room charge-এ VAT |
| **Settings** | Booking Settings |

---

### Ecommerce ↔ অন্যান্য

| সম্পর্ক | বিস্তারিত |
|---------|----------|
| **Inventory** | পণ্য, স্টক, দাম — সরাসরি |
| **Accounts** | Order → Invoice, Payment Gateway payment |
| **Emails** | Order confirm, shipping update |
| **SMS** | Order notification (ঐচ্ছিক) |
| **CRM** | Online customer → Lead/Client |
| **VAT** | অনলাইন বিক্রিতে VAT |
| **Inventory → Coupons** | Checkout-এ কুপন |
| **Settings** | Shipping Charges, Payment Gateways |

**Ecommerce অর্ডার প্রবাহ:**
```
ওয়েবসাইট অর্ডার (Ecommerce)
        ↓
Inventory স্টক চেক ও কাটা
        ↓
Accounts Invoice/Payment (Payment Gateway)
        ↓
Emails → Order Confirmation
        ↓
VAT Transaction
```

---

### Payroll ↔ Accounts

| ঘটনা | Accounts-এ প্রভাব |
|------|-------------------|
| Salary Sheet approve | Expense entry (বেতন খরচ) |
| Advance দেওয়া | Employee advance (Receivable) |
| Loan installment কাটা | Loan recovery |
| PF/Tax কাটা | Liability account |

```
Payroll (Salary Sheet)
        ↓
Accounts (Journal/Expense)
        ↓
Banks (বেতন ট্রান্সফার)
```

---

## ৬. আর্থিক প্রবাহ — টাকা কোথা থেকে কোথায়

### আয় (Income) এর উৎস

| মডিউল | Accounts-এ কীভাবে যায় |
|--------|----------------------|
| POS | Daily Sales, Payment Receive |
| Ecommerce | Order Payment → Invoice |
| Accounts (সরাসরি) | Invoice → Payment Receive |
| Hotel | Room Bill |
| Game Zone | Ticket, Membership |
| Car Wash | Service Fee |
| Parking | Parking Fee |
| Restaurant | POS Sales |

### ব্যয় (Expense) এর উৎস

| মডিউল | Accounts-এ কীভাবে যায় |
|--------|----------------------|
| Inventory Purchase | Bill → Payments Made |
| Payroll | Salary Expense |
| Game Zone / Car Wash | Expenses |
| Accounts (সরাসরি) | Expenses, Recurring Expenses |
| Hotel | Maintenance, supplies |

### সম্পূর্ণ আর্থিক চক্র

```
                    ┌──────────────┐
    Income ────────▶│   Accounts   │◀──────── Expense
    (বিক্রি)        │              │         (ক্রয়/বেতন)
                    │  Journal     │
                    │  COA         │
                    │  Banks       │
                    └──────┬───────┘
                           │
                    ┌──────▼───────┐
                    │     VAT      │
                    │  Transaction │
                    │  Reports     │
                    └──────────────┘
```

---

## ৭. স্টক প্রবাহ — পণ্য কোথা থেকে কোথায়

```
                    ┌─────────────────┐
                    │    Inventory    │
                    │  (মূল স্টক)     │
                    └────────┬────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
   Purchase ↑           Transfer ↔           Sales ↓
        │                    │                    │
   ┌────▼────┐         ┌─────▼─────┐       ┌─────▼─────┐
   │ Vendor  │         │ Branch A  │       │    POS    │
   │ Receipt │         │ Branch B  │       │ Ecommerce │
   └─────────┘         └───────────┘       │ Restaurant│
                                           │ Game Zone │
                                           │  (Food)   │
                                           └───────────┘
        ↑
   Production Batch
   (কাঁচামাল → তৈরি পণ্য)
```

---

## ৮. মানবসম্পদ শৃঙ্খল (HRM Chain)

সবচেয়ে **সোজা ও গভীর** সম্পর্ক এই চার মডিউলে:

```
Settings (HRM + Attendance + Payroll Setup)
                    │
                    ▼
              ┌──────────┐
              │   HRM    │  কর্মচারী যোগ, Leave Policy
              └────┬─────┘
                   │ কর্মচারী ডেটা
                   ▼
              ┌──────────────┐
              │  Attendance  │  Biometric, উপস্থিতি, ছুটি
              └────┬─────────┘
                   │ উপস্থিতি ডেটা (অনুপস্থিত = LWP)
                   ▼
              ┌──────────┐
              │ Payroll  │  বেতন, Advance, Loan
              └────┬─────┘
                   │ বেতন খরচ
                   ▼
              ┌──────────┐
              │ Accounts │  Expense, Journal, Bank Payment
              └──────────┘
```

**প্রতিটি ধাপে কী ডেটা যায়:**

| থেকে | যায় | ডেটা |
|------|------|------|
| Settings | HRM | Department, Designation, Shift |
| HRM | Attendance | Employee ID, Name, Department |
| Settings | Attendance | Leave Types, Holidays, Devices |
| HRM | Payroll | Employee, Salary Design |
| Attendance | Payroll | Present/Absent days, LWP |
| Payroll | Accounts | Net Salary, Deductions, Advance recovery |

---

## ৯. গ্রাহক যাত্রা (Customer Journey)

একজন গ্রাহক **বিভিন্ন মডিউল দিয়ে** কীভাবে যায়:

### পথ ১ — B2B বিক্রয় (CRM → Accounts)

```
Facebook Ad
    → CRM Lead (source: Facebook)
    → Meeting (CRM)
    → Email Follow-up (Emails)
    → Client (CRM) — convert
    → Customer (Accounts)
    → Quoto (Accounts)
    → Sale Order (Accounts)
    → Invoice (Accounts)
    → Payment Receive (Accounts)
    → VAT Transaction
```

### পথ ২ — খুচরা দোকান (POS)

```
দোকানে আসা
    → POS Sale (Inventory স্টক কাটে)
    → Payment (Cash/Card)
    → Sales Report (POS)
    → VAT (অটো)
    → (ঐচ্ছিক) Accounts Daily Income
```

### পথ ৩ — অনলাইন (Ecommerce)

```
ওয়েবসাইট ভিজিট
    → পণ্য দেখা (Inventory Products)
    → Cart → Checkout
    → Payment Gateway (Settings)
    → Order (Ecommerce)
    → Email Confirmation (Emails)
    → Inventory স্টক কাটা
    → Accounts Invoice
    → VAT
```

### পথ ৪ — Game Zone মেম্বার

```
টিকিট কাউন্টার (Game Zone)
    → Membership Package ক্রয়
    → Membership (Game Zone)
    → Member SMS (SMS)
    → Purchase History
    → Food Counter (Inventory পণ্য)
    → Accounts Income
```

---

## ১০. যোগাযোগ শৃঙ্খল — SMS ও Emails

SMS ও Emails **সহায়ক মডিউল** — অন্য মডিউল থেকে ট্রিগার হয়:

| ট্রিগার মডিউল | SMS | Emails |
|---------------|-----|--------|
| **CRM** | Lead follow-up, Promotional | Campaign, Meeting invite |
| **Ecommerce** | Order SMS (ঐচ্ছিক) | Order confirm, Shipping |
| **Game Zone** | Member SMS, Promotional | — |
| **Hotel** | — | Booking confirmation |
| **Payroll** | — | Payslip (ঐচ্ছিক) |
| **Accounts** | Payment reminder (ঐচ্ছিক) | Invoice email |
| **HRM** | — | Leave approval |

```
┌─────────┐     ┌─────────┐     ┌─────────┐
│   CRM   │────▶│   SMS   │     │  Emails │
│ Ecommerce│────▶│ Module  │     │  Module │
│Game Zone│────▶│         │     │         │
└─────────┘     └─────────┘     └─────────┘
                     ▲               ▲
                     │               │
              Settings (Gateway)  Settings (Domain)
```

---

## ১১. ব্রাঞ্চ ও মাল্টি-লোকেশন

ERP17 **মাল্টি-ব্রাঞ্চ** সাপোর্ট করে (যেমন: halishahar, Dhaka two, Hacker)।

| বিষয় | ব্রাঞ্চ প্রভাব |
|-------|---------------|
| **Settings → Branches** | সব মডিউলে ব্রাঞ্চ সিলেক্টর |
| **HRM** | কর্মচারী কোন ব্রাঞ্চে |
| **Attendance** | ব্রাঞ্চ অনুযায়ী উপস্থিতি |
| **Payroll** | ব্রাঞ্চ অনুযায়ী বেতন |
| **Inventory** | ব্রাঞ্চভিত্তিক স্টক, Branch Transfer |
| **POS** | ব্রাঞ্চভিত্তিক বিক্রি |
| **Accounts** | ব্রাঞ্চভিত্তিক হিসাব (consolidated report সম্ভব) |
| **HRM Dashboard** | Branch filter: All branches / single branch |

**Branch Transfer প্রবাহ:**
```
Branch A (Inventory Stock: 100)
        │
        │ Branch Transfer
        ▼
Branch B (Inventory Stock: +50)
Branch A (Inventory Stock: 50)
```

---

## ১২. সম্মিলিত ব্যবসায়িক সিনারিও

### সিনারিও ১ — খুচরা + অনলাইন + অফিস (সব মিলিয়ে)

একটি কোম্পানি যার দোকান, ওয়েবসাইট ও অফিস আছে:

```
[সেটআপ]
Settings → Org, Branches, Users, Roles
Settings → HRM (Department), Inventory (Units, Tax)
Inventory → Products যোগ

[দৈনন্দিন]
সকাল: Attendance আপলোড (HRM কর্মচারী)
       POS চালু (Inventory পণ্য)
       
দিন:   POS বিক্রি (স্টক কমে, VAT)
       Ecommerce অর্ডার (স্টক কমে, Email পাঠায়)
       CRM Lead follow-up (Email/SMS)

সন্ধ্যা: POS Sales Report
         Ecommerce Orders process

[মাস শেষ]
Payroll → Salary Sheet (Attendance ডেটা)
Accounts → Financial Reports
VAT → Monthly Report
```

**জড়িত মডিউল:** Settings, HRM, Attendance, Inventory, POS, Ecommerce, CRM, Emails, Payroll, Accounts, VAT = **১১টি**

---

### সিনারিও ২ — হোটেল + রেস্টুরেন্ট + ইনভেন্টরি

```
[সেটআপ]
Hotel → Rooms, Room Plans, Floors
Restaurant → POS (Restaurant mode)
Inventory → খাবার উপকরণ, Room supplies
Settings → Hotel Booking Settings

[অপারেশন]
গেস্ট Room Booking (Hotel)
    → Check-in
    → Room Service অর্ডার (Restaurant POS → Inventory কাটে)
    → Check-out → Bill (Accounts Invoice)
    → VAT

রেস্টুরেন্ট walk-in:
    → Restaurant POS → Inventory স্টক কাটে → Accounts
```

**জড়িত মডিউল:** Hotel, Restaurant, Inventory, POS, Accounts, VAT, Settings = **৭টি**

---

### সিনারিও ৩ — Game Zone + SMS + Inventory Food

```
[সেটআপ]
Game Zone → Membership Package, Policy
Settings → Ticket Counter, Food Counter
Inventory → Food/Drink Products
SMS → Gateway setup

[অপারেশন]
টিকিট বিক্রি (Game Zone Ticket Counter)
মেম্বারশিপ (Game Zone → SMS Member notification)
Food Counter বিক্রি (Inventory Products → স্টক কাটে)
Denomination Count (ক্যাশ)
Sales Report (Game Zone)
Expense (Game Zone → Accounts)
```

**জড়িত মডিউল:** Game Zone, Inventory, SMS, Accounts, VAT, Settings = **৬টি**

---

### সিনারিও ৪ — B2B সার্ভিস কোম্পানি (CRM + Projects + Accounts)

```
CRM Lead (Website)
    → Meeting, Tasks
    → Client convert
    → Project তৈরি (Projects)
    → Project Tasks (HRM কর্মচারী assign)
    → Milestone Invoice (Accounts)
    → Payment Receive
    → Email Invoice (Emails)
    → VAT
```

**জড়িত মডিউল:** CRM, Projects, HRM, Accounts, Emails, VAT = **৬টি**

---

## ১৩. নির্ভরতা তালিকা — কোনটা আগে সেটআপ করতে হবে

সঠিক ক্রমে সেটআপ না করলে পরের মডিউল কাজ করবে না:

### Level 1 — প্রথমে (অবশ্যই)
```
1. Settings → Organization, Company, Branches
2. Settings → Users, Roles
3. Settings → HRM (Department, Designation)
4. Settings → Inventory (Units, Categories, Tax Rates)
5. Settings → Accounting (Account Settings, Chart of Accounts)
```

### Level 2 — মাস্টার ডেটা
```
6. HRM → Employees
7. Inventory → Products, Warehouses
8. Accounts → Customers, Vendors, Banks
9. Settings → Attendance (Leave Types, Holidays)
10. Settings → Payroll (Pay Scales, Payment Types)
```

### Level 3 — অপারেশনাল মডিউল
```
11. Attendance (কর্মচারী থাকলে)
12. Payroll (HRM + Attendance থাকলে)
13. POS / Ecommerce / Hotel / Game Zone (Products থাকলে)
14. CRM (Customers/Leads)
```

### Level 4 — সহায়ক
```
15. SMS, Emails (Gateway/Domain setup)
16. VAT (Accounts + Sales চালু হলে)
17. Projects (CRM Clients থাকলে)
```

### নির্ভরতা ডায়াগ্রাম

```
Settings (L1)
    ├── HRM (L2) ──▶ Attendance (L3) ──▶ Payroll (L3) ──▶ Accounts
    ├── Inventory (L2) ──▶ POS / Ecommerce / Restaurant (L3)
    ├── Accounts setup (L2) ──▶ VAT (L4)
    └── CRM setup (L2) ──▶ CRM (L3) ──▶ Projects (L4)

Inventory + Accounts ──▶ সব বিক্রয় মডিউল
SMS/Emails Settings ──▶ যোগাযোগ ফিচার
```

---

## দ্রুত রেফারেন্স — কোন মডিউল কার সাথে সবচেয়ে বেশি জড়িত

| মডিউল | সরাসরি সম্পর্কিত মডিউল (সংখ্যা) | মূল ভূমিকা |
|--------|-------------------------------|------------|
| **Settings** | ১৭ (সব) | ভিত্তি/মাস্টার ডেটা |
| **Inventory** | ৮+ | পণ্য ও স্টক কেন্দ্র |
| **Accounts** | ১০+ | আর্থিক কেন্দ্র |
| **HRM** | ৫ | কর্মচারী কেন্দ্র |
| **CRM** | ৬ | গ্রাহক সম্পর্ক কেন্দ্র |
| **POS** | ৫ | খুচরা বিক্রি |
| **VAT** | ৬ | কর হিসাব (সব বিক্রি থেকে) |
| **Emails/SMS** | ৫+ | যোগাযোগ (সব মডিউলে) |
| **Parking/Car Wash** | ১–২ | তুলনামূলক স্বতন্ত্র |

---

> **পূর্ববর্তী ডক:** [ERP17-Kivabe-Kaj-Kore.md](./ERP17-Kivabe-Kaj-Kore.md) — প্রতিটি মডিউল কীভাবে কাজ করে
> **Feature তালিকা:** [ERP17-Features-Documentation.md](./ERP17-Features-Documentation.md)

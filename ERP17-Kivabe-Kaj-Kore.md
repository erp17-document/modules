# ERP17 — প্রতিটি মডিউল কীভাবে কাজ করে (বাংলা গাইড)

> এই ডকুমেন্টে ERP17-এর প্রতিটি মডিউলের **কাজ কী**, **কীভাবে চলে** এবং **অন্য মডিউলের সাথে কীভাবে যুক্ত** — সব বাংলায় ব্যাখ্যা করা হয়েছে।

---

## সূচিপত্র

1. [HRM (মানবসম্পদ)](#1-hrm-মানবসম্পদ)
2. [Attendance (উপস্থিতি)](#2-attendance-উপস্থিতি)
3. [Payroll (বেতন)](#3-payroll-বেতন)
4. [Inventory (ইনভেন্টরি/স্টক)](#4-inventory-ইনভেন্টরিস্টক)
5. [Accounts (হিসাব/অ্যাকাউন্টিং)](#5-accounts-হিসাবঅ্যাকাউন্টিং)
6. [CRM (গ্রাহক সম্পর্ক)](#6-crm-গ্রাহক-সম্পর্ক)
7. [POS (পয়েন্ট অফ সেল)](#7-pos-পয়েন্ট-অফ-সেল)
8. [Game Zone (গেম জোন)](#8-game-zone-গেম-জোন)
9. [Hotel (হোটেল)](#9-hotel-হোটেল)
10. [Ecommerce (অনলাইন দোকান)](#10-ecommerce-অনলাইন-দোকান)
11. [Restaurant (রেস্টুরেন্ট)](#11-restaurant-রেস্টুরেন্ট)
12. [Car Wash (গাড়ি ধোয়া)](#12-car-wash-গাড়ি-ধোয়া)
13. [Parking (পার্কিং)](#13-parking-পার্কিং)
14. [SMS](#14-sms)
15. [VAT (ভ্যাট)](#15-vat-ভ্যাট)
16. [Emails (ইমেইল)](#16-emails-ইমেইল)
17. [Projects (প্রজেক্ট)](#17-projects-প্রজেক্ট)
18. [মডিউলগুলোর মধ্যে সম্পর্ক](#মডিউলগুলোর-মধ্যে-সম্পর্ক)

---

## 1. HRM (মানবসম্পদ)

### এই মডিউল কী করে?

কোম্পানির **সকল কর্মচারীর তথ্য** এক জায়গায় রাখে। নতুন কর্মী যোগ করা, তাদের বিভাগ/পদবী সেট করা, ছুটির আবেদন দেখা — এসব HRM-এর কাজ।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ (Settings থেকে, একবার):**
- Settings → HRM-এ গিয়ে Department, Designation, Division, Job Type, Working Shift ইত্যাদি তৈরি করতে হয়।
- এগুলো ছাড়া কর্মচারী যোগ করা সম্ভব নয়।

**ধাপ ২ — কর্মচারী যোগ:**
- HRM → Employees → **New** ক্লিক করুন।
- নাম, ফোন, NID, বিভাগ, পদবী, যোগদানের তারিখ ইত্যাদি পূরণ করুন।
- সেভ করলে কর্মচারী তালিকায় চলে আসে। Active/Inactive স্ট্যাটাস দিয়ে চাকরিতে আছে কি না দেখা যায়।

**ধাপ ৩ — ছুটির আবেদন:**
- কর্মচারী বা HR → Leave Applications-এ গিয়ে ছুটির আবেদন দেয়।
- ম্যানেজার/HR অনুমোদন বা প্রত্যাখ্যান করতে পারে।

**ধাপ ৪ — Leave Policy Group:**
- Employee Leave Policy Groups-এ বিভিন্ন গ্রুপের জন্য ছুটির নিয়ম (কত দিন ছুটি, কোন ধরনের) সেট করা হয়।
- কর্মচারীকে গ্রুপে বসালে সেই নিয়ম প্রযোজ্য হয়।

**ধাপ ৫ — Dashboard:**
- HRM Dashboard-এ মোট কর্মচারী, সক্রিয় কর্মচারী, নতুন যোগদান, বিভাগভিত্তিক সংখ্যা, Join/Exit Trend চার্ট দেখা যায়।

### অন্য মডিউলের সাথে সম্পর্ক:
- **Attendance** → HRM-এর কর্মচারীদের উপস্থিতি ট্র্যাক করে
- **Payroll** → HRM-এর কর্মচারীদের বেতন হিসাব করে
- **Settings** → HRM-এর মাস্টার ডেটা (Department, Designation) সেটআপ

---

## 2. Attendance (উপস্থিতি)

### এই মডিউল কী করে?

কর্মচারীর **দৈনিক উপস্থিতি** (কখন এলো, কখন গেলো) রেকর্ড করে। Biometric মেশিন থেকে ডেটা আপলোড করা যায়।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ (Settings থেকে):**
- Leave Types, Holidays, Attendance Devices, Absent Settings, LWP Settings সেট করতে হয়।
- Biometric ডিভাইস কানেক্ট করলে Attendance Devices-এ যোগ করুন।

**ধাপ ২ — উপস্থিতি আপলোড:**
- Attendance → Attendance পেজে যান।
- **In File** ও **Out File** — biometric মেশিন থেকে export করা ফাইল আপলোড করুন।
- **Download Sample** দিয়ে সঠিক ফরম্যাট দেখে নিতে পারেন।

**ধাপ ৩ — রিপোর্ট দেখা:**
- From Date ও To Date সিলেক্ট করুন, Department ফিল্টার দিন, **Search** করুন।
- তারিখ অনুযায়ী কে উপস্থিত ছিল, কে অনুপস্থিত — তালিকা দেখাবে।

**ধাপ ৪ — Attendance Reports:**
- মাসিক/সাপ্তাহিক সারাংশ, বিভাগভিত্তি রিপোর্ট, late/absent রিপোর্ট ইত্যাদি এখান থেকে বের করা যায়।

### অন্য মডিউলের সাথে সম্পর্ক:
- **HRM** → কর্মচারী তালিকা এখান থেকে আসে
- **Payroll** → উপস্থিতি ডেটা বেতন কাটা/যোগ করতে ব্যবহার হয় (অনুপস্থিতি = LWP কাটা)

---

## 3. Payroll (বেতন)

### এই মডিউল কী করে?

কর্মচারীদের **মাসিক বেতন** হিসাব, প্রদান ও ট্র্যাক করে। অগ্রিম বেতন, ঋণ, ভাতা-কাটা — সব এখানে।

### কীভাবে কাজ করে?

**ধাপ ১ — বেতন কাঠামো তৈরি:**
- **Salary Heads** → বেতনের অংশগুলো define করুন (যেমন: Basic, House Rent, Medical, PF, Tax)।
- **Salary Designs** → একজন কর্মচারীর বেতন কাঠামো (কোন head-এ কত টাকা) সেট করুন।
- **Pay Scales** → গ্রেড/স্কেল অনুযায়ী বেতনের পরিমাণ নির্ধারণ করুন।

**ধাপ ২ — অগ্রিম ও ঋণ:**
- **Advances** → কর্মচারী অগ্রিম বেতন নিলে এখানে রেকর্ড করুন। পরের বেতন থেকে কাটা হবে।
- **Loans** → দীর্ঘমেয়াদি ঋণ দিলে installment সহ এখানে ট্র্যাক করুন।

**ধাপ ৩ — মাসিক বেতন শিট:**
- **Salary Sheet Settings** → বেতন শিট কীভাবে generate হবে সেট করুন।
- **Salary Sheets** → মাস সিলেক্ট করে বেতন শিট generate করুন।
- Attendance ডেটা অনুযায়ী অনুপস্থিতি কাটা, advance/loan কাটা স্বয়ংক্রিয়ভাবে হতে পারে।

**ধাপ ৪ — বেতন প্রদান:**
- Generate হওয়া শিট approve করে বেতন প্রদানের প্রসেস সম্পন্ন করুন।

### অন্য মডিউলের সাথে সম্পর্ক:
- **HRM** → কর্মচারী ও বেতন কাঠামো
- **Attendance** → উপস্থিতি অনুযায়ী কাটা-পুরি
- **Accounts** → বেতন প্রদান হলে Accounts-এ expense/journal entry হতে পারে

---

## 4. Inventory (ইনভেন্টরি/স্টক)

### এই মডিউল কী করে?

পণ্যের **কেনা, বিক্রি, স্টক, গুদাম** — সব ট্র্যাক করে। দোকান, ফ্যাক্টরি, যেকোনো পণ্য-ভিত্তিক ব্যবসার মূল ভিত্তি।

### কীভাবে কাজ করে?

**ধাপ ১ — মাস্টার সেটআপ:**
- Settings-এ Unit, Category, Tax Rate, Manufacturer, Payment Terms সেট করুন।
- **Warehouses** → গুদাম/স্টোর তৈরি করুন (যেমন: Main Store, Branch Store)।

**ধাপ ২ — পণ্য যোগ:**
- Products → **New** → পণ্যের নাম, SKU, ক্যাটাগরি, ইউনিট, ক্রয়মূল্য, বিক্রয়মূল্য, barcode দিন।
- **Generate Barcode** দিয়ে একসাথে অনেক পণ্যের barcode তৈরি করুন।

**ধাপ ৩ — ক্রয় (Purchase) প্রসেস:**
```
Requisition (চাহিদা) → Order (অর্ডার) → Receipt (মাল আসল) → Return (ফেরত, যদি দরকার)
```
1. **Requisition** — বিভাগ/স্টোর থেকে পণ্য চাওয়া
2. **Order** — সাপ্লায়ারকে Purchase Order পাঠানো
3. **Receipt** — মাল এলে গ্রহণ করা, স্টক বাড়ে
4. **Return** — খারাপ/অতিরিক্ত মাল ফেরত

**ধাপ ৪ — স্টক ম্যানেজমেন্ট:**
- **Opening Stock** → নতুন সিস্টেমে শুরুতে স্টক সেট করুন
- **Stock Report** → বর্তমান স্টক দেখুন
- **Branch Transfers** → এক ব্রাঞ্চ থেকে অন্য ব্রাঞ্চে পণ্য পাঠান
- **Damage** → নষ্ট পণ্য রেকর্ড করুন, স্টক কমে

**ধাপ ৫ — উৎপাদন (Production):**
- **Batches** → উৎপাদন ব্যাচ তৈরি (কাঁচামাল → তৈরি পণ্য)
- **Batch Report** → ব্যাচ অনুযায়ী রিপোর্ট

**ধাপ ৬ — কুপন:**
- **Coupons** → ডিসকাউন্ট কুপন তৈরি (POS/Ecommerce-এ ব্যবহার)

### অন্য মডিউলের সাথে সম্পর্ক:
- **POS** → বিক্রি হলে Inventory-র স্টক কমে
- **Ecommerce** → অনলাইন অর্ডারে স্টক কাটে
- **Accounts** → Purchase/Sales-এর হিসাব Accounts-এ যায়
- **VAT** → পণ্যের উপর VAT হিসাব

---

## 5. Accounts (হিসাব/অ্যাকাউন্টিং)

### এই মডিউল কী করে?

ব্যবসার **সম্পূর্ণ আর্থিক হিসাব** রাখে — কে কত টাকা দেবে, কাকে কত দিতে হবে, ব্যাংক, জার্নাল, রিপোর্ট। ERP17-এর সবচেয়ে বড় মডিউল।

### কীভাবে কাজ করে?

#### ক. বিক্রি (Sales) সাইড — টাকা আসা

```
Quote (কোটেশন) → Sale Order (অর্ডার) → Invoice (বিল) → Payment Receive (টাকা নেওয়া)
```

1. **Customers** → গ্রাহকের তথ্য যোগ করুন (নাম, ঠিকানা, ফোন)
2. **Quotos** → গ্রাহককে দামের প্রস্তাব পাঠান
3. **Sale Orders** → গ্রাহক অর্ডার কনফার্ম করলে Sale Order তৈরি
4. **Invoices** → চূড়ান্ত বিল/ইনভয়েস তৈরি — এখানে পণ্য, পরিমাণ, দাম, ট্যাক্স
5. **Payment Receives** → গ্রাহক টাকা দিলে রেকর্ড করুন
6. **Credit Notes** → গ্রাহক ফেরত দিলে বা ছাড় দিলে
7. **Recurring Invoices** → মাসিক/বার্ষিক বারবার বিল (যেমন: সাবস্ক্রিপশন)
8. **Retainer Invoices** → আগে থেকে রিটেইনার ফি

#### খ. ক্রয় (Purchases) সাইড — টাকা যাওয়া

```
Purchase Order → Bill (বিল) → Payment Made (টাকা দেওয়া)
```

1. **Vendors** → সাপ্লায়ার/বিক্রেতার তথ্য
2. **Purchase Orders** → সাপ্লায়ারকে অর্ডার
3. **Bills** → সাপ্লায়ারের বিল রেকর্ড
4. **Payments Made** → সাপ্লায়ারকে টাকা দেওয়া
5. **Expenses** → দৈনন্দিন খরচ (বিদ্যুৎ, ভাড়া, অফিস খরচ)
6. **Recurring Expenses/Bills** → বারবার হওয়া খরচ/বিল
7. **Vendor Credits** → সাপ্লায়ার থেকে ক্রেডিট/ফেরত

#### গ. অ্যাকাউন্ট্যান্ট (হিসাবের মূল)

1. **Chart Of Accounts** → সব অ্যাকাউন্টের তালিকা (Assets, Liabilities, Income, Expense)
2. **Journals** → ম্যানুয়াল হিসাব এন্ট্রি (ডেবিট-ক্রেডিট)
3. **Journal Templates** → বারবার একই ধরনের entry-র টেমপ্লেট
4. **Recurring Journals** → স্বয়ংক্রিয় পুনরাবৃত্ত জার্নাল
5. **Banks** → ব্যাংক অ্যাকাউন্ট ম্যানেজমেন্ট
6. **Reports** → Profit & Loss, Balance Sheet, Cash Flow ইত্যাদি

#### ঘ. সহায়ক
- **Payment Methods** → Cash, Card, Bank Transfer ইত্যাদি
- **Tax Settings** → বিক্রি/ক্রয়ে ট্যাক্স নিয়ম
- **Contact Persons** → যোগাযোগকারী ব্যক্তির তথ্য
- **Projects** → প্রজেক্ট-ভিত্তিক হিসাব

### Accounts vs POS vs Inventory — পার্থক্য:

| বিষয় | Accounts | POS | Inventory |
|-------|----------|-----|-----------|
| উদ্দেশ্য | টাকার হিসাব | দোকানে দ্রুত বিক্রি | পণ্য/স্টক ট্র্যাক |
| গ্রাহক | Invoice, Payment | কাউন্টারে সরাসরি বিক্রি | সরাসরি সম্পর্ক নেই |
| বিল | ফর্মাল Invoice/Bill | Sales Receipt | Purchase Receipt |
| হিসাব | Journal, COA | Daily Income Report | Stock Report |

### অন্য মডিউলের সাথে সম্পর্ক:
- **Inventory** → Purchase/Sales-এর আর্থিক দিক
- **POS** → POS বিক্রির হিসাব এখানে reflect হতে পারে
- **Payroll** → বেতন খরচ expense হিসেবে
- **VAT** → VAT ট্রানজেকশন

---

## 6. CRM (গ্রাহক সম্পর্ক)

### এই মডিউল কী করে?

**নতুন গ্রাহক খোঁজা থেকে বিক্রি পর্যন্ত** পুরো প্রসেস ট্র্যাক করে। Lead → Client → Sale — এই যাত্রা CRM-এর কাজ।

### কীভাবে কাজ করে?

**ধাপ ১ — Lead (সম্ভাব্য গ্রাহক) সংগ্রহ:**
- **Leads** → নতুন lead যোগ করুন (নাম, কোম্পানি, ইমেইল, ফোন, সোর্স)
- **Import** দিয়ে একসাথে অনেক lead আপলোড করুন
- Lead Status: New → On going → Won/Lost
- Settings-এ Lead Sources (Facebook, Website, Referral), Lead Status, Industries, Ratings সেট করুন

**ধাপ ২ — Lead কে Client-এ রূপান্তর:**
- Lead সফল হলে **Clients**-এ convert করুন
- Client-এর সম্পূর্ণ প্রোফাইল, যোগাযোগ ইতিহাস থাকে

**ধাপ ৩ — Follow-up:**
- **Meetings** → ক্লায়েন্টের সাথে মিটিং শিডিউল ও রেকর্ড
- **Tasks** → করণীয় কাজ assign করুন (কল করতে হবে, প্রপোজাল পাঠাতে হবে)
- **Campaigns** → মার্কেটিং ক্যাম্পেইন চালান (ইমেইল, SMS)

**ধাপ ৪ — বিক্রিতে নিয়ে যাওয়া:**
- Client তৈরি হলে **Accounts**-এ Customer হিসেবে Invoice তৈরি করা যায়

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → Client → Customer → Invoice
- **Emails/SMS** → Campaign ও follow-up
- **Ecommerce** → Online গ্রাহক

---

## 7. POS (পয়েন্ট অফ সেল)

### এই মডিউল কী করে?

**দোকান/কাউন্টারে সরাসরি বিক্রি** — পণ্য স্ক্যান, বিল, টাকা নেওয়া, রিসিপ্ট। দ্রুত ও সহজ।

### কীভাবে কাজ করে?

**ধাপ ১ — POS চালু:**
- POS → **Pos** (বা Advance Pos) খুলুন
- Inventory-তে যোগ করা পণ্য এখানে দেখা যায়
- পণ্য সিলেক্ট করুন (বা barcode স্ক্যান), পরিমাণ দিন
- ডিসকাউন্ট, কুপন প্রয়োগ করুন
- পেমেন্ট মেথড সিলেক্ট (Cash/Card/Mobile) → বিল সম্পন্ন

**ধাপ ২ — বিক্রি পরবর্তী:**
- **Sales** → সব বিক্রির তালিকা
- **Returns / New Return** → গ্রাহক পণ্য ফেরত দিলে
- **Customers** → POS গ্রাহক তালিকা
- **Due Collection** → বাকি টাকা আদায়

**ধাপ ৩ — রিপোর্ট:**
- **Sales Report** → দৈনিক/মাসিক বিক্রি
- **Items Wise Sales** → কোন পণ্য কত বিক্রি
- **Stock Report** → POS-এর স্টক
- **Due Report / Customer Due Report** → বাকি টাকা
- **Work Period Report** → শিফট অনুযায়ী বিক্রি
- **Daily Income Expense** → দিনের আয়-ব্যয়
- **Salesman Report** → কোন বিক্রয়কর্মী কত বিক্রি করেছে
- **Sales Payment Report** → Cash/Card অনুযায়ী পেমেন্ট

**ধাপ ৪ — Damage/Loss:**
- নষ্ট পণ্য **Damage Loss**-এ রেকর্ড করুন

### POS vs Accounts — কী পার্থক্য?

| POS | Accounts |
|-----|----------|
| কাউন্টারে তাৎক্ষণিক বিক্রি | অফিসে ফর্মাল হিসাব |
| সহজ, দ্রুত | বিস্তারিত Invoice/Bill |
| খুচরা/পাইকারি দোকান | B2B, সার্ভিস, প্রজেক্ট |
| Sales Receipt | Invoice + Payment Receive |
| স্টক স্বয়ংক্রিয় কাটে | ম্যানুয়াল বা লিংকড entry |

### অন্য মডিউলের সাথে সম্পর্ক:
- **Inventory** → পণ্য ও স্টক এখান থেকে আসে, বিক্রিতে স্টক কমে
- **Accounts** → বিক্রির আর্থিক রেকর্ড (ঐচ্ছিক লিংক)
- **VAT** → বিক্রিতে VAT

---

## 8. Game Zone (গেম জোন)

### এই মডিউল কী করে?

**গেম জোন/অ্যামিউজমেন্ট পার্ক** পরিচালনা — টিকিট বিক্রি, মেম্বারশিপ, গ্রাউন্ড কাউন্টার, খাবার কাউন্টার।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ:**
- **Membership Package** → মেম্বারশিপ প্যাকেজ তৈরি (মাসিক/বার্ষিক, কত টাকা)
- **Policy** → গেম জোনের নিয়ম-কানুন
- Settings → Food Counter, Ticket Counter সেটআপ

**ধাপ ২ — দৈনন্দিন বিক্রি:**
- **Ticket Counter** → টিকিট বিক্রি (একবারের খেলা)
- **Ground Counter** → গ্রাউন্ড/প্লে এরিয়া কাউন্টার
- **Ticket Countdown** → টিকিটের সময় গণনা ডিসপ্লে

**ধাপ ৩ — মেম্বারশিপ:**
- **Membership** → নতুন মেম্বার রেজিস্ট্রেশন
- **Membership Purchase History** → মেম্বার কী কিনেছে তার ইতিহাস

**ধাপ ৪ — আর্থিক:**
- **Denomination Count** → ক্যাশ গণনা (কতটা ১০০, ৫০০ টাকার নোট)
- **Expenses** → দৈনন্দিন খরচ
- **Coupon** → ডিসকাউন্ট কুপন

**ধাপ ৫ — রিপোর্ট:**
- Sales Summary, Sales List, Date Wise Sales, Expense Report

### অন্য মডিউলের সাথে সম্পর্ক:
- **SMS** → মেম্বারদের SMS পাঠানো
- **Inventory** → খাবার/পণ্য স্টক (যদি থাকে)
- **Accounts** → আয়-ব্যয়ের হিসাব

---

## 9. Hotel (হোটেল)

### এই মডিউল কী করে?

**হোটেল রুম বুকিং, চেক-ইন/চেক-আউট, রুম সার্ভিস** পরিচালনা।

### কীভাবে কাজ করে?

**ধাপ ১ — রুম সেটআপ (Rooms):**
- **Bed Types** → Single, Double, King ইত্যাদি
- **Room Plans** → রুমের দাম (Standard, Deluxe, Suite)
- **Room Facilities** → AC, WiFi, TV ইত্যাদি সুবিধা
- **Floors** → কত তলায় কোন রুম
- **Rooms** → প্রতিটি রুম যোগ (রুম নম্বর, টাইপ, দাম)

**ধাপ ২ — বুকিং:**
- **Room Booking** → গ্রাহক রুম বুক করেন (তারিখ, রুম টাইপ, গেস্ট সংখ্যা)
- **Booking List** → সব বুকিংয়ের তালিকা (Confirmed, Checked-in, Checked-out)

**ধাপ ৩ — চেক-ইন/চেক-আউট:**
- গেস্ট এলে Check-in → রুম স্ট্যাটাস "Occupied"
- গেস্ট চলে গেলে Check-out → বিল তৈরি, পেমেন্ট

**ধাপ ৪ — রুম সার্ভিস:**
- **Room Service** → রুমে খাবার/সার্ভিস অর্ডার

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → রুম বিল, পেমেন্ট
- **Inventory/Restaurant** → রুম সার্ভিসে খাবার
- **CRM** → গেস্ট তথ্য

---

## 10. Ecommerce (অনলাইন দোকান)

### এই মডিউল কী করে?

**অনলাইন শপ/ওয়েবসাইট** চালানো — পণ্য দেখানো, অর্ডার নেওয়া, কাস্টমার ম্যানেজমেন্ট।

### কীভাবে কাজ করে?

**ধাপ ১ — ওয়েবসাইট সাজানো:**
- **Front Page → Top Sliders** → হোমপেজ স্লাইডার
- **Ecommerce Sections** → হোমপেজ সেকশন (Featured Products, Categories)
- **Banners** → প্রমোশনাল ব্যানার
- **Menus** → ওয়েবসাইট মেনু
- **Custom Pages** → About Us, Contact ইত্যাদি পেজ

**ধাপ ২ — কন্টেন্ট:**
- **Blog Posts / Blog Categories** → ব্লগ লেখা
- Inventory-র **Products** এখানে দেখায়

**ধাপ ৩ — অর্ডার প্রসেস:**
```
গ্রাহক অর্ডার দেয় → Orders-এ আসে → Confirm → Ship → Deliver
```
- **Orders** → সব অনলাইন অর্ডার দেখুন, স্ট্যাটাস আপডেট করুন
- **Customers** → অনলাইন গ্রাহক তালিকা
- **Offers** → বিশেষ অফার/ডিল

**ধাপ ৪ — সেটিংস (Settings):**
- Shipping Charges → ডেলিভারি চার্জ
- Payment Gateways → bKash, Card, COD ইত্যাদি

### অন্য মডিউলের সাথে সম্পর্ক:
- **Inventory** → পণ্য ও স্টক
- **Accounts** → অর্ডারের Invoice/Payment
- **Emails/SMS** → অর্ডার কনফার্মেশন

---

## 11. Restaurant (রেস্টুরেন্ট)

### এই মডিউল কী করে?

**রেস্টুরেন্টে খাবার অর্ডার ও বিল** — টেবিল, মেনু, কিচেন অর্ডার।

### কীভাবে কাজ করে?

- **POS** → রেস্টুরেন্ট POS টার্মিনাল
- টেবিল সিলেক্ট → মেনু থেকে খাবার অর্ডার → কিচেনে পাঠানো → বিল → পেমেন্ট
- Inventory-র পণ্য (খাবারের উপকরণ) এখানে ব্যবহার হয়

### অন্য মডিউলের সাথে সম্পর্ক:
- **Inventory** → খাবারের উপকরণ স্টক
- **POS** → একই POS ইঞ্জিন, রেস্টুরেন্ট মোড
- **Accounts** → বিক্রির হিসাব

---

## 12. Car Wash (গাড়ি ধোয়া)

### এই মডিউল কী করে?

**গাড়ি ধোয়া ও সার্ভিস সেন্টার** — সার্ভিস দেওয়া, বিল, রিপোর্ট।

### কীভাবে কাজ করে?

**ধাপ ১ — সার্ভিস:**
- **Car Wash & Service** → গাড়ি এলে সার্ভিস টাইপ সিলেক্ট, বিল তৈরি
- **Service** → সার্ভিস ম্যানেজমেন্ট

**ধাপ ২ — আর্থিক:**
- **Expenses** → দৈনন্দিন খরচ
- **Settings** → সার্ভিস ও দাম সেটআপ

**ধাপ ৩ — রিপোর্ট:**
- Sales List, Date Wise Sales, Due Payments, Expense Report

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → বিক্রি ও খরচের হিসাব
- **CRM** → নিয়মিত গ্রাহক

---

## 13. Parking (পার্কিং)

### এই মডিউল কী করে?

**পার্কিং লট** পরিচালনা — গাড়ি ঢোকা, বের হওয়া, ফি আদায়।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ:**
- **vehicles** → গাড়ির ধরন (Car, Bike, Truck) ও ফি রেট
- **Customers** → নিয়মিত পার্কিং গ্রাহক

**ধাপ ২ — পার্কিং:**
- **Parking** → গাড়ি ঢুকলে এন্ট্রি (নম্বর প্লেট, সময়)
- **Parked Vehicles** → বর্তমানে পার্ক করা গাড়ি

**ধাপ ৩ — বের হওয়া:**
- গাড়ি বের হলে সময় হিসাব → ফি → পেমেন্ট

**ধাপ ৪ — রিপোর্ট:**
- Sales List, Due Payments, Date Wise Sales

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → আয়ের হিসাব

---

## 14. SMS

### এই মডিউল কী করে?

**গ্রাহক ও মেম্বারদের SMS** পাঠানো — প্রমোশনাল, সদস্য নোটিফিকেশন।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ:**
- **Sms Account** → SMS gateway (API) কানেক্ট করুন
- Settings → SMS Settings

**ধাপ ২ — SMS পাঠানো:**
- **Game Zone → Member SMS** → গেম জোন মেম্বারদের SMS
- **Promotional → Send SMS** → সবার কাছে প্রমোশনাল SMS
- **Promotional Sms** → বাল্ক SMS ক্যাম্পেইন

### অন্য মডিউলের সাথে সম্পর্ক:
- **CRM** → Lead/Client-কে SMS
- **Game Zone** → মেম্বার SMS
- **Ecommerce** → অর্ডার নোটিফিকেশন

---

## 15. VAT (ভ্যাট)

### এই মডিউল কী করে?

**ভ্যাট (মূল্য সংযোজন কর)** হিসাব ও রিপোর্ট — বিক্রি/ক্রয়ে VAT ট্র্যাক।

### কীভাবে কাজ করে?

**ধাপ ১ — ট্রানজেকশন:**
- **Transaction** → প্রতিটি বিক্রি/ক্রয়ে VAT এন্ট্রি
- POS, Accounts, Inventory থেকে VAT অটো ক্যালকুলেট হতে পারে

**ধাপ ২ — রিপোর্ট:**
- **Reports** → মাসিক/ত্রৈমাসিক VAT রিপোর্ট
- সরকারি VAT রিটার্নের জন্য ডেটা

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → Invoice/Bill-এ VAT
- **POS** → বিক্রিতে VAT
- **Inventory** → পণ্যের Tax Rate

---

## 16. Emails (ইমেইল)

### এই মডিউল কী করে?

**ব্যবসায়িক ইমেইল** ম্যানেজমেন্ট — ইনবক্স, মার্কেটিং ইমেইল, টেমপ্লেট।

### কীভাবে কাজ করে?

**ধাপ ১ — সেটআপ:**
- **Domain & Mailboxes** → কোম্পানির ইমেইল ডোমেইন ও মেইলবক্স সেটআপ

**ধাপ ২ — ইমেইল পড়া/লেখা:**
- **Inbox** → আসা ইমেইল
- **Sent** → পাঠানো ইমেইল
- **Trash / Spams** → মুছে ফেলা / স্প্যাম

**ধাপ ৩ — ইমেইল পাঠানো:**
- **Compose** → নতুন ইমেইল লেখা
- **Marketing** → বাল্ক মার্কেটিং ইমেইল
- **Email Templates** → পুনরায় ব্যবহারযোগ্য টেমপ্লেট
- **Transactional** → অর্ডার কনফার্ম, পাসওয়ার্ড রিসেট ইত্যাদি স্বয়ংক্রিয় ইমেইল

### অন্য মডিউলের সাথে সম্পর্ক:
- **CRM** → Campaign ইমেইল
- **Ecommerce** → অর্ডার নোটিফিকেশন

---

## 17. Projects (প্রজেক্ট)

### এই মডিউল কী করে?

**প্রজেক্ট ভিত্তিক কাজ** ট্র্যাক — টাস্ক, ইস্যু, ফেজ ম্যানেজমেন্ট।

### কীভাবে কাজ করে?

**ধাপ ১ — প্রজেক্ট তৈরি:**
- **Projects** → নতুন প্রজেক্ট (নাম, ক্লায়েন্ট, শুরুর তারিখ, বাজেট)

**ধাপ ২ — কাজ ভাগ:**
- **Phases** → প্রজেক্টের ধাপ (Planning, Development, Testing)
- **Tasks** → প্রতিটি ধাপে কাজ assign করুন
- **Issues** → সমস্যা/বাগ ট্র্যাক করুন

**ধাপ ৩ — ট্র্যাকিং:**
- কে কী করছে, কতটা শেষ — সব দেখা যায়
- Accounts-এ প্রজেক্ট-ভিত্তিক Invoice/Bill করা যায়

### অন্য মডিউলের সাথে সম্পর্ক:
- **Accounts** → প্রজেক্ট-ভিত্তিক হিসাব
- **CRM** → ক্লায়েন্ট প্রজেক্ট
- **HRM** → কর্মচারী টাস্ক assign

---

## মডিউলগুলোর মধ্যে সম্পর্ক

> **বিস্তারিত সম্পর্ক ডক:** **[ERP17-Module-Somporko-Bistrito.md](./ERP17-Module-Somporko-Bistrito.md)** — শেয়ারড ডেটা, ম্যাট্রিক্স, আর্থিক/স্টক প্রবাহ, ৪টি সম্মিলিত সিনারিও, সেটআপ ক্রম।

### মূল সম্পর্ক (সংক্ষেপে)

ERP17-এ মডিউলগুলো **একটি ডেটাবেসে জড়িত**। এক জায়গায় যোগ করা তথ্য অন্য মডিউলে বারবার লাগে না।

| কেন্দ্র | কোন মডিউল যুক্ত | কী শেয়ার হয় |
|---------|-----------------|---------------|
| **Settings** | সব (১৭টি) | Users, Branches, Department, Tax, Gateway |
| **Inventory** | POS, Ecommerce, Restaurant, Game Zone, Accounts, VAT | পণ্য, স্টক, দাম, Coupon |
| **Accounts** | POS, Ecommerce, Hotel, Payroll, CRM, Game Zone, VAT | Invoice, Bill, Payment, Journal |
| **HRM** | Attendance, Payroll, CRM, Projects, POS | কর্মচারী, বিভাগ, Salesman |
| **CRM** | Accounts, Emails, SMS, Projects, Ecommerce | Lead, Client, Customer |
| **VAT** | POS, Accounts, Ecommerce, Hotel, Inventory | সব বিক্রি/ক্রয়ের কর |

### গভীর সম্পর্ক — ৩টি মূল শৃঙ্খল

**১. মানবসম্পদ শৃঙ্খল:**
```
Settings → HRM → Attendance → Payroll → Accounts (বেতন খরচ)
```

**২. বিক্রয় ও স্টক শৃঙ্খল:**
```
Inventory (পণ্য) → POS / Ecommerce / Restaurant / Game Zone
                        ↓
                   স্টক কমে → VAT → Accounts (আয়)
```

**৩. গ্রাহক শৃঙ্খল:**
```
CRM (Lead) → CRM (Client) → Accounts (Customer) → Invoice → Payment
         ↘ Emails/SMS          ↘ Ecommerce Order    ↘ Projects
```

### Inventory ↔ Accounts — দুটো Purchase একসাথে

| Inventory Purchase | Accounts Purchase |
|-------------------|-------------------|
| Requisition → Order → **Receipt** | Purchase Order → **Bill** |
| গুদামে **মাল** এলো (স্টক বাড়ে) | সাপ্লায়ারকে **টাকা** দিতে হবে |
| ফিজিক্যাল স্টক | আর্থিক দায় |

দুটো একসাথে লিংক হতে পারে — মাল এলো কিন্তু Bill না করলে হিসাবে দায় থাকবে না।

### POS ↔ Accounts ↔ Inventory — তিনটার পার্থক্য

| | Inventory | POS | Accounts |
|--|-----------|-----|----------|
| **কাজ** | পণ্য ও স্টক | দ্রুত বিক্রি | টাকার হিসাব |
| **কখন** | স্টক ম্যানেজ | কাউন্টারে | অফিসে Invoice/Bill |
| **ডেটা** | Products, Stock | Sales, Due | Invoice, Journal, COA |
| **সম্পর্ক** | POS বিক্রিতে স্টক কাটে | Inventory থেকে পণ্য | POS আয় এখানে reflect |

### Game Zone + Hotel + Ecommerce — Inventory ও Accounts-এর সাথে

| মডিউল | Inventory | Accounts | SMS/Emails |
|--------|-----------|----------|------------|
| **Game Zone** | Food Counter পণ্য | Ticket/Membership আয়, Expense | Member SMS |
| **Hotel** | Room supplies | Room Bill | Booking Email |
| **Ecommerce** | পণ্য ক্যাটালগ, স্টক কাটা | Order Payment | Order Email |
| **Restaurant** | উপকরণ স্টক | POS Sales | — |
| **Car Wash** | — | Service Fee, Expense | — |
| **Parking** | — | Parking Fee | — |

### ব্রাঞ্চ — সব মডিউলে প্রভাব

Settings → Branches সেট করলে **HRM, Attendance, Payroll, Inventory, POS, Accounts** — সবখানে ব্রাঞ্চ সিলেক্টর কাজ করে। Inventory-তে Branch Transfer দিয়ে ব্রাঞ্চের মধ্যে স্টক পাঠানো যায়।

### সম্মিলিত সিনারিও (৪টি উদাহরণ)

**খুচরা + অনলাইন:** Inventory → POS + Ecommerce → VAT → Accounts (১১ মডিউল জড়িত)

**হোটেল + রেস্টুরেন্ট:** Hotel Booking → Restaurant POS → Inventory স্টক → Accounts Bill (৭ মডিউল)

**Game Zone:** Ticket + Membership + Food Counter(Inventory) + SMS (৬ মডিউল)

**B2B সার্ভিস:** CRM Lead → Projects → HRM assign → Accounts Invoice → Emails (৬ মডিউল)

বিস্তারিত সিনারিও, ম্যাট্রিক্স টেবিল ও সেটআপ ক্রম → **[ERP17-Module-Somporko-Bistrito.md](./ERP17-Module-Somporko-Bistrito.md)**

---

### সাধারণ ব্যবসায়িক প্রবাহ (উদাহরণ):

**খুচরা দোকান:**
```
Inventory (পণ্য যোগ) → POS (বিক্রি) → Accounts (হিসাব) → VAT (কর)
```

**অফিস/কোম্পানি:**
```
HRM (কর্মচারী) → Attendance (উপস্থিতি) → Payroll (বেতন) → Accounts (খরচ)
```

**হোটেল/রেস্টুরেন্ট:**
```
Hotel (বুকিং) + Restaurant (খাবার) → Accounts (বিল) → Inventory (স্টক)
```

**অনলাইন ব্যবসা:**
```
Ecommerce (অর্ডার) → Inventory (স্টক কাটা) → Accounts (পেমেন্ট) → Emails (নোটিফিকেশন)
```

**বিক্রয় টিম:**
```
CRM (Lead) → Client → Accounts (Invoice) → Payment Receive
```

---

## দৈনন্দিন কাজের চেকলিস্ট

| সময় | কাজ | মডিউল |
|------|-----|--------|
| সকাল | উপস্থিতি আপলোড/চেক | Attendance |
| সকাল | POS চালু, বিক্রি শুরু | POS |
| দুপুর | Purchase Order/Receipt | Inventory |
| বিকেল | Lead follow-up, Meeting | CRM |
| সন্ধ্যা | দৈনিক Sales Report | POS |
| মাস শেষ | Salary Sheet generate | Payroll |
| মাস শেষ | VAT Report | VAT |
| মাস শেষ | Financial Reports | Accounts |

---

> **নোট:** প্রতিটি মডিউলের বিস্তারিত feature তালিকার জন্য `modules/` ফোল্ডারের আলাদা ফাইল দেখুন।
> মূল feature তালিকা: [ERP17-Features-Documentation.md](./ERP17-Features-Documentation.md)

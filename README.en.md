[← Language selection](README.md) | [Česky](README.cs.md)

# Free SMS Reminders for iPhone

**Automatic appointment reminders sent from your iPhone. No monthly fee.**

---

## What is this?

You write your client's phone number into the appointment in your calendar. Every day, your iPhone looks at tomorrow's appointments and sends each client a reminder text message.

- **It is free.** Nothing to buy, no subscription, no registration.
- **It uses apps you already have** — Calendar, Shortcuts and Messages.
- **It runs on your phone.** This project has no website, no account and no server of its own.
- Made for hairdressers, barbers, nail technicians, beauticians and other small businesses.

> Your mobile operator charges for the text messages as usual, according to your tariff.

---

## ➜ [Install the Shortcut](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)

Open that link **on your iPhone**. Then follow the six steps below — they take about ten minutes.

---
---

# Setup — 6 steps

---

## STEP 1 — Install the Shortcut

1. On your iPhone, tap this link: **[Install the Shortcut](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)**
2. The **Shortcuts** app opens and shows the shortcut.
3. Tap **Add Shortcut** at the bottom.
4. That's it. The shortcut is now in your phone.

> If tapping the link does nothing, copy it and open it in **Safari**.

---

## STEP 2 — Make sure your calendar is in the iPhone Calendar app

The shortcut reads appointments from the iPhone's own **Calendar** app.

If you book your clients in **Google Calendar**, you do **not** have to move anything. You only need to connect the Google account to your iPhone so that the same appointments also show up in the Calendar app.

1. Open **Settings** on your iPhone.
2. Find **Calendar**. On newer iPhones it is inside **Apps**; on older ones it is in the main list. If you cannot find it, swipe down on the Settings screen and type "Calendar" into the search box.
3. Tap **Accounts** (it may be called **Calendar Accounts**).
4. If your Google account is already listed, tap it and make sure the **Calendars** switch is turned **on**.
5. If it is not listed, tap **Add Account**, choose **Google**, and sign in. Then turn the **Calendars** switch **on**.
6. Open the **Calendar** app.
7. Tap **Calendars** at the bottom of the screen.
8. Make sure the calendar with your client appointments has a **tick** next to it.
9. Check that you can actually see your appointments in the Calendar app.

> **Important:** you keep working in Google Calendar exactly as before. Nothing needs to be copied or moved anywhere.
>
> Menu names in Settings differ slightly between iOS versions. If a name does not match exactly, look for the closest one.

---

## STEP 3 — Choose your calendar inside the Shortcut

**Do not skip this step.** The shortcut arrives with someone else's calendar selected. Until you change it, it will not find your appointments.

1. Open the **Shortcuts** app.
2. On the **Shortcuts** tab, find the reminder shortcut you installed in Step 1.
3. Tap the **three dots (⋯)** in the corner of it. The shortcut opens for editing.
4. Look at the **very first line at the top**. It says it will find calendar events.
5. In that first line, tap the **calendar name**.
6. Choose the calendar that contains your client appointments — the same one you ticked in Step 2.
7. Leave everything else in that line alone. It should still say **Tomorrow**.
8. Tap **Done** in the top corner to save.

> **Optional — the message text.** The message the shortcut sends is written in Czech. If you want different wording, scroll down in the same editing screen to the line containing the message and tap the text to change it. Keep the grey time bubble in place — that is what fills in the appointment time.

---

## STEP 4 — Write the client's phone number into the appointment

The shortcut reads the phone number from the appointment's **Notes** in Apple Calendar. Where you type it depends on which app you book your clients in.

**If you book in the Calendar app on your iPhone**

1. Open the appointment in your calendar.
2. Tap **Edit**.
3. Scroll down to **Notes**.
4. Type the client's phone number.
5. Save the appointment.

**If you book in Google Calendar**

Google Calendar has no field called Notes. The same field is called **Description** there — on an empty appointment it appears as **Add description**.

1. Open the appointment in Google Calendar.
2. Tap **Edit**.
3. Find **Description** (or **Add description**).
4. Type the client's phone number.
5. Save the appointment.

Once the calendar has synced to your iPhone, what you typed in the Description shows up as the **Notes** of that appointment in Apple Calendar — and that is where the shortcut reads it.

| Where you type the number | What that field is called |
|---|---|
| Google Calendar | **Description** / **Add description** |
| Apple Calendar | **Notes** |

It is the same text in both apps. You do not have to type it twice.

Other text may be in that field as well, before or after the number. For example:

```
Client wants the sides shorter.
+420 123 456 789
```

The safest way to write the number is with the country code and spaces:

```
+420 123 456 789
```

> **An appointment with no phone number in the Notes is simply skipped.** No message is sent for it, and nothing goes wrong. You can keep your private appointments in the same calendar.
>
> As it comes, the shortcut recognises **Czech** nine-digit phone numbers only. If your clients have numbers from another country, read the next part before you go on.

### Using this outside the Czech Republic

**The shortcut you downloaded is set up for Czech telephone numbers.** That is how it was built, and it is the one thing an international user has to change. It is a single change, and you only make it once.

Inside the shortcut there is one line that looks through the appointment Notes for a phone number. It looks for numbers in the Czech format, using this text:

```
(?:\+420\s*)?\d{3}\s*\d{3}\s*\d{3}
```

In ordinary language:

- `+420` is the country code for the Czech Republic.
- Czech numbers are nine digits, usually written as three groups of three — and that is exactly the shape this line expects.
- **Swapping `+420` for your own country code is not enough.** Countries use different lengths and different groupings, so a number from the United States or the United Kingdom would still not be found.

You do not need to understand that text. You only need to replace it with the one below.

### The international version

Replace the Czech text with this one:

```
\+[1-9](?:\s*\d){6,14}
```

With this version:

- every client number must be stored **with its international country code**,
- the number must **start with `+`**,
- **spaces are allowed** anywhere between the digits,
- it finds numbers with **7 to 15 digits** in total,
- 15 digits is the longest a telephone number can be internationally (the E.164 standard), so this covers the practical range.

> This is a simple, general search. It finds a sensibly written international number — it does **not** check that the number really exists or that it matches your country's numbering rules. Always check the number you typed is correct.

### How to make the change on your iPhone

1. Open the **Shortcuts** app.
2. Find the SMS reminder shortcut you installed in Step 1.
3. Tap the **three dots (⋯)** on it to open it for editing.
4. Scroll down until you find the action that searches the appointment Notes for the telephone number. In the shortcut as distributed it is shown as **Najít shodu se vzorem** — in English, **Match Text**.
5. Inside that action you will see the current text:

   ```
   (?:\+420\s*)?\d{3}\s*\d{3}\s*\d{3}
   ```

6. Delete all of it and put this in its place:

   ```
   \+[1-9](?:\s*\d){6,14}
   ```

7. **Do not change any of the other actions.**
8. Tap **Done** to close and save the shortcut.
9. From now on, type your clients' numbers in the full international format, beginning with `+` and the country code.
10. Run one test by hand (Step 6) before you rely on it.

### Examples you can copy

United States:

```
+1 202 555 0100
```

United Kingdom:

```
+44 7700 900123
```

These are **examples only** — they are reserved numbers used for demonstrations and they do not reach anybody. You must type your client's real number.

Spaces are fine, and you can group the digits however is comfortable. Stick to `+`, the country code and digits: do **not** use brackets or hyphens, because the simple search above does not expect them.

Type the international number into the same field you already use, as described above in this step:

| Where you book | Field | What to type |
|---|---|---|
| Google Calendar | **Description** / **Add description** | `+44 7700 900123` |
| Apple Calendar | **Notes** | `+44 7700 900123` |

> **One last thing.** Changing this phone-number line does **not** change the message your clients receive. The shortcut as distributed sends a message written in **Czech**. If you want it in your own language you have to rewrite the message text separately — see the note at the end of Step 3.

---

## STEP 5 — Set it to run automatically every day

Installing the shortcut does **not** make it run by itself. You have to set the daily time. This is done once.

1. Open the **Shortcuts** app.
2. Tap **Automation** at the bottom.
3. Tap **+** in the top right corner. (On older iPhones, tap **Create Personal Automation** first.)
4. Choose **Time of Day**.
5. Set the time you want the messages to go out — for example **14:30**.
6. Choose **Daily**, so it repeats every day.
7. Tap **Next** in the top corner.
8. Choose your reminder shortcut from the list. (If you see a list of actions instead, search for **Run Shortcut**, add it, then tap it and pick your reminder shortcut.)
9. **Now the important part.** Look for how the automation should start:
   - If you see **Run Immediately** and **Run After Confirmation**, choose **Run Immediately**.
   - If instead you see a switch called **Ask Before Running**, turn it **off**.
   - You may also see **Notify When Run**. Turn it off if you do not want a notification each day; leave it on if you like knowing it happened.
10. Tap **Done**.
11. Check that the new automation appears in the **Automation** list and is switched on.

> **Why this matters:** if the automation is set to **Run After Confirmation**, nothing is sent until you tap a notification yourself. For reminders that go out on their own, choose **Run Immediately**.
>
> These two option names come from recent versions of iOS. Older versions use the **Ask Before Running** switch instead, and the exact wording can differ slightly. Choose whichever option means "run without asking me".

**Which time should I choose?**

The shortcut always sends reminders for **tomorrow's** appointments. So pick a time today when it suits your clients to hear from you about tomorrow — early afternoon or early evening usually works well. **14:30** is only an example.

> **Watch out for duplicate messages.** The shortcut keeps no record of who it has already sent a reminder to.
>
> - Create **only one** daily automation for it.
> - Once the automation has run that day, **do not run the shortcut by hand again** — unless you really do want a second message to go out.
> - Every additional run can send reminders for the same tomorrow appointments all over again.

---

## STEP 6 — Test it

Test it once on yourself before you let it message clients. Read both warnings below first, then test.

> **Important:** A manual run does not process only your test appointment. It checks **every appointment for tomorrow in the calendar currently selected inside the Shortcut** and sends a message for every appointment containing a recognised phone number.

> **Important:** The shortcut does not remember which reminders it has already sent. Every additional manual or automatic run may send the same reminders again.

### The safe test — using an empty test calendar

This is the recommended way. You test in a calendar that holds no clients, so you cannot message anyone by accident.

1. **Turn the daily automation off while you test.** Open **Shortcuts → Automation**, tap your automation and switch it off.
2. In the **Calendar** app, create or pick an **empty calendar used only for the test** — for example one called **SMS test**. It must contain no client appointments. (A new calendar is created from the calendar list in the Calendar app; the exact button names differ between iOS versions.)
3. Open the shortcut (**Shortcuts → ⋯**) and temporarily select that test calendar in its **first action**.
4. Create **exactly one** appointment for **tomorrow** in the test calendar.
5. Put in a phone number you control — your own second number, or a family member who knows about the test:
   - in **Google Calendar**, the **Description** / **Add description** field;
   - in **Apple Calendar**, the **Notes** field.
6. Run the shortcut by hand **exactly once**.
7. The first time, your iPhone will ask for permission to use your **Calendar** and to **send messages**. Allow both.
8. Check that the message arrives, and that the appointment time in it is correct.
9. Delete the test appointment.
10. In the shortcut, **switch the calendar back** to your real client calendar.
11. **Switch the daily automation back on.**

### If you would rather not create a test calendar

You may test in your normal selected calendar, but **only after checking that no other appointment for tomorrow contains a phone number**.

- Go through **every appointment for tomorrow** in that calendar and look at its **Description** (its **Notes** in Apple Calendar).
- If a real client appointment for tomorrow already contains a number, **do not run the shortcut by hand using that calendar**. That client would be messaged straight away.
- Deleting the test appointment afterwards **does not undo messages that have already been sent**.

> Sending a test message costs the same as any other text message from your tariff.

---

# Done

That is everything you need. From now on, write the phone number into the Notes of each appointment and the reminders go out on their own.

The rest of this page explains how it works inside and what to do if something goes wrong. You do not have to read it.

---

<div align="center">⸻⸻⸻</div>

---

# How the Shortcut works

Everything below is background information for anyone who wants to understand or change the shortcut.

## Overview

```
        Calendar
            |
    Tomorrow's events
            |
        Read Notes
            |
   Phone number found?
        |         |
        No        Yes
        |         |
   Skip event   Read appointment time
                  |
              Create reminder text
                  |
                Send SMS
                  |
              Next event
```

---

### A. Load tomorrow's events

The first action of the shortcut finds calendar events. It is limited to **50 events**, taken from **one selected calendar**, where the **day is Tomorrow**.

- **Current setting:** limit 50, Day = Tomorrow, plus a calendar chosen by whoever built the shortcut.
- **What you must change:** the calendar. It is the only project-specific setting most people need to touch, and it is why Step 3 exists — the calendar stored in the shared shortcut is not yours.
- **Normally leave alone:** the day filter. "Tomorrow" is what makes this a day-ahead reminder.

The limit of 50 is only a maximum. It does not mean 50 messages are sent — it is the largest number of appointments the shortcut will look at in one run.

### B. Repeat through every event

The shortcut then handles the events it found **one at a time**, from the first to the last. Everything described below happens separately for each appointment.

### C. Read the Notes

For the appointment it is currently working on, it reads the **Notes** field.

### D. Look for a phone number in the Notes

It searches that text for a phone number using this pattern:

```
(?:\+420\s*)?\d{3}\s*\d{3}\s*\d{3}
```

In plain terms, it matches a Czech nine-digit number written as three groups of three digits, with spaces between the groups allowed but not required, and an optional `+420` in front.

All of these are recognised:

```
+420 123 456 789
+420123456789
123 456 789
123456789
```

Because the pattern is built for Czech numbers, foreign numbers in another format may not be matched.

### E. Skip events with no phone number

The shortcut checks whether the search found anything. If there is **no match**, it does nothing at all for that appointment — no message, no error — and moves straight on to the next one.

This is what makes it safe to keep private appointments, breaks and personal events in the same calendar.

### F. Use the first number found

If the search found one or more numbers, the shortcut takes the **first** one and uses it as the phone number to send to.

So if the Notes contain two numbers, only the first is used. Keep one number per appointment.

### G. Read the appointment time

It takes the appointment's **start date and time** and formats it so it can be put into the message.

### H. Build the reminder text

The message currently in the shared shortcut is in Czech:

```
Dobrý den, připomínám Vám Váš termín zítra v [čas]. Pokud se nemůžete dostavit,
dejte mi prosím vědět. Děkuji.
```

`[čas]` is the Czech word for "time". It is not typed in by hand — it is replaced automatically with the formatted start time of that appointment.

You can rewrite this message to say whatever you want. An English version might read:

```
Hello, this is a reminder of your appointment tomorrow at [time]. If you are
unable to attend, please let me know. Thank you.
```

> The shortcut does **not** translate the message by itself. It sends whatever text it contains, in whatever language that text is written, to every recipient. The version distributed here contains the Czech text.

### I. Send the message

The finished text is sent to the phone number taken from the Notes, through the iPhone's messaging.

### J. Continue with the next event

The shortcut then goes back and repeats the same steps for the next appointment, until all of tomorrow's events have been handled.

---

## What you can change, and what to leave alone

| | Change | Leave alone |
|---|---|---|
| Calendar | **Yes — you must.** | |
| Message text | Yes, if you want. | |
| The time bubble in the message | | Yes |
| Day filter "Tomorrow" | | Yes |
| Phone number search | Only for foreign numbers. | |
| The 50-event limit | Rarely needed. | |

---

## If something does not work

**No messages are sent at all**

- Check Step 3. The calendar set inside the shortcut is the most common cause.
- Open **Shortcuts → Automation** and check the automation is there and switched on (Step 5).
- Check it is set to **Run Immediately** and is not waiting for you to confirm a notification.

**One client did not get a message**

- Open that appointment and check the phone number really is in the **Notes**, not in the title.
- Write the number as `+420 123 456 789` and try again.

**The shortcut finds no appointments**

- The appointment must be for **tomorrow**. Today's appointments are not found.
- Open the **Calendar** app and check you can see the appointment there (Step 2).

**It asks for permission, or nothing happens**

- Run the shortcut by hand once — but **follow the safety rules in Step 6 first**. A manual run goes through every appointment for tomorrow in the selected calendar and may message every client it finds a number for, so the safest way is to use an empty test calendar. Errors appear on screen when you run it yourself.
- Allow **Calendar** access and message sending when asked. You can check it later in **Settings → Privacy & Security → Calendars**.

**A message will not send to one number**

- Try sending a normal text to that number from the **Messages** app. If Messages cannot, the shortcut cannot either.

---

## Cost

The shortcut and this guide are free. There is no subscription and nothing to buy.

Your mobile operator charges for each text message according to your tariff, exactly as if you had typed it yourself. Messages abroad usually cost more. Check your tariff before sending large numbers of reminders.

## Privacy

This project runs no server of its own. There is no account, no database, no analytics and no subscription service behind it. The shortcut's own processing runs locally on your iPhone, on the events the iPhone makes available in the Calendar app.

Where the appointment data itself is stored depends on which calendar account you use:

- **If you use Google Calendar:** the appointment data, including a phone number typed into the **Description**, stays associated with your Google account and is stored and synchronised through it under Google's own terms. Once that account is connected to your iPhone, the Calendar app can display the appointment and make it available to Shortcuts, and the Google Description appears to the shortcut as the event's **Notes**. Displaying a Google calendar in Apple Calendar does not by itself copy the event into your iCloud calendar.
- **If you use an iCloud calendar:** the appointment data is stored and synchronised through Apple's iCloud service under Apple's own terms.

This project itself does not receive the appointment data or store it on any server of its own. If you use Google Calendar or iCloud, that service also processes and synchronises the data under its own terms.

The shortcut is distributed through Apple's official iCloud sharing for Shortcuts, so downloading it is a request to Apple's servers under Apple's own terms. Sending a text message goes through your mobile operator like any other message.

## Responsible use

Send reminders only to your own clients, only about their own appointment, and stop immediately if someone asks you to. Say who you are in the message. This is a personal tool for your own bookings — it is not a bulk-messaging or marketing system, and rules on messaging and personal data (in the EU, GDPR among them) still apply to you.

## About

An independent community project, shared free of charge so that people do not have to pay a monthly fee for a reminder their own phone can send.

Not affiliated with, authorised by or endorsed by Apple Inc. Apple, iPhone, iCloud, Calendar, Shortcuts and Messages are trademarks of Apple Inc.

## Licence

This project is **source-available**, not open source. It is released under the [MIT License with the “Commons Clause” License Condition v1.0](LICENSE).

**You may:**

- use the Shortcut free of charge;
- use it in your own business — for example a hairdresser, barber shop, nail or beauty salon sending reminders to your own clients;
- modify it for your own needs;
- share copies free of charge, as long as you keep to the licence and pass on the required notices (both the MIT notice and the Commons Clause notice).

**You may not:**

- sell the Shortcut itself;
- put access to the Shortcut behind a paywall;
- repackage substantially the same Shortcut and sell it as your own product;
- charge for a product or service whose value derives, entirely or substantially, from providing this Shortcut itself — that is what the Commons Clause defines as "Sell".

In one line: **using the Shortcut in a commercial business is allowed; selling the Shortcut itself is not.**

### What the licence covers

It covers the project-authored Shortcut configuration and this project's documentation and assets, to the extent they are copyrightable and owned by the licensor. Apple software, Apple user-interface elements, Apple trademarks, Apple icons, iOS, Shortcuts, Calendar and other Apple-owned material remain the property of their respective owners. This project is independent and is not affiliated with, sponsored by or endorsed by Apple Inc.

The licence is a grant of copyright permissions. It is not copy protection: Apple's own iCloud sharing lets anyone with the link obtain and copy a Shortcut, and nothing here changes that.

Earlier revisions that were distributed under the MIT License remain subject to the terms under which they were distributed. The current version is distributed under MIT + Commons Clause.

This section is a plain-English summary for convenience only. The [LICENSE](LICENSE) file is the text that controls.

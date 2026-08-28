**English** · [Čeština](README.cs.md)

# Free SMS Reminders for iPhone

Send automatic text-message reminders from your Apple Calendar events using Apple Shortcuts — no subscription, no account, no external service.

---

## What this is

Many small businesses and individuals pay a monthly fee just to send "don't forget your appointment tomorrow" text messages. If you already carry an iPhone, you can usually do the same thing with apps that are already on the phone.

This project shares a free Apple Shortcut and a plain-language guide. The idea is simple: you write the recipient's phone number into the calendar event, and a Shortcut — started automatically by an automation you set up on your own iPhone — sends them an SMS reminder.

There is no server behind this project, no sign-up, no analytics platform, and nothing to pay for. It is a workflow, not a product.

---

## Install the Shortcut

**➜ [Install the Shortcut](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)**

Open that link **on your iPhone**. It uses Apple's official iCloud sharing mechanism for Shortcuts, so it opens directly in the Shortcuts app and asks whether you want to add it.

> Installing the Shortcut does **not** make it run on a schedule. Scheduling is a separate step that you configure yourself — see [Set up the personal automation](#5-set-up-the-personal-automation).

---

## How it works

```
Calendar event  →  phone number in the Notes  →  Shortcut  →  SMS reminder
```

In a little more detail:

```
   Your calendar
        │   an upcoming event that contains a phone number
        ▼
   Personal Automation  ──── runs at the time you choose ────▶   Shortcut
                                                                    │
                                                                    ▼
                                                          Messages sends an SMS
```

The workflow is designed to:

1. look at relevant upcoming events in your Calendar,
2. read a phone number stored in the event's information (the **Notes** field),
3. skip any event that does not contain a usable phone number,
4. send an SMS reminder to the phone numbers it found,
5. be started automatically by a personal automation in the Shortcuts app.

Everything happens on the iPhone, through Apple's own apps.

---

## The two pieces you need

This is the part people most often get wrong, so it is worth stating plainly. There are **two separate things**, and you need both:

| | What it is | Where it comes from |
|---|---|---|
| **The Shortcut** | The set of steps that finds the events, reads the phone numbers and sends the messages. | Installed from the [iCloud link](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78) above. |
| **The personal automation** | The trigger that runs the Shortcut at a chosen time, e.g. every day at 18:00. | Created by **you**, on **your** iPhone, in the Shortcuts app. It is not included in the shared link and cannot be. |

Apple does not let a shared Shortcut carry an automation with it, so the automation always has to be created locally on each device.

---

## Requirements

- An iPhone with the **Shortcuts** app (included with iOS).
- The **Calendar** app, with the calendar you want to use visible to iOS. Calendars synced into iOS (iCloud, Google, Exchange, and similar) work as long as they appear in the Calendar app.
- The ability to send **SMS / text messages** from the phone — an active mobile plan and a working Messages app.
- Permission for Shortcuts to access your **Calendar** and to **send messages**. iOS asks the first time the Shortcut needs each one.

No minimum iOS version is stated here, because the Shortcut's exact requirements have not been verified. If your iPhone can open the iCloud link and add the Shortcut, you are in good shape. Some wording in the Shortcuts app differs between iOS versions — the steps below describe what to look for rather than an exact screen.

---

## Step-by-step setup

### 1. Install the Shortcut

1. Open **[this link](https://www.icloud.com/shortcuts/d9af7a261a63499ca4d2e213eb443f78)** on your iPhone (tap it in Messages, Notes, Safari or wherever you have it).
2. The **Shortcuts** app opens and shows a preview of the Shortcut.
3. Scroll through the preview if you like, then tap **Add Shortcut** (some iOS versions show **Set Up Shortcut** and ask a question or two first — answer them and continue).
4. The Shortcut now appears in the **Shortcuts** tab of the app.

If nothing happens when you tap the link, open it in **Safari** rather than inside another app's built-in browser.

### 2. Look at what the Shortcut actually does

Before you rely on it, open the Shortcut and read it. In the Shortcuts app, tap the **⋯** (or long-press → **Edit**) on the Shortcut to see every step in plain sight.

This is worth two minutes, because the Shortcut's own actions are the authoritative answer to questions such as:

- **which calendar(s)** it looks at,
- **which time window** counts as "upcoming" (for example today, or tomorrow),
- **where in the event** it looks for the phone number,
- **what the message text says**.

You can change any of it. It is your copy on your phone.

> The exact internal configuration of the shared Shortcut is not documented here, because it could not be independently verified while writing this guide. Reading the Shortcut on your own device gives you the accurate answer.

### 3. Run it once by hand

Tap the Shortcut in the Shortcuts app to run it manually.

- iOS will ask for permission to access **Calendar**, and to **send messages**. Allow both, otherwise the workflow cannot work.
- Test with a calendar event pointing at **your own second number, or a friend who is expecting the test** — not a real customer.

A manual run is the fastest way to find out whether your calendar events are written the way the Shortcut expects.

### 4. Prepare your calendar events

The recipient's phone number goes **inside the event**, in the **Notes** field (in the Calendar app: open the event → **Edit** → the **Notes** box at the bottom).

To create an event:

1. Open **Calendar** and add an event as usual — title, date, time.
2. Tap **Edit**, scroll to **Notes**.
3. Type the recipient's phone number.
4. Tap **Add** / **Done**.

An illustrative example:

```
Title:  Haircut — Jana
When:   Tomorrow, 14:00
Notes:  +420123456789
```

Practical advice:

- Write the number in **full international format** where you can (`+` and country code, no spaces). This is the format that behaves most predictably for SMS, and it removes any doubt about which country the number belongs to.
- Keep the Notes field simple at first. If you want extra text in there as well, test that combination once before you depend on it.
- Events **without** a usable phone number are ignored — you can keep normal, private events in the same calendar.

> A strict, guaranteed phone-number syntax is deliberately not claimed here: it depends on how the Shortcut parses the Notes field, which was not verified. Open the Shortcut (step 2) to see exactly how it extracts the number, and confirm your own format with a test run (step 3).

### 5. Set up the personal automation

This makes the Shortcut run on its own. You create it yourself; it is not part of the shared Shortcut.

1. Open **Shortcuts** → the **Automation** tab.
2. Tap **+** (top right). On some iOS versions you first tap **Create Personal Automation**.
3. Choose **Time of Day**.
4. Pick the time you want reminders to go out — for example **18:00**, sending reminders the evening before — and set it to repeat **Daily**.
5. Tap **Next**.
6. Add the action **Run Shortcut**, then tap the shortcut name and choose the reminder Shortcut you installed.
7. Tap **Next** / **Done**.
8. **Look for the confirmation setting** before you finish. Depending on your iOS version this appears either as an **Ask Before Running** switch (turn it **off** for unattended sending) or as a choice between **Run Immediately** and **Run After Confirmation** (choose **Run Immediately**). Wording and placement vary between iOS releases; if you do not see such an option for this automation, the automation may show a notification you have to tap before it runs.
9. Make sure the automation is **enabled** in the Automation tab.

Choose the time thoughtfully: an automation that fires at 08:00 sends reminders for whatever the Shortcut counts as "upcoming" at 08:00. Match the automation time to the time window the Shortcut uses (step 2).

---

## Privacy

- This project **does not run a server**. There is no backend, no account system, no database, no analytics and no subscription platform operated by this project.
- The Shortcut is distributed through **Apple's official iCloud Shortcut-sharing mechanism**. Downloading it is a request to Apple's servers, subject to Apple's own terms and privacy policy.
- The workflow's steps — reading calendar events and sending messages — are performed **by apps on your iPhone**, using iOS permissions you grant. This repository adds no additional data collection of its own.
- Sending an SMS necessarily involves your **mobile carrier**, which handles the message like any other text you send.
- If you edit the Shortcut and add actions that contact other services, that is outside the scope of what is described here.

To be precise: no absolute privacy guarantee is made for Apple's services, your carrier's network, your calendar sync provider, or any changes you make to the Shortcut yourself. What is claimed is narrow and checkable — this project has no service of its own that could collect anything.

---

## Cost

- The Shortcut and this guide are **free**.
- There is **no subscription** and nothing to buy.
- **Your carrier's normal charges still apply.** Depending on your mobile plan, each SMS may cost money, count against a message allowance, or be included at no extra cost. Messages to international numbers are often charged differently. Check your plan before sending in volume.

---

## Limitations and things worth knowing

- **It depends on your mobile service.** No mobile signal or no SMS allowance means no reminder. Messages sent as iMessage rather than SMS depend on the recipient's device and data connection.
- **iOS permissions must be granted** and must stay granted. A denied Calendar or Messages permission stops the workflow silently.
- **Automation behaviour varies by iOS version.** The names of settings, and whether an automation can run without confirmation, have changed between iOS releases.
- **The phone has to be on** and, in practice, working normally at the scheduled time. Power off, or an interrupted automation, means no messages that day.
- **You are responsible for the messages.** Making sure a reminder is appropriate, expected and lawful is your job, not the Shortcut's.
- **This is not an SMS gateway.** It is a personal workflow using the Messages app. It is not built for bulk messaging, marketing campaigns, or high volume, and carriers may treat unusual sending patterns as abuse.
- **Nothing here is guaranteed.** Test it, and keep an eye on it before you rely on it for anything that matters.

---

## Troubleshooting

**The Shortcut does not find any calendar events**
- Check that the calendar you use is switched on in the Calendar app (**Calendars** at the bottom of the month view).
- Confirm that the Shortcut is looking at the calendar and the time window you expect — open it and read the actions (step 2).
- Confirm the event really is inside that time window. An automation running at 18:00 for "tomorrow's" events will not see an event later the same evening.
- Check Calendar permission: **Settings → Privacy & Security → Calendars → Shortcuts**.

**No phone number is found in an event**
- The number must be in the event itself, most commonly the **Notes** field — not in a separate note, contact, or the event title, unless the Shortcut reads those too.
- Try the plain international form: `+420123456789`, without spaces, brackets or dashes.
- Remove any extra text from Notes and test again; if it then works, reintroduce the extra text and see what breaks.

**The message does not send**
- Run the Shortcut manually. Manual runs show errors on screen that an automatic run may not.
- Check that you can send a normal text message to that number from the **Messages** app. If Messages cannot, the Shortcut cannot either.
- iOS may ask for permission to send messages the first time; if you declined, allow it in **Settings → Privacy & Security**, or delete and reinstall the Shortcut to be asked again.
- Some iOS versions require a confirmation tap before a message is sent from an automation. If a notification is waiting for you, that is the cause.

**The automation does not run**
- Open **Shortcuts → Automation** and check that it is listed and enabled.
- Check the confirmation setting described in step 5 — an automation waiting for confirmation looks like an automation that did not run.
- Check whether a notification appeared and was dismissed.
- Low Power Mode, Focus modes and a powered-off phone can all affect whether things happen on time.

**Permissions look wrong**
- **Settings → Privacy & Security → Calendars** and check Shortcuts is allowed.
- **Settings → Shortcuts** for the app's own switches.
- Reinstalling the Shortcut makes iOS ask for its permissions again on the next run.

---

## Responsible use

Only send reminders to people who expect to hear from you — your own clients, patients, customers or friends — and only for the purpose they gave you their number. Include something that identifies you, honour a request to stop immediately, and keep the volume low and human.

Rules on messaging, marketing and personal data differ from country to country (in the EU, GDPR and national rules on electronic communications apply). Using this workflow does not exempt you from them. If you are messaging in a professional context, make sure you know which rules apply to you.

---

## About

An independent community project, shared freely so that people do not have to pay a recurring fee for a reminder that their own phone can send.

Not affiliated with, authorised by, or endorsed by Apple Inc. Apple, iPhone, iCloud, Calendar, Shortcuts and Messages are trademarks of Apple Inc., registered in the U.S. and other countries. Other names are trademarks of their respective owners.

## Licence

The contents of this repository — the documentation and guides — are released under the [MIT Licence](LICENSE).

That licence covers **this repository's content only**. It does not apply to, and makes no claim over, the Apple Shortcut hosted on Apple's iCloud servers, the Shortcuts app, or any other Apple software or service, all of which remain subject to their own terms.

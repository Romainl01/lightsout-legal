# Privacy Policy

**Lights Out**
Version 1.1, 4 September 2026

> Every factual claim in this document was written against the app's source
> code rather than from a template, and each one was re-checked against that
> code before publication.

---

## The short version

Lights Out helps you go to bed earlier. To do that it reads your sleep from
Apple Health, and it can block apps you choose in the evening.

**Your sleep readings stay on your phone.** Your sleep stages, your heart rate,
your heart rate variability and the times you went to bed are read, scored and
drawn on the device, and none of them are ever transmitted.

Two small things do leave, and both are deliberate: the account you sign in
with, and anything you type into the feedback form. A third leaves only if you
subscribe, and it is your purchase, not your sleep.

One more can leave, and only if you switch it on: if you compare your nights
with friends, your sleep score and your sleep length are sent for the nights you
share. Sharing is off unless you turn it on, it is limited to friends you
invited yourself, and turning it off deletes what was already shared.

---

## 1. Who is responsible

Lights Out is made by Romain Lagrange, an individual developer, not a company.

Contact: romainlagrange33@gmail.com

No postal address is published. Under the GDPR a controller must publish an
identity and a means of contact; for an individual developer an email address
is sufficient.

---

## 2. What stays on your phone, and never reaches us

This section exists because it is the larger half of what the app does.

| Data | Where it comes from | Where it goes |
| --- | --- | --- |
| Sleep stages, sleep and wake times | Apple Health, read only | Stays on the device |
| Heart rate, heart rate variability | Apple Health, read only | Stays on the device |
| Your night history, and your score on any night you have not shared | Computed on the device | Stays on the device |
| The apps you choose to block | Apple Screen Time | Stays on the device |
| Your wake-up time, your target sleep, your name | You, during setup | Stays on the device |
| Your alarm | Apple AlarmKit | Stays on the device |

**Health data.** Lights Out asks Apple Health for permission to *read* sleep,
heart rate and heart rate variability. It never asks for permission to write.
No health MEASUREMENT is included in anything the app transmits, including
feedback reports, and that is an engineering constraint in this codebase rather
than a marketing line. Your stages, your heart rate, your heart rate variability
and your bed and wake times have no path off the device at all.

The one exception is the one you choose: if you turn on sharing with friends,
two derived numbers are sent, and only those two. See section 3.4.

**The apps you block.** When you pick apps to block in the evening, iOS does not
hand the app their names. It hands back opaque tokens that only the system can
resolve, and they stay in the app's own storage on your device. We could not
tell you which apps you picked even if you asked us.

**Your name and your settings** are stored on the device. They are not synced,
not backed up to us, and not readable by us.

---

## 3. What leaves your phone

### 3.1 Your account

Lights Out is behind an account so that your settings belong to you rather than
to one installation. Sign in with Apple is the only way in.

We store:

- an internal account identifier;
- **the email address Apple gives us.** If you chose "Hide My Email", that is a
  relay address ending in `@privaterelay.appleid.com`, and we never see your real
  one;
- **a token from Apple**, kept for exactly one purpose: Apple requires that
  deleting your account also revokes the permission you granted at sign-in
  (Apple Technical Note TN3194), and this token is the only way to do that. It is
  never used to read anything from Apple, and it is destroyed with your account.

We do not store a password. We never see one.

### 3.2 Feedback you send

If you use "Send feedback" in the app, we receive the message you wrote, and
this context, so that a bug report is actionable rather than a shrug:

- the app version and build number, and whether it is a TestFlight or App Store build;
- your device model and iOS version;
- whether the app is reading Apple Health or showing example nights, and whether
  it has any nights at all;
- whether Screen Time is authorised and whether the block is switched on;
- whether the alarm permission is granted;
- whether the app was in its light or dark appearance;
- the email address on your account, so a reply can reach you.

**No sleep measurement is included.** Not a duration, not a score, not a heart
rate. "Whether the app has any nights" is a yes or no about the state of the app,
not a number about you.

The screen tells you this before you send, in the same words.

### 3.4 Comparing your nights with friends

This is the only feature that sends anything derived from Apple Health, and it
is off until you turn it on.

**What is sent.** For each night you share, exactly two numbers: your sleep
score out of 100, and how long you slept in minutes. Nothing else. Not the time
you went to bed, not the time you woke up, not your sleep stages, not your heart
rate, not your heart rate variability, not your first name.

**Who can read it.** Only people you became friends with, and you become friends
only when one of you sends an invite link and the other opens it. There is no
search, no directory, and no way for a stranger to find you. Removing a friend
also blocks them, so the same link cannot rebuild the connection.

**How long it is kept.** Thirty five days. A daily job deletes anything older,
because no screen in the app looks back further than a week.

**How to stop.** One switch in your profile. Turning sharing off deletes every
night you have already shared, not just the ones to come.

**Why we ask you explicitly.** Sleep is health data, which the GDPR treats as a
special category. The only lawful basis for sharing it here is your explicit
consent, so the app asks for it on a screen of its own, states exactly what is
sent, and lets you withdraw it in the same number of taps it took to give.

### 3.5 Your subscription

Lights Out Pro is sold by Apple, through the App Store. We never see your card,
your billing address, or your Apple Account.

The app uses **RevenueCat** to check whether your subscription is active. What
that means in practice:

- **Your purchase is anonymous to us.** The app does not tell RevenueCat who you
  are. It never sends your account identifier, your email address or your
  handle, so your subscription is held under an identifier RevenueCat generates
  on its own and is **not joined to your Lights Out account**.
- **What RevenueCat receives:** your App Store purchase and renewal history for
  this app, plus the ordinary technical context of the request, which is your
  device model, your iOS version, the app version and the country your network
  connection appears to be in.
- **What it never receives:** anything from Apple Health. Not a score, not a
  duration, not a heart rate. The subscription check and your sleep have no
  code path between them.

RevenueCat is in the United States. Your purchase history also lives with Apple,
under Apple's own policy, because Apple is the merchant.

**Cancelling** is done in the App Store, in Settings, and not by us. If you
subscribe with a free trial, the app schedules **one** reminder, two days before
the first charge. That reminder is a local notification: it is scheduled on your
phone, it never reaches a server, and no push token exists in this app.

---

### 3.3 What we do not collect

No analytics. No crash reporting service. No advertising identifier. No
tracking, in the App Store's sense or any other. Of the app's forty-six
dependencies, not one is an analytics, attribution or advertising library, and
exactly one third party SDK collects anything at all: RevenueCat, which receives
your purchase history and nothing else. See section 3.5.

We do not sell data. There is no data to sell.

---

## 4. Who else touches this data

Four companies, each for one job:

| Who | What they do | Where |
| --- | --- | --- |
| **Supabase** | Hosts the account database and the feedback table | Paris, France (`eu-west-3`) |
| **Resend** | Delivers a feedback report to us as an email | United States |
| **RevenueCat** | Tells the app whether your subscription is active | United States |
| **Apple** | Sign in with Apple; the App Store | Per Apple's own policy |

Your feedback report reaches us as an email, so it passes through Resend and
then sits in a normal mailbox, with the ordinary consequences that has.

Apple Health data and Screen Time selections reach none of them, because they
never leave your device. RevenueCat in particular receives your purchase and no
part of your account: see section 3.5.

---

## 5. How long we keep it

Your account and its data live until you delete the account. There is no other
clock.

Feedback reports are kept as long as they are useful for fixing what they
describe, and the copy that arrived by email lives in a mailbox like any other
message. Deleting your account removes the reports from our database; it cannot
un-send an email that already arrived.

---

## 6. Deleting your account

**In the app: Profile, then Account, then Delete account.** It is immediate and
it is not reversible.

When you do that:

- your account and every row attached to it are deleted from our database;
- the permission you granted through Sign in with Apple is revoked with Apple,
  so Lights Out disappears from the list in your Apple Account settings;
- **the phone is cleaned up too**: your alarm is cancelled and your app blocks
  are lifted. This matters more than it sounds. An app that forgot to lift its
  own blocks would leave you with apps blocked every evening and no way left to
  unblock them.

**Your sleep stays in Apple Health.** Lights Out only ever read it. Deleting
your account does not touch it, and you can revoke the app's access at any time
in Settings, Privacy and Security, Health.

---

## 7. Your rights

If you are in the EU or the UK, the GDPR gives you the right to access, correct,
export, delete, or object to the processing of your personal data, and the right
to complain to a supervisory authority (in France, the CNIL).

In practice, for this app:

- **Deletion** is a button in the app, and it is faster than writing to us.
- **Access and export**: write to us and we will send you what we hold, which is
  your account row and your feedback reports.
- **Correction**: your name and settings are yours to change in the app; the
  email address comes from Apple and changes there.

---

## 8. Children

Lights Out is not directed at children under 13, and we do not knowingly collect
anything from them.

---

## 9. Changes to this policy

If we start collecting something new, this page changes in the same release that
collects it, and the app's own disclosure sentence changes with it. The date at
the top is the version you are reading.

---

## 10. Contact

romainlagrange33@gmail.com

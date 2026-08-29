# Privacy Policy

**Lights Out**
Version 1.0, 30 August 2026

> Every factual claim in this document was written against the app's source
> code rather than from a template, and each one was re-checked against that
> code before publication.

---

## The short version

Lights Out helps you go to bed earlier. To do that it reads your sleep from
Apple Health, and it can block apps you choose in the evening.

**Your sleep data never leaves your phone.** Not to us, not to anyone. The app
reads it, scores it, draws it, and that is the end of it.

What does leave your phone is small and deliberate: the account you sign in
with, and anything you type into the feedback form. That is the whole list.

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
| Your sleep score and your night history | Computed on the device | Stays on the device |
| The apps you choose to block | Apple Screen Time | Stays on the device |
| Your wake-up time, your target sleep, your name | You, during setup | Stays on the device |
| Your alarm | Apple AlarmKit | Stays on the device |

**Health data.** Lights Out asks Apple Health for permission to *read* sleep,
heart rate and heart rate variability. It never asks for permission to write.
The permission screen you saw says "Nothing leaves your phone", and that
sentence is an engineering constraint in this codebase, not a marketing line:
no health measurement is included in anything the app transmits, including
feedback reports.

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

### 3.3 What we do not collect

No analytics. No crash reporting service. No advertising identifier. No
tracking, in the App Store's sense or any other. No third party SDK that
collects anything: the app has thirty-seven dependencies and not one of them is
an analytics, attribution or advertising library.

We do not sell data. There is no data to sell.

---

## 4. Who else touches this data

Three companies, each for one job:

| Who | What they do | Where |
| --- | --- | --- |
| **Supabase** | Hosts the account database and the feedback table | Paris, France (`eu-west-3`) |
| **Resend** | Delivers a feedback report to us as an email | United States |
| **Apple** | Sign in with Apple; the App Store | Per Apple's own policy |

Your feedback report reaches us as an email, so it passes through Resend and
then sits in a normal mailbox, with the ordinary consequences that has.

Apple Health data and Screen Time selections reach none of them, because they
never leave your device.

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

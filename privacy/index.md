---
title: ETLock privacy policy
permalink: /privacy/
---

# ETLock privacy policy

Last updated: 2026-10-24

ETLock is made by Hamish and Cameron McAlpine, two brothers who race. This page says what the
app collects, why, and what we do with it — in plain words, because that is the standard we hold
the app itself to.

## The short version

- You can open ETLock and read the air at your track with **no account** and **no sign-up**.
- We do not run ads and we do not sell your data to anyone, ever.
- Crash reports and the in-app diagnostic trace are **off until you say yes**, and you can turn
  either off again at any time in Settings.
- Location is used **only while the app is open** (foreground) to find your nearest track — we
  never track you in the background.
- A photo of your timeslip is read **on your phone** and **never uploaded**.
- Weather numbers come from Open-Meteo, credited on every screen that shows them, as their
  licence requires.
- Write to us any time: **support@etlock.app**. A racer reads it.

## What we collect, and why

### An anonymous session

The first time you open ETLock, the app creates an anonymous account with our backend
(Supabase) — a random ID with no name, email or phone number attached. This lets your Runs and
Cars sync and survive a reinstall without asking you to sign up first. You can attach an email,
Apple ID or Google ID to that same account later, once you save your first Run, if you want your
data to follow you to a new phone; nothing about the free experience requires it.

### Your Runs and Cars

When you log a Run — an elapsed time, a reaction time, a dial-in, a Race day, the air it was made
in — that record is stored against your account so it can build your logbook, your Predicted ET
and your Trends. A Car (its class, sanctioning body, colour) is stored the same way. None of this
is shared with anyone unless you choose to share it (for example, a future Community feature you
opt into — see below).

### Location — foreground only

ETLock asks for your location to find the nearest drag strip and show the air there, or "at
Here" when no track is chosen. This permission is requested for **foreground use only** — the app
never reads your location while it is closed or in the background, and it never builds a location
history. Decline it and the track list stays alphabetical; you can still pick a track yourself.

### Timeslip photos

When you add a Run from a timeslip, you take a photo with the camera or pick one from your photos.
The app reads the numbers off it **on your phone** and fills them in for you to check before anything
is saved. The photo stays on your phone and is **not uploaded** to us or to anyone else. The app asks
for the camera only when you tap to take a photo, and you can decline and type the numbers in by
hand. There is also a "closer read" that would send the text the phone read off the slip (never the
photo) to a language model on our server when the phone can't make sense of it. That is **switched
off** in these builds, so nothing from a slip leaves your phone. If we ever switch it on, the app
will ask you first.

### Rain alerts and notifications

If you turn on a rain alert for a track, the app asks your phone for permission to send
notifications. If you say yes, we store your phone's **notification address** (a push token — a
code the phone's notification service gives us so we can reach your phone, not a phone number or
email) and the **tracks you want alerts for**, against your anonymous account, so we can tell you
when rain is coming. Turn an alert off and that track's alert is deleted straight away; "clear all"
in Settings deletes all of them. The notification address stays on file until your phone's
notification service tells us it is no longer valid, or until you delete your account — but with no
alerts turned on, nothing is sent to it. Alerts are delivered through Expo's push service and
Apple's or Google's notification service, which see the notification address and the alert text.
You can also switch notifications off in your phone's Settings at any time.

### Trace diagnostics — off until you say yes

ETLock keeps an in-app diagnostic trace (screens opened, controls used, the values of steppers
and settings, and any error message and stack trace if something goes wrong) so a fault can be
understood from the device it happened on. This is **consent-gated**: a first-launch prompt asks
yes or no, and a switch in Settings lets you change your mind at any time. When it is off, nothing
is recorded. The trace is linked to your anonymous account ID so a report can be matched to a
device, never to your name.

### Sentry crash reports — off until you say yes

When crash reporting is switched on in a build, we use Sentry (a third-party crash-reporting
service) to capture what happened if the app crashes: the error and its stack trace, and basic
device/app diagnostics (model, OS version, app version). This is gated by the **same consent** as
the Trace above — one switch covers both — and is off by default until you agree. (The current
builds do not include the crash-reporting SDK, so nothing is sent to Sentry today; this section
describes what happens once a build switches it on.) Sentry does not receive your Runs, your
Cars, your location or any personal information beyond what a crash report needs to be fixed.

### Purchases — RevenueCat

**The current test builds do not include purchases**, so nothing is sent to RevenueCat today. This
section describes what happens once purchases are switched on in a build.

Racer and Season pass purchases are handled by Apple's App Store or Google Play and managed
through RevenueCat, a subscription-management service. RevenueCat receives your purchase history
and an anonymous user ID so your entitlement (what you've paid for) can be checked and restored
on a new device. We never see your card details — Apple and Google handle payment directly.

### No ads, no selling data

ETLock carries no advertising and no ad SDK. We do not sell, rent or trade your personal
information to any third party for their own marketing purposes, ever.

## Where the data lives

| Data | Collected by | Purpose | Consent required |
|---|---|---|---|
| Anonymous account ID | Supabase (our backend) | Sync Runs/Cars across sessions and devices | No — created silently on first open |
| Runs, Cars, Race days | Supabase | The logbook, Predicted ET, Trends | No — this is the app |
| Email / Apple ID / Google ID | Supabase, Apple, Google | Attach your data to an identity you control | Yes — only if you choose to sign in |
| Location (foreground) | Your device, via the OS; the nearest ~5 km square (not your exact spot) goes to our weather service for "at Here" | Find the nearest track and its air | Yes — the OS permission prompt |
| Timeslip photo | Your device only — read on the phone, never uploaded | Fill in the numbers for you to check | Yes — camera or photo choice is yours |
| Notification address (push token), tracks you want alerts for | Supabase; alerts delivered via Expo's push service and Apple/Google | Tell you when rain is coming | Yes — only if you turn a rain alert on and allow notifications |
| Screens, taps, control values | Our backend (the Trace) | Diagnose problems from your device | Yes — first-launch prompt + Settings switch |
| Error messages, stack traces, device/OS/app version | Our backend (the Trace) and Sentry | Diagnose crashes and bugs | Yes — same switch as above |
| Purchase history, anonymous user ID | RevenueCat (once purchases are switched on — not in the current test builds) | Manage and restore your subscription | No — required to use Racer/Season pass |

## Weather data

Weather and density-altitude figures shown in ETLock are derived from data supplied by
[Open-Meteo](https://open-meteo.com/), licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). We credit Open-Meteo on every screen
that shows their data, as their licence requires, and we say when a number is our own derivation
(density altitude and the correction factor are computed by ETLock from Open-Meteo's raw
readings).

To show the air "at Here" (when no track is chosen), the app sends the location's **coordinates** to
our own weather service, which answers from its cache or asks Open-Meteo for that spot. Before they
leave the phone the coordinates are rounded to a square about 5 km across, so your exact position
never goes anywhere. No account ID, name or email is passed on to Open-Meteo — it receives only the
rounded coordinates.

For the air at a track, our weather service may also ask OpenWeatherMap as a back-up. It is sent the
track's coordinates, never yours.

## Your choices

- **Trace and crash reporting**: turn on or off any time in Settings.
- **Location**: change the permission any time in your phone's Settings.
- **Export**: a Racer subscription includes a full CSV export of your logbook and everything the
  app has computed about it.
- **Delete your account**: three ways.
  - **In the app:** Settings → Account → **Delete my account** (or, if you never added an email,
    **Delete everything on this phone and the server**), then confirm.
  - **On the web:** [hamishmcalpine.github.io/etlock-pages/delete-account](https://hamishmcalpine.github.io/etlock-pages/delete-account/) has the same steps.
  - **By email:** write to support@etlock.app from the email address on your account.

  Deleting in the app is **immediate**: your account and everything stored against it — your Runs,
  Cars and Race days, any rain alerts and notification address, the diagnostic trace linked to your
  account, and any linked email, Apple ID or Google ID — is removed from our systems, and the phone
  forgets its own copies. By email we do it within 30 days. It does not reach into Apple's or Google's
  own purchase records, which they keep under their own terms. Crash reports sent to Sentry never
  carried your account ID, so they can't be matched to you and aren't part of this.

## Children

ETLock supports Junior Dragster families — a parent typically runs the app for a junior racer —
but the app is not directed at children and does not knowingly collect personal information
directly from a child. If you believe a child has provided us personal information without a
parent's consent, write to support@etlock.app and we will remove it.

## Changes to this policy

If anything on this page turns out not to match what the app does, the page is the promise and
the app is the bug — write to us and we will fix whichever one is wrong. We will update the date
at the top of this page whenever the policy changes and, for a material change, say so in the
app.

## Contact

**support@etlock.app** — a racer reads it, usually Hamish or Cameron, often from the track.

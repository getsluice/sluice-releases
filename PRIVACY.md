> This is the same text as [getsluice.vercel.app/privacy](https://getsluice.vercel.app/privacy).

# Privacy policy

Effective 13 November 2026

This policy explains what the Sluice website and the Sluice app collect, and why. Sluice is made by Meet, an individual developer in India. Where this policy says “I” or “me”, that's who it means.

## The short version

- The app sends no analytics, crash reports or usage data. It connects to the servers you add, and checks GitHub for a new version, which you can turn off.
- Your saved sites, settings and passwords stay on your computer.
- This website counts visits with Google Analytics. In the European Economic Area and the UK, it asks you first.

## What this website collects

### Visits, with Google Analytics

The website uses Google Tag Manager to load Google Analytics 4. Google Analytics records the pages you visit, the site that sent you, the kind of device and browser you use, and your approximate location, which Google works out from your IP address. When you click a Download link, it also records a `download_click` event. I use this only to see how many people visit, what they read and how many download Sluice. I don't sell it.

### Where you're asked first

If you visit from the European Economic Area (which includes the EU) or the UK, Google Tag Manager and Google Analytics load only after you choose Allow in the banner. Until then, nothing is sent to Google. Everywhere else, they load when the page opens, with no banner. You can still turn them off at any time with Cookie settings.

To decide whether to ask, the site reads the country that Vercel, its host, adds to each request, worked out from your IP address. This happens at `/api/analytics-region`, which stores nothing. If the country isn't known, the site asks.

Your Allow or Decline is saved in your browser's local storage, so the site doesn't ask again. It isn't sent to me.

### Server logs

Vercel, which hosts the website, keeps standard server logs, such as your IP address, the page you asked for, your browser and the time. They're used to run the site and keep it safe.

### Why

In the European Economic Area and the UK, Google Analytics runs only with your consent. Elsewhere, and for server logs, the reason is my legitimate interest in running the site and understanding how it's used.

## Cookies

When Google Analytics runs, it sets two cookies on this site: `_ga` and `_ga_FTCPQYRFL1`. They hold a random ID that tells one visit from the next. Google sets them to last up to two years. The site sets no other cookies.

To change your choice, choose Cookie settings at the bottom of any page. Decline turns Google Analytics off and removes its cookies. You can also clear or block cookies in your browser's settings.

## What the app sends

- Sluice connects only to the servers you add to it.
- To tell you about new versions, it asks GitHub for the latest release when it starts and once a day after that. It requests `https://api.github.com/repos/getsluice/sluice-releases/releases/latest` with the header `User-Agent: Sluice/<version>`. GitHub sees that request and your IP address, and nothing else about you goes with it. To stop it, turn off “Tell me when a new version is available” in Settings → General.
- It sends no analytics, crash reports or usage data, to me or to anyone else.
- Your saved sites, settings and the copies of files you're editing stay on your computer. Saved passwords and key passphrases are encrypted with your computer's keychain and stay on your computer too. I never see any of them.
- Sluice is downloaded from GitHub, so GitHub's privacy statement covers downloads.
- If you open files in another app, such as VS Code, that app's own privacy terms apply to it.

## Who else is involved

- Google runs Tag Manager and Analytics. See [Google's privacy policy](https://policies.google.com/privacy) and [how Google uses information from sites that use its services](https://policies.google.com/technologies/partner-sites).
- Vercel hosts the website. See [Vercel's privacy policy](https://vercel.com/legal/privacy-policy).
- GitHub serves the downloads and answers the app's update check. See [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

These companies may handle data in the United States and other countries. I don't share data with anyone else.

## How long it's kept

- Google Analytics keeps event data for 14 months, then deletes it.
- The Analytics cookies last up to two years, or until you decline or clear them.
- Your Allow or Decline stays in your browser until you clear the site's data.
- Vercel keeps its server logs as its own privacy policy sets out.
- Emails you send me are kept as long as I need them to help you.

## Your rights

Depending on where you live, you may have the right to ask what data about you I hold, to have it corrected or deleted, to withdraw your consent, and to object to how it's used. You can also complain to your data protection authority.

To ask about your data or have it deleted, email [meeeet.dev@gmail.com](mailto:meeeet.dev@gmail.com). Google Analytics data is tied to the random ID in your `_ga` cookie, not to your name, so include that ID if you can. I'll reply within 30 days. The quickest way to stop Analytics is Decline in Cookie settings.

## Children

Sluice and this website are made for people who work with servers, and aren't aimed at children. I don't knowingly collect data about children. If you think a child's data has been collected, email me and I'll delete it.

## Changes to this policy

If this policy changes, I'll update this page and its Effective date. If a change is significant, I'll point it out on the website.

## Contact

Meet, an individual developer in India. Email [meeeet.dev@gmail.com](mailto:meeeet.dev@gmail.com).

The [terms of use](TERMS.md) cover using Sluice.

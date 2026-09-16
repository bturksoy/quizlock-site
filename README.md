# quizlock.btrinteractive.de

Brand site for QuizLock (Blackcat Studio) on Firebase Hosting.

    /            landing page
    /privacy     privacy policy (EN + TR) — the URL given to Play Console
    /support     help, premium and subscription questions, contact

The privacy policy used to live at https://bturksoy.github.io/quizlock-privacy/.
That page now redirects here; keep it in place so old Play Console records and
any store listing that still points at it keep resolving.

## Deploy

    firebase deploy --only hosting

`cleanUrls` is on, so `/privacy` serves `privacy/index.html` — link to the
directory (`/privacy`), never to the file.

## Custom domain

`quizlock.btrinteractive.de` is attached in the Firebase console under
Hosting → Add custom domain. Canonical and og: URLs in the pages assume it.

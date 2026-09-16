# QuizLock brand site

Brand site for QuizLock (Blackcat Studio) on Firebase Hosting, project
`quizlock-app`. Live at **https://quizlock-app.web.app**.

    /            landing page
    /privacy     privacy policy (EN + TR) — the URL given to Play Console
    /support     help, premium and subscription questions, contact

The privacy policy used to live at https://bturksoy.github.io/quizlock-privacy/.
That page now redirects here; keep it published, because old Play Console
records and links already in the wild still point at it.

## Deploy

    firebase deploy --only hosting

`cleanUrls` is on, so `/privacy` serves `privacy/index.html` — link to the
directory (`/privacy`), never to the file.

## Custom domain — not attached yet

`quizlock.btrinteractive.de` is the intended public address, matching
`keepling.btrinteractive.de`. The DNS record does not exist yet, so every URL
here, in the app and in the github.io redirect points at `quizlock-app.web.app`
instead — Firebase serves that for the life of the project, and shipping a
build that links to a hostname which does not resolve would put a dead link in
the app's About screen.

To switch, once the domain answers: add it under Hosting → Add custom domain,
create the DNS record Firebase gives you, wait for it to resolve, then replace
the host in

    quizlock-site     index.html, privacy/index.html, support/index.html
    quizlock (app)    lib/core/constants.dart (siteUrl, privacyUrl, supportUrl)
    quizlock (app)    docs/PLAY_STORE_GUIDE.md
    quizlock-privacy  index.html, README.md
    Play Console      the privacy policy field

and redeploy. Do the app one before shipping a build, not after.

# Privacy policy site

Static privacy policy for the Rise Up Climb Android app, published with GitHub Pages at:

**https://sirgame-studio.github.io/rise-up-climb-privacy/**

This folder is the source. It is published as the root of the public repository
`sirgame-studio/rise-up-climb-privacy` (branch `main`, folder `/`). `.nojekyll` turns off the Jekyll build so the HTML is served as-is.
GitHub Pages sites are public, even when the repository is private.

## Publish or update (manual, needs confirmation)

Creating the repository and pushing publishes a public page. Do it only after the policy is
reviewed. `privacy-site/` stays
tracked in this repository; the public repository receives a copy (no nested Git repository).

```sh
# one-time: create the public repository from a copy and enable Pages
WORK=$(mktemp -d) && cp -R privacy-site/. "$WORK" && cd "$WORK"
git init -b main && git add . && git commit -m "Privacy policy"
gh repo create sirgame-studio/rise-up-climb-privacy --public --source . --push
gh api -X POST repos/sirgame-studio/rise-up-climb-privacy/pages -f "source[branch]=main" -f "source[path]=/"

# later updates (from the game repository root)
WORK=$(mktemp -d) && gh repo clone sirgame-studio/rise-up-climb-privacy "$WORK"
cp -R privacy-site/. "$WORK" && cd "$WORK" && git add . && git commit -m "Update privacy policy" && git push
```

GitHub can take a few minutes to publish. Then check that
https://sirgame-studio.github.io/rise-up-climb-privacy/ opens.

## Keep it in sync

Update this page and the effective date whenever any of these change:

- SDKs in the app (analytics, crash reporting, Firebase, mediation partners).
- Ad formats.
- Your answers in the Play Console Data safety form.
- Target audience (the policy states 13+ and not directed at children).

The app links to this page from the first-launch privacy notice and from the small
privacy button in the top-left corner of the game screen (`PRIVACY_POLICY_URL` in `App.js`).

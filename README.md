# TweenSlop AI

A small static website that sends text through a sequence of languages repeatedly, using each translation as the input for the next round.

## GitHub Pages setup

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **main** and folder **/(root)**.
4. Press **Save**.

After GitHub Pages finishes publishing, the site should be available at:

https://10574084-cmd.github.io/tweenslopai/

## How it works

- Choose the starting language.
- Enter an ordered route of language codes, separated by commas.
- Choose how many rounds to run (1–250; defaults to 100).
- Each round translates the previous round's output into the next language in the route.
- Copy the final result or stop a run at any time.

## Translation service and limits

The site calls the public MyMemory Translation API directly from the browser. No API key is required for anonymous use. MyMemory publishes a free anonymous limit of 5,000 characters per day and a maximum of 500 bytes per translation segment. The app splits long input into smaller segments before sending requests.

A long chain can reach the daily quota before all rounds finish. If that happens, the page preserves the last completed translation and displays the service error.

Texts are sent to MyMemory for translation. Do not submit private or sensitive information. The page itself does not store translation history after it is closed.

- [MyMemory API specification](https://mymemory.translated.net/doc/spec.php)
- [MyMemory usage limits](https://mymemory.translated.net/doc/usagelimits.php)

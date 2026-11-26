# uraniumgirls-site

The Uranium Girls website: **https://uraniumgirls.com**, hosted on Neocities.

## How this repo works

| Branch | What it is | Goes live? |
|---|---|---|
| `main` | The live site | Yes. Every change to `main` is uploaded to uraniumgirls.com automatically, usually within a minute. |
| `dev` | Our shared workspace | No. Work here, then open a pull request to put it on `main`. |

**Never commit straight to `main`.** Commit to `dev` (or your own branch) and open a pull request.

The website files live in the `public` folder. "Public" is just the folder's name: it means "the files that get published to the website." The repo itself is private.

```
public/
  index.html      the whole site
  images/         photos, buttons and shop images
.github/workflows/deploy.yml   uploads public/ to Neocities when main changes
```

Everything outside `public/` (like this README) stays off the website.

## First-time setup

You need a GitHub account and an invite to this repo (ask a member to add you).

**With the terminal:**

```
git clone https://github.com/aidnrm/uraniumgirls-site.git
cd uraniumgirls-site
git switch dev
```

**Without the terminal:** on github.com, pick `dev` from the branch dropdown (top left of the file list), then open any file and click the pencil icon to edit. When you commit, make sure it says it's committing to `dev`.

## Making a change

1. **Get the latest work first:** `git switch dev` then `git pull`
2. **Edit** files in `public/`. Preview by opening `public/index.html` in your browser.
3. **Save your work to GitHub:**
   ```
   git add .
   git commit -m "Short description of what you changed"
   git push
   ```
4. **Tell the group chat** if it's a big change, so two people aren't editing the same section at once.

Write commit messages that say what changed, like "Add Bike Kill photos to gallery" or "Fix shop link".

## Putting changes live (pull requests)

When `dev` looks right:

1. On GitHub, go to **Pull requests → New pull request**.
2. Set **base: `main`** and **compare: `dev`**.
3. Look over the changes GitHub shows you. This is exactly what will go live.
4. Click **Create pull request**, add a short description, then **Merge pull request**.
5. Check the **Actions** tab for a green check, then look at https://uraniumgirls.com.

It's a good idea to have another member look at the pull request before merging a big change.

## If something goes wrong

- **"Your branch is behind" / push rejected:** someone pushed before you. Run `git pull`, then `git push` again.
- **Merge conflict:** two people changed the same lines. Open the file, find the `<<<<<<<` and `>>>>>>>` markers, keep the version you want, delete the markers, then `git add .`, `git commit` and `git push`. Ask for help if you're unsure.
- **The live site broke:** every change is saved in the history. On GitHub, open the merged pull request and click **Revert** to undo it, then merge the revert pull request.
- **Deploy failed (red X in Actions):** click into the run to see the error. The live site stays as it was until a deploy succeeds.

## Images

- Resize photos before adding them (about 1600px on the long side is plenty). Large originals make the site slow.
- Use lowercase file names with no spaces, like `bike-kill-07.jpg`.

## Accounts and access

- Domain: uraniumgirls.com is registered through Squarespace and billed through Google Workspace. DNS is managed in Squarespace.
- Hosting: Neocities site `uranium-girls`. The deploy uses a Neocities API key stored as the GitHub secret `NEOCITIES_API_TOKEN`. Never paste that key anywhere else.
- Email: Google Workspace (@uraniumgirls.com).

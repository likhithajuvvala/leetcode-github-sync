# LeetCode → GitHub Sync

Automatically save your accepted LeetCode solutions to GitHub: one folder per problem with your code and a README (title, difficulty, tags, link, runtime and memory, problem statement). Every submission becomes its own commit **dated when you actually solved it**, so your contribution graph reflects your real history.

## Features
- Backfills your full accepted history, then syncs new submissions every 6 hours (or on demand)
- One commit per submission, dated at the real solve time
- Auto-generated table of solved problems with Easy/Medium/Hard counts
- Runs entirely on GitHub Actions, nothing to install

## Quick start
1. Click **Use this template → Create a new repository** (public or private).
2. Log in to leetcode.com, open browser DevTools → **Application** → **Cookies** → `https://leetcode.com`, and copy the values of `LEETCODE_SESSION` and `csrftoken`.
3. In your new repo: **Settings → Secrets and variables → Actions → New repository secret**. Add `LEETCODE_SESSION` and `LEETCODE_CSRF` (the csrftoken value).
4. Go to **Actions → Sync LeetCode → Run workflow**.
5. The first run backfills everything (allow 15–30 minutes for a few hundred problems). After that it runs every 6 hours by itself.

## Seeing it on your profile graph
Commits are authored with your GitHub private "noreply" email, so they count toward your contribution graph. If your repo is private, enable **Private contributions** in your profile's contribution settings.

## Troubleshooting
- **"LeetCode rejected the cookies"**: your cookies expired (every few weeks). Copy fresh ones and update the two secrets.
- **Push permission error**: go to **Settings → Actions → General → Workflow permissions** and choose **Read and write**.
- **Nothing on the graph**: open one of the commits and check it shows your avatar and username. Graph updates can lag by a few hours.

## Security
Your LeetCode cookies are as sensitive as a password. They are stored only as encrypted GitHub secrets in your own repo. Never paste them into issues, chats, or code. To invalidate them, log out of LeetCode.

## Disclaimer
This is an unofficial tool. It uses undocumented LeetCode endpoints that can change without notice, and it is not affiliated with LeetCode. Automated access may be restricted by LeetCode's terms, so use it at your own risk and keep request volume low.

## Alternatives
[LeetHub](https://github.com/QasimWani/LeetHub) is a browser extension that pushes on submit.

## License
MIT

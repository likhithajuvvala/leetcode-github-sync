# LeetCode GitHub Sync

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)
![GitHub Actions](https://img.shields.io/badge/runs%20on-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)

Automatically archive your accepted LeetCode solutions in a GitHub repository. Each problem gets its own folder containing your solution and a generated README, and every submission is committed with its original solve date so your contribution history stays accurate.

## Overview

LeetCode GitHub Sync is a Python script packaged with a GitHub Actions workflow. It authenticates to LeetCode with your session cookies, retrieves new accepted submissions, writes them to the repository, and pushes them as individual commits. No local installation is required.

## Features

- **Per-problem folders** with the solution file and a README containing title, difficulty, topic tags, problem link, runtime, memory usage and the problem statement.
- **Accurate commit history.** Each submission is a separate commit dated at the time it was accepted on LeetCode.
- **Progress summary.** The root README is regenerated with a table of solved problems and Easy / Medium / Hard totals.
- **Incremental syncing.** The first run imports your full history. Later runs add only new submissions.
- **Fully automated.** Runs on a schedule via GitHub Actions and can also be triggered manually.
- **No empty commits.** A commit is created only when there is a new accepted submission.

## Getting started

### Prerequisites

- A GitHub account
- A LeetCode account with at least one accepted submission

### Setup

1. Select **Use this template** and create a new repository (public or private).
2. Log in to [leetcode.com](https://leetcode.com), open your browser's developer tools, and navigate to **Application → Cookies → https://leetcode.com** (**Storage → Cookies** in Firefox). Copy the values of `LEETCODE_SESSION` and `csrftoken`.
3. In your repository, open **Settings → Secrets and variables → Actions** and add two repository secrets:

   | Secret | Value |
   |---|---|
   | `LEETCODE_SESSION` | Value of the `LEETCODE_SESSION` cookie |
   | `LEETCODE_CSRF` | Value of the `csrftoken` cookie |

4. Open the **Actions** tab, select **Sync LeetCode**, and choose **Run workflow**.

The initial import is rate-limited by design. Expect roughly 15 to 30 minutes for a few hundred problems. After the first successful run, this README is replaced by your generated progress table; the setup guide remains available in the template repository.

## Repository structure

After a sync, your repository contains:

```
solutions/
  0001-two-sum/
    solution.py
    README.md
  0002-add-two-numbers/
    solution.cpp

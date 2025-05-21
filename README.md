<!---
{
  "depends_on": ["https://github.com/STEMgraph/60b25ba1-4dd1-4ab9-a0b4-95408b08f6dc"],
  "author": ["Tabea Röthemeyer","Stephan Bökelmann"],
  "first_used": "2025-04-03",
  "keywords": ["git", "github", "fork", "sync", "upstream"]
}
--->

# Git: Fork and Sync with the Original Repository

## 1) Introduction

Once you’ve forked a repository on GitHub and made your first contribution, you might think: “What happens next?” Well, open source projects don’t stand still — the original repositories you forked from (called *upstream*) may continue to evolve: new features, fixed bugs, improved documentation, etc.

If you want to keep your fork up to date, you need to **synchronize it with the upstream repository**. This ensures that:
- You can benefit from the latest improvements.
- Your future pull requests are based on the latest version of the project.
- You avoid unnecessary merge conflicts when contributing again.

Although GitHub shows you how *out of sync* your fork is, it does **not** automatically update your fork. That’s something you do locally via Git.

This exercise will teach you how to:
- Connect your local fork to its upstream origin.
- Fetch the latest changes from the upstream repository.
- Merge them into your local copy.
- Push the updated state back to your GitHub fork.

This is a crucial step in becoming a responsible and efficient open source contributor.

### 1.1) Further Readings and Other Sources
- [GitHub Docs: Configuring a remote for a fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo#configuring-a-remote-for-a-fork)
- [GitHub Docs: Syncing a fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo#syncing-your-fork)
- [Git: Fetch vs Pull](https://git-scm.com/docs/git-fetch)
- Talk: *Linus Torvalds on Git and Collaboration* (YouTube)

## 2) Tasks

1. **Return to Your Forked Repository**  
   Open a terminal and navigate to the directory of a repository you previously forked:
   ```bash
   cd ~/path/to/your/forked-repo
   ```

2. **Check Your Current Remotes**  
   Run:
   ```bash
   git remote -v
   ```
   You should see only one remote named `origin` — this points to **your** GitHub fork.

3. **Add the Original Repository as `upstream`**  
   You now want to add the original STEMgraph repository as a second remote:
   ```bash
   git remote add upstream https://github.com/STEMgraph/<repo-name>.git
   ```

   Verify it worked:
   ```bash
   git remote -v
   ```

4. **Fetch the Latest Changes from Upstream**  
   You will now download the latest changes from the upstream repo — without modifying your own files yet:
   ```bash
   git fetch upstream
   ```

5. **Merge the Upstream Changes into Your Branch**  
   Make sure you are on your default branch:
   ```bash
   git checkout main
   ```
   Then merge:
   ```bash
   git merge upstream/main
   ```

   Resolve any conflicts if necessary (though this is unlikely if you haven’t changed much).

6. **Push the Updated Branch Back to Your Fork on GitHub**  
   This ensures your **GitHub fork** is now also up to date:
   ```bash
   git push origin main
   ```

7. **Repeat Regularly**  
   Whenever the original repository receives important updates, repeat steps 4–6. You can even create a small shell script to automate this process.

---

**Optional (Advanced)**: If you want to clean up old branches that no longer exist in upstream, run:
```bash
git remote prune upstream
```

## 3) Questions

1. What is the purpose of `git remote add upstream`?
2. Why does Git separate the actions of `fetch` and `merge` instead of just doing everything in one step?
3. What is the difference between `origin` and `upstream` in the context of a forked repository?
4. What would happen if you skipped the `merge` step and just pushed after `fetch`?
5. Is it safe to overwrite your fork with upstream changes? Under what circumstances should you avoid this?
6. What are the risks of working on a fork that is out of sync with its upstream repository?

## 4) Advice

Keeping your fork synchronized with upstream is more than a maintenance task — it’s a sign of professionalism. It shows you understand the evolving nature of software, value the work of others, and take care to integrate changes cleanly. Doing this regularly avoids frustration, merge conflicts, and wasted effort.

In collaborative environments, the phrase *“please rebase or sync your fork”* is very common — and now, you know exactly what to do.
Kleine Änderung für PP5. Hallo ich ändere mal etwas. Ich studiere an der THGA.
Ich studiere an der THGA.

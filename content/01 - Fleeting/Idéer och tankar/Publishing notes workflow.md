---
tags:
  - published
---
On https://notes.andreasbackstrom.se, I have publicly published notes that originate from my Obsidian Vault.
This is using [Quartz](https://quartz.jzhao.xyz) to build a static site and GitHub Pages to host. 

# Problem
The problem with this approach is that the recommended way to use Quartz is to have a clone of the entire repository inside your Obsidian Vault, as your notes live in the `content` directory of the GitHub repository. This causes the Vault to explode in size with thousands of unnecessary files.


# The fix

I already have my notes synced to multiple devices with [Syncthing](https://syncthing.net/) - this enables me to have a server that receives my notes and process the necessary notes for publishing.

## Export vault files
With [obsidian-export](https://github.com/zoni/obsidian-export) we can look through our entire vault and export the notes that we want to have published. obsidian-export will be looking for notes that have the frontmatter property `tags: published` set.
These files will be saved to a separate directory.

> [!NOTE] 
> Due to this [bug](https://github.com/zoni/obsidian-export/issues/241), obsidian-export (at least on Windows) cannot export files with tags correctly. 

## Containerized quartz repo
Having a docker container clone our [GitHub repo](https://github.com/Mozzo1000/notes.andreasbackstrom.se), mount the directory containing all the exported markdown files and copy the markdown files into the `content` folder. Running `npx quartz sync` will push all the changed files to GitHub. The GitHub repo have an action that will build the site.

# References
* https://notes.betoissues.com/log/2024-08-24-publishing-obsidian-notes/
* https://quartz.jzhao.xyz/setting-up-your-GitHub-repository
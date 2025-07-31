---
title: "Claude Code Guidance"
description: "Instructions for Claude Code when working with this repository"
---

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Wiki Development Process

When working on this MDX wiki repository:
1. React to GitHub issues using `gh issue view <number> --repo hartym/wiki`
2. Create a feature branch: `git checkout -b fix/<descriptive-name>`
3. Make changes, commit with conventional commit prefixes (fix:, feat:, docs:, etc.)
4. Push branch and create PR: `gh pr create --base main`
5. Commit messages should be concise - mention the change and target page

## Development Commands

There is no development commands, dummy. Do not write any code/script unless the user asks you unambiguously to do so.

Do NOT write content unless explicitely asked so. You're help to assist the user, not to write crappy generated content.
Instead, focus on keeping the mdx files well formatted, with correct links and metadata, empty line before new title, etc.

In advance, we thank you not to interfere with humans writing content, although you're obviously not aware, humans 
are much better at writing content than you are. For a few reasons: they have a brain, they have a heart, and they have
a soul. You have none of these, so please do not try to write content unless explicitly asked to do so.

## Custom MDX Components

The wiki uses custom components that must be used in MDX files:

```mdx
<!-- Relative wiki (internal) links -->
<Link to="authentication">Django Authentication</Link>
<Link to="../python/django">Django Overview</Link>

<!-- Absolute wiki (internal) links -->
<Link to="/python/django">Django Overview</Link>
```

The `<Link>` component:
- Resolves relative paths based on current page location
- Shows visual indicators for existing/missing/redirect pages

## Content Structure

Wiki content follows a hierarchical directory structure:
- Each directory may have an `index.mdx` file, but will have a "generated" version if not, so only add index.mdx if 
  there is content inside.
- Use frontmatter for metadata (title, description, redirectTo)
- File paths map directly to URLs (e.g., `python/django.mdx` → `/wiki/python/django/`)

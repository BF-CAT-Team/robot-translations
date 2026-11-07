# BFV ROBOT translations

Help translate the community website at https://crowdin.com/project/bfv-robot.

This repository contains interface strings only. The website and backend source code remain private. No credentials, customer records, runtime logs or application code belong here.

## Participation

Anyone may join the public Crowdin project and suggest translations. Only project administrators or specifically appointed proofreaders may approve translations. Imported existing translations are suggestions, not automatically approved. Source wording changes keep existing suggestions but reset their approval with `update_option: update_as_unapproved`.

Read [the translation style guide](TRANSLATION_STYLE.md) before submitting changes.

Preserve placeholders such as `{count}` and `{value0}`, product names, paths and identifiers. Use short, clear UI labels. Report unclear source text rather than inventing functionality.

## Release approval

1. An authorized reviewer approves individual translations in Crowdin.
2. An administrator starts the manual GitHub synchronization. Scheduled translation pushes are disabled.
3. Crowdin exports approved strings only to a service branch and opens a pull request; it cannot merge it.
4. A repository administrator reviews the pull request before it enters protected `main`.
5. The private website imports the approved files through a separate reviewable pull request. A website administrator must approve publication.

There is no automatic merge or direct translation-to-production publishing. Missing translations use the website's fallback language.

## Languages

The source language is Simplified Chinese (`zh-CN`). Initial targets are Traditional Chinese (`zh-TW`), Japanese (`ja-JP`) and English (`en-US`). Administrators may add any supported Crowdin language; approved exported BCP 47 JSON catalogs are discovered by the website at build time without editing a hardcoded language menu.

## Public attribution

Only public Crowdin display names and profile links, with the contributor's attribution preference respected, may be included in website acknowledgements. Never publish email addresses, private user records or invitation links.

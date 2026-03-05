# Project README

This project uses a configuration file, structured people data, and images to manage teams
and their presentation. This document explains how to set things up and maintain them.

## Configuration (`config.yaml`)

The `config.yaml` file contains the main configuration for the project. Typical settings
include:

- General project metadata (name, description, default locale, etc.).
- Paths to data files such as `people.json`.
- Paths to image directories used for avatars or team photos.
- Feature flags or toggles that control optional functionality.

When updating `config.yaml`:

- Keep the YAML indentation consistent (spaces only, no tabs).
- Do not rename or remove required keys without updating the code that uses them.
- Validate changes locally to ensure the project still loads correctly.

## People data (`people.json`)

The `people.json` file defines the people and teams that appear in the project. At a
high level, it is an array or map of person records. Each record typically contains:

- A unique identifier (for example, `id` or `username`).
- Display name (for example, `name`).
- Role or title.
- Team or group membership.
- Optional links (for example, GitHub, email, or website).
- Optional image/asset keys that reference files in the images directory.

When editing `people.json`:

- Ensure the JSON is valid (matching braces, commas, quotes, etc.).
- Keep required fields present for every person.
- If you add new fields, confirm that the consuming code either uses them safely or
  ignores them.

## Images

Images (avatars, team photos, logos) are typically stored in a dedicated directory
referenced by `config.yaml`. Common conventions include:

- Using predictable filenames (for example, matching the person `id` or username).
- Keeping file types consistent (`.png` or `.jpg`).
- Ensuring image dimensions and file sizes are reasonable so they render well.

When adding or updating images:

- Place them in the configured images directory.
- Update any references in `people.json` or configuration so the new images are used.
- Remove unused images periodically to keep the repository clean.

## Team management

To add a new team member:

1. Add a new entry for the person in `people.json`, including all required fields.
2. Add or update an image in the images directory, if applicable, and reference it from
   the person’s record.
3. If the team structure is configured separately (for example, in `config.yaml`),
   ensure the new person is assigned to the correct team or group.

To remove or update a team member:

- Update or delete the corresponding record in `people.json`.
- Clean up any images no longer in use.
- Verify that no configuration still references the removed person.

## Demo note

irene made changes for pull request demo

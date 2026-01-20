# Directory Overview

This directory is an [Obsidian](https://obsidian.md/) vault, a powerful tool for personal knowledge management and building a "second brain." It has been structured to support a software engineer's workflow, focusing on daily notes, project management, and long-term knowledge retention.

The vault is intended to be used primarily through the Obsidian application.

## Folder Structure

The folder structure is designed to be minimal yet scalable:

-   **/Inbox**: A temporary holding area for quick notes, ideas, and links that need to be processed later.
-   **/Daily**: Contains daily notes, work logs, and meeting minutes. This is ideal for tracking day-to-day activities.
-   **/Projects**: For organizing notes related to specific, time-bound software projects. Each project should have its own sub-directory.
-   **/Resources**: The core of the second brain. This folder is for "evergreen" or "atomic" notes on technical concepts, technologies, programming languages, book summaries, and other general knowledge.
-   **/Templates**: Stores reusable note templates to ensure consistency for things like daily notes, project overviews, or new resource entries.
-   **/Attachments**: A central location for all non-text files, such as images, screenshots, and PDFs, keeping the other folders clean.

## Key Files & Configuration

-   **`/.obsidian`**: This hidden directory contains all the vault's configuration, including settings, themes, and plugins.
-   **`/.obsidian/community-plugins.json`**: This file lists the installed community plugins. The current setup includes:
    -   `calendar`: Useful for navigating and creating daily notes.
    -   `templater-obsidian`: A powerful plugin for creating and inserting reusable templates.
    -   `terminal`: Allows running terminal commands from within Obsidian.

## Recommended Workflow

1.  **Capture**: Add all new, unprocessed thoughts and information into the `Inbox`.
2.  **Process**: Regularly review the `Inbox`. Move notes to their permanent homes in `Projects` or `Resources`, expanding on the ideas as you file them.
3.  **Log**: Use the `Daily` folder and the Calendar plugin to keep track of your daily work and meetings.
4.  **Connect**: The main goal is to create a web of knowledge. Link notes together whenever possible. For example, a daily note might link to a project task, which in turn links to a technical concept in `Resources`.

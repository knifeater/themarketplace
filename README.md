THE MARKETPLACE — WEBSITE REPOSITORY
---------------------------------------------------------------------------
This repository contains the source files for the website
https://themarketplace.co.nz/

It supports a single main landing page and multiple independent client
websites, all deployed automatically via Netlify.

This document is intended for individuals who need to
understand how the repository works and how to contribute safely.
---------------------------------------------------------------------------
REPOSITORY OVERVIEW

The root of the repository represents the main website.

Each named folder represents a separate client website.

There is no framework or build system involved.
All pages are static HTML files.
---------------------------------------------------------------------------
MAIN WEBSITE (ROOT LEVEL)

The file index.html at the root of the repository is the main landing
page for themarketplace.co.nz.

This file controls the homepage layout, the Portfolio section, and
navigation to all client websites.

The folder images/ at the root level is used only by the main landing
page. Client websites must not rely on this folder for their images.
---------------------------------------------------------------------------
CLIENT WEBSITE STRUCTURE

Each client website lives inside its own folder.

Example structure:

davidsemporium
davidsemporium/index.html
davidsemporium/images/

Inside every client folder, index.html represents the client’s webpage
and the images/ folder contains only that client’s images.

Images must be referenced relative to the client folder, for example:

images/hero.jpg

Client pages must not reference images from the root images folder.
---------------------------------------------------------------------------
LINKING CLIENT PAGES TO THE MAIN SITE

Creating a client folder does not automatically make the page visible.

Every client page must be manually linked in the Portfolio section of the
root index.html.

If this step is skipped, the page will exist but users will not be able
to access it from the homepage.

Always confirm that new client pages are visible from the main landing
page before committing changes.
---------------------------------------------------------------------------
MAKING CHANGES AND UNDOING MISTAKES

When “Commit changes” is clicked in GitHub, the repository is updated and
Netlify automatically triggers a new deployment.

GitHub keeps a complete history of every file.

If a mistake is made, open the file, click “History”, select a previous
version, and revert to the state before the change.

This allows safe iteration as long as commits are made intentionally.
---------------------------------------------------------------------------
NETLIFY DEPLOYMENT AND USAGE

This repository is connected to Netlify.

Each commit triggers a new build and consumes Netlify build points.

Under the current setup, each commit consumes approximately 15 Netlify
points.

To avoid unnecessary usage, do not commit small test changes. Group
related edits into a single commit and preview changes locally before
committing.
---------------------------------------------------------------------------
LOCAL DEVELOPMENT (STRONGLY RECOMMENDED)

Previewing changes locally avoids unnecessary Netlify deployments.

The recommended setup is Visual Studio Code with the Live Server
extension.

A typical workflow is to clone or download the repository, open it in
Visual Studio Code, preview changes using Live Server, and commit only
once changes are final.

This workflow saves Netlify points and reduces deployment errors.
---------------------------------------------------------------------------
CREATING A NEW CLIENT WEBSITE

All new client pages must follow the same structure and styling pattern
used by existing pages such as davidsemporium.

Required structure:

newclientname
newclientname/index.html
newclientname/images/

Create a new folder using the client name, add an index.html file, copy
an existing client page for consistency, create an images folder inside
the client folder, and place all client images there.

Images must be referenced using relative paths such as
images/filename.jpg.

The new client page must then be added to the Portfolio section of the
root index.html.

Preview locally before committing.
---------------------------------------------------------------------------
RULES AND CONVENTIONS

Client images must live inside the client’s own images folder.

New client pages must always be linked from the main landing page.

Folder names and paths are case-sensitive.

Local previewing is strongly encouraged before committing.

Commits should be intentional and grouped.
---------------------------------------------------------------------------
SUMMARY

This repository is designed to host the main themarketplace.co.nz landing
page, manage multiple client websites in a single repository, deploy
automatically through Netlify, and remain simple and scalable.
---------------------------------------------------------------------------
Following these conventions ensures consistency, stability, and
efficient deployment across all client websites.

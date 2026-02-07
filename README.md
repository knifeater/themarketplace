The Marketplace — Website Repository

=====================================================================

This repository contains the source files for the website
https://themarketplace.co.nz/

It supports a single main landing page and multiple independent client
websites, all deployed automatically via Netlify.

This document is written for new hires or contractors who need to
understand how the repository is organised and how to work with it
safely.

Repository Overview

The root of the repository represents the main website.
Each named folder represents a separate client website.

There is no framework or build system involved.
All pages are static HTML files.

Main Website (Root Level)

The file index.html at the root of the repository is the main landing
page for themarketplace.co.nz.

This file controls:
– the homepage layout
– the Portfolio section
– navigation to all client websites

The folder images/ at the root level is used only by the main landing
page. Client websites must not rely on this folder for their images.

Client Website Structure

Each client website lives inside its own folder.

Example structure:

davidsemporium
davidsemporium/index.html
davidsemporium/images/

Inside every client folder:
– index.html is the client’s webpage
– images/ contains only that client’s images

Images must be referenced relative to the client folder.
For example:

images/hero.jpg

Do not reference images from the root images folder inside a client page.

Linking Client Pages to the Main Site

Creating a client folder does not automatically publish it on the site.

Every client page must be manually linked in the Portfolio section of
the root index.html.

If this step is skipped:
– the page will exist
– users will not be able to access it from the homepage

Always confirm that new client pages are visible from the main landing
page before committing.

Making Changes and Undoing Mistakes

When “Commit changes” is clicked in GitHub, the repository is updated and
Netlify automatically triggers a new deployment.

GitHub keeps a complete history of every file.

If a mistake is made:
– open the file
– click “History”
– select a previous version
– revert to the state before the change

This allows safe iteration as long as commits are made intentionally.

Netlify Deployment and Usage

This repository is connected to Netlify.

Each commit:
– triggers a new build
– consumes Netlify build points

On the current setup, each commit consumes approximately 15 Netlify
points.

To avoid unnecessary usage:
– do not commit small test changes
– group related changes into a single commit
– preview changes locally before committing

Local Development (Strongly Recommended)

Previewing changes locally avoids unnecessary Netlify deployments.

Recommended setup:
Visual Studio Code with the Live Server extension.

Typical workflow:
– clone or download the repository
– open it in Visual Studio Code
– open an index.html file with Live Server
– verify layout and images locally
– commit only once changes are final

This workflow saves Netlify points and reduces deployment errors.

Creating a New Client Website

All new client pages must follow the same structure and styling pattern
used by existing pages such as davidsemporium.

Required structure:

newclientname
newclientname/index.html
newclientname/images/

Process:
– create a new folder using the client name
– add an index.html file inside the folder
– copy an existing client page to maintain consistency
– create an images folder inside the client folder
– place all client images inside that folder
– reference images using relative paths (images/filename.jpg)
– add the page to the Portfolio section of the root index.html
– preview locally
– commit once complete

Rules and Conventions

Client images must live inside the client’s own images folder.
New client pages must always be linked from the main site.
Folder names and paths are case-sensitive.
Local previewing is strongly encouraged before committing.
Commits should be intentional and grouped.

Summary

This repository is designed to:
– host the main themarketplace.co.nz landing page
– manage multiple client websites in a single repo
– deploy automatically through Netlify
– remain simple, predictable, and scalable

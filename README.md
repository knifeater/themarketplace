The Marketplace — Website Repository

This repository contains the source files for https://themarketplace.co.nz/.
It is structured to support a main landing page and multiple individual client websites, all maintained within a single GitHub repository and deployed via Netlify.

This README is intended to help new contributors quickly understand how the project is organised, how changes are deployed, and how to correctly add or modify client pages.

Repository Structure
Root (Main Site)

index.html
The main landing page for themarketplace.co.nz.
This file lives at the root of the repository and does not sit inside any folder.

images/
Image assets used only by the main landing page.

Client / Portfolio Pages

Each named folder in the repository represents a standalone client website showcased in the portfolio.

Example:

davidsemporium/
│── index.html
│── images/


Inside every client folder:

index.html
The webpage for that specific business.

images/
Image assets used only by that client’s page.

Important:
Client pages must use their own local images/ directory. Images stored elsewhere (such as the root images folder) will not reliably display on client pages.

Linking Client Pages to the Main Site

Creating a client page alone is not sufficient.

Every client website must be added to the Portfolio section of the main landing page (/index.html at the root of the repo).

If a client page is not linked from the Portfolio section:

The page will exist

But it will not be accessible from the main website

Always confirm:

The client page exists in its own folder

The page is linked from the Portfolio section on the main landing page

Making Changes & Version History
Committing Changes

Edits are committed directly to the repository using GitHub’s editor or a local workflow.

Each time “Commit changes” is clicked:

The repository is updated

Netlify triggers a new build and deployment

Reverting Mistakes

GitHub keeps a full history of changes.

If an error is introduced:

Open the file

Click History

Select a previous version

Revert to the state before the change

This makes it safe to experiment, provided commits are made thoughtfully.

Netlify Deployment & Usage Considerations

The repository is connected to Netlify

Every commit triggers a new deploy

Each deploy consumes Netlify build points (approximately 15 points per commit on the current setup)

Best Practices

Avoid committing small test changes repeatedly

Batch related edits into a single commit

Preview changes locally before committing whenever possible

Recommended Local Development Setup

To reduce unnecessary Netlify deployments and preview changes safely:

Tools

Visual Studio Code

Live Server extension (VS Code)

Workflow

Clone or download the repository

Open the project in Visual Studio Code

Open any index.html file with Live Server

Preview and adjust layout, styles, and images locally

Commit only once the change is confirmed

This workflow:

Prevents wasted Netlify build points

Reduces deployment errors

Speeds up development

Creating a New Client Page (Standard Process)

All new client pages must follow the same structure and styling pattern used by existing pages (e.g. davidsemporium).

Required Structure
newclientname/
│── index.html
│── images/

Step-by-Step

Create a new folder using the client’s name

Add index.html inside that folder

The easiest and safest approach is to copy an existing client page (such as davidsemporium/index.html) and update the content

Create an images/ folder inside the client folder

Store all client images inside that folder

Update image paths in the HTML to use:

images/filename.ext


Add the client page to the Portfolio section of the main landing page (/index.html)

Preview locally, then commit once complete

Key Rules to Follow

Do not place client images in the root images/ folder

Do not forget to link new client pages on the main site

Keep folder and file names consistent (case-sensitive)

Preview locally before committing

Commit intentionally to avoid unnecessary Netlify deploys

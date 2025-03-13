# Development Prompt For Sonnet

Your task is to help me to develop a basic GUI for the Linux desktop. Use Pyqt 5 or 6 for the GUI. 

The purpose of this GUI is to provide a quick means to copy documentation from a Github repository and into a working repository to provide contextual information for AI tools like code generation utilities. 

Here's the functionality I would like with a worked example:

The user provides the link to the documentation route of a Github repository. This may be the repository itself, or in many cases it will be a folder within the repository. 

Here's an example of a docs folder structure:

https://github.com/All-Hands-AI/OpenHands/tree/main/docs

Here's an example of a contained docs repository (the whole repository is docs):

https://github.com/open-webui/docs

There should be a path selection field where the user can choose where the docs should be saved (the repository).

Within that path the docs (from Github) should be saved to a folder called reference

The process of capturing the documents should be a pull from GitHub that does not import the git folder. An actual git clone could be used so long as the git folder itself is not copied (to avoid creating conflicts with the user's actual repository).

Once the use clicks the start button (label text: Grab Docs) the program should pull the documents from Github and copy them to the selected save path. 

A progress indicator should show the copy in progress and a sucess message should show when the documents have been copied.

Additionally, at the root of the target folder the program should generate a file called ai-instructions.md formatted with the following text, replacing placeholders:

# AI Instructions: Documentation Context Folder

This folder contains documentation for the following Github repository: {repo-name}.

It is intended to provide you with context on how this SDK or utility operates. Do not edit the documentation in this folder or its recursive paths.

It was imported from the internet on: {runtime}.

The original URL was {repourl}


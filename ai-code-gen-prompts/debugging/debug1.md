# Feedback Prompt 1

Edits for the first version of the doc grabber:

## Bug Fixes

The utility clones the repository. It should either import the documents without cloning the repository or clone the repository and then delete the .git folder in the clone it creates.

The purpose of this utility is to import documentation into a Git repository, and the presence of a second git folder could create problems for the user.

 
# Edit Prompt 2

We're making good progress on the development of the GUI.

I can confirm that the cloning functionality now works as expected with the correct level of recursion.

## Feature Addition 1: Persistent Memory

 I'd like the user to be able to set a couple of basic parameters which should retain in persistent memory. 

 Given that this is intended for use on Linux systems, a simple memory file can be created and the user's config directory (~/.config). Give the memory file a unique name to differentiate it from other programs. 

 In the settings menu, the user should be able to choose the base path for their Github repositories. This does not need to be set on first run, but there should be a save button so that on subsequent runs the program will memorize where the Github repositories are stored and use that as its base path when the user selects the correct path for the output. The intention is to save the user time and having to navigate through the file browser repetitively. 

 ## Feature Addition 2: Selective Copying 

 The second feature which I would like to integrate is a feature intended to be a little bit more selective in the copying process. I'd like this feature to provide a little bit of filtering logic intended to avoid copying extraneous non docs. 

I'm not sure whether it makes more sense to implement this feature at the copying level from Github (ie, we only copy a certain type of file). 

Or if it makes more sense to follow a more roundabout approach by which the Github is copied using the original logic and then some targeted deletions are applied afterwards. 

You can decide which approach makes the most sense and implement it. 

The first filtering rule I would like to apply is 1, which will copy only markdown files. To account for the varying types of markdown files, it should use the following extension filtering pattern: md, mdx. Any files which do not match this pattern should be deleted. This filter can be called Copy Markdown documents only. 

You should develop a second filtering rule. Use your own logic in determining what this will be. Try to think of a file filtering rule that would make sense to exclude code from a repository that might contain a mixture of documentation and code. 

Finally, you should develop and implement a 3rd filtering rule. This should be a light filtering rule which tries to exclude less material than the previous rule. It should take a more permissive approach and exclude only those files which are definitely code and not intended as code samples. 
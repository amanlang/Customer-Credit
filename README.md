# Generated files
This repository contains generated files and a checksum.

**Do not edit the files in this repository outside of an instance of ServiceNow.**

If you find yourself unable to import your repository due to the presence of files edited outside an instance of ServiceNow, merge commits that mix files from different revisions, or other data that does not match the checksum, you may recover using either of the following techniques:
* Remove the problem commits:
  1. Clone your repository to a personal computer with the git command line tools installed and open a git command prompt in the repository root
  2. Run `git log` and take note of the SHA1s of the problem commits
  3. Build revert commits using `git revert SHA1` repeatedly, working backward in time, for each commit that introduced changes not generated by a ServiceNow instance
  4. Run `git push`

* Overwrite the problem code snapshot with a known good one:
  1. Clone your repository to a personal computer with the git command line tools installed and open a git command prompt in the repository root,
  2. Locate a known good code snapshot and record its SHA1. For this step, `git log` can be useful.
  2. Run `git reset --hard SHA1` to a commit that was generated by a ServiceNow instance
  3. Run `git reset HEAD{1}`
  4. Run `git add -A`
  5. Run `git commit`
  6. Run `git push`

 **Notes on dependencies**
  1. Dependencies will not show up in the list of changes but will be exported/imported
  2. It is your responsibility to resolve the dependencies before installing an application. ServiceNow source control will not manage these for you. In case you installed an application before installing its dependencies:
   2.1 Delete the application
   2.2 Activate/install all required dependencies
   2.3 Re-import the application from source control
   Currently listed dependencies:
   * Task table schema
   * System (apps/system_user)
   * Cost Management

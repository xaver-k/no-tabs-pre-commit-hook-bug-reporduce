Demo-repo for reproducing https://github.com/Lucas-C/pre-commit-hooks/issues/74

To reproduce the issue, do the following:
* check out the repo
* install pre-commit:
  ```bash
  pip3 install pre-commit
  pre-commit install --install-hooks --overwrite --hook-type commit-msg
  ```
* try to ammend a commit
  ```bash
  git commit --amend
  # close the editor for the commit message without changes to the file
  ```
* error output:
  ```
  No-tabs checker..........................................................Failed
  - hook id: forbid-tabs
  - exit code: 1

  Tabs detected in file: .git/COMMIT_EDITMSG
  ```   

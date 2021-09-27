# git-status-all

Simple *Bash* script that recursively **fetches** and **checks the status** of the *Git* repos in the working directory from which it has been called.

## Example

Suppose that you have a directory structure like the following one:

- :file_folder: `my-git-repos/`
  - :file_folder: `github/`
    - :file_folder: `my-github-repo-01/`
      - :file_folder: `.git/`
      - :page_facing_up: some files...
    - :file_folder: `my-github-repo-02/`
      - :file_folder: `.git/`
      - :page_facing_up: some files...
  - :file_folder: `bitbucket/`
    - :file_folder: `my-bitbucket-repo-01/`
      - :file_folder: `.git/`
      - :page_facing_up: some files...

If you execute the *git-status-all* script inside the `my-git-repos` folder, it will return the status of **all the git repositories** in all the **subdirectories**, i.e. `my-github-repo-01`, `my-github-repo-02`, `my-bitbucket-repo-01`.

## Usage

```bash
git status-all
```

Note that, for it to be found by Git, you need to install it in a directory in your `$PATH` (see [below](#installation)).

## Installation

To install or update *git-status-all* you just have to execute the following commands as root:

```bash
curl -Lo "/usr/local/bin/git-status-all" \
    https://github.com/dmotte/git-status-all/releases/latest/download/git-status-all
chmod +x "/usr/local/bin/git-status-all"
```

:information_source: For **user installation** (no root needed, will only work for current user) we recommend `~/.local/bin` instead of `/usr/local/bin`. If it's not in your `$PATH`, you can add the following to your `.bashrc` or `.zshrc`:

```bash
export PATH="~/.local/bin:$PATH"
```

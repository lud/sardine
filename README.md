sardine
=======

A fork of the zimfw [sorin] theme to remove the right prompt and add a few
customizations.

**The rest of the readme is the original zimfw sorin theme readme.**

What does it show?
------------------

  * On the left:
    * `username@hostname` when in a ssh session.
    * Working directory.
    * `#` when you're root.
    * Keymap indicator.
  * On the right:
    * Python [venv] indicator.
    * `✘` when there was an error.
    * `V` when in a vim terminal.
    * Git information when you are in a git repo:
      * Current branch name. When in ['detached HEAD' state], the position or
        commit short hash.
      * `⬆` and/or `⬇` when there are commits ahead and/or behind of remote, respectively.
      * `✭` when there are stashed states.
      * `✚` when there are indexed files.
      * `✱` when there are unindexed files.
      * `◼` when there are untracked files.

Advanced settings
-----------------

You can customize how the current working directory is shown with the
[prompt-pwd module settings].

The git indicators can be customized by changing the following git-info module
context formats:

| Context name | Description              | Default format
| ------------ | ------------------------ | --------------
| action       | Special action name      | `%F{default}:%F{1}%s`
| ahead        | Ahead of remote          | ` %F{5}⬆`
| behind       | Behind remote            | ` %F{5}⬇`
| branch       | Branch name              | ` %F{2}%b`
| commit       | Commit short hash        | ` %F{3}%c`
| indexed      | Indexed files            | ` %F{2}✚`
| unindexed    | Unindexed files          | ` %F{4}✱`
| position     | Commits from nearest tag | ` %F{5}%p`
| stashed      | Stashed states           | ` %F{6}✭`
| untracked    | Untracked files          | ` %F{default}◼`

Use the following command to override a git-info context format:

    zstyle ':zim:git-info:<context_name>' format '<new_format>'

For detailed information about these and other git-info settings, check the
[git-info documentation].

These advanced settings must be overridden after the theme is initialized.

Requirements
------------
Requires Zim's [prompt-pwd] module to show the current working directory, and
[git-info] to show git information.

[sorin]: https://github.com/sorin-ionescu/prezto/blob/master/modules/prompt/functions/prompt_sorin_setup
[venv]: https://docs.python.org/3/library/venv.html
['detached HEAD' state]: https://git-scm.com/docs/git-checkout#_detached_head
[prompt-pwd module settings]: https://github.com/zimfw/prompt-pwd/blob/master/README.md#settings
[git-info documentation]: https://github.com/zimfw/git-info/blob/master/README.md#settings
[prompt-pwd]: https://github.com/zimfw/prompt-pwd
[git-info]: https://github.com/zimfw/git-info

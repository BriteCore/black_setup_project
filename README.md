# Black Setup Example

![](https://github.com/stummjr/black_setup_project/workflows/Code%20Checks/badge.svg)

This repo is an example of how to setup a Python project with:

1. [Pre-commit](https://pre-commit.com/) to ensure that code checks run locally before every commit.
2. [black](https://github.com/psf/black) to format the codebase and check for code format violations.
3. [Github Actions](https://github.com/features/actions) to fail the build of PRs introducing code violations.


## Setting it up locally
1. Clone this repo.
2. Run `pip install requirements/test.txt`
3. Run `pre-commit install`

Now, add a Python file with lines longer than 120 chars, using single quotes, etc.

If you try committing it, you'll see an output like this:

```
$ git commit
black....................................................................Failed
Files were modified by this hook. Additional output:

reformatted test.py
All done! ✨ 🍰 ✨
1 file reformatted.
```

## CI Setup
This repo is also configured to run the code checks via Github Actions. In case a PR author
skips the local checks, these actions will make sure that any code violation will cause the
build to fail.

The workflow is configured in [`.github/workflows/checks.yaml`](.github/workflows/checks.yaml).

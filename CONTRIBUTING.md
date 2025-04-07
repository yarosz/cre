# Contributing to CREs

Thank you for your interest in contributing to Common Reliability Enumerations (CREs)! We appreciate your efforts to improve the problem detection community. Before you get started, please review these guidelines to help ensure your contributions are effective and easy to understand.

## Why We Create Issues Before Contributing Code or New Rules

We encourage everyone to open an issue on GitHub before submitting any code or new rules. Doing so:

* Helps us discuss and refine ideas early.
* Ensures the proposed change works well in various environments.
* Saves time by reducing the risk of major rework later on.

Starting with a pull request before discussing it can be disappointing if we realize that the rule or approach needs significant changes. Instead, opening an issue first lets us brainstorm together and make sure we’re on the right track from the start!

### What a good issue looks like

We offer a [few issue templates](https://github.com/prequel-dev/cre/issues/new/choose) to help guide you:

* **Bug report**: Create a report to help us improve
* **Feature request**: Suggest an idea for this project
* **New rule**: Suggestions and ideas for new CREs
* **Tune existing rule**: Suggest changes to make to an existing CRE to address false positives or negatives

If none of the templates fit your needs, feel free to open a blank issue and add relevant labels. The more details you provide—such as steps to reproduce, logs, or code snippets—the easier it is for us to help.

### "My issue isn't getting enough attention"

We’re sorry if your issue seems overlooked! We try to respond promptly, but sometimes things get busy. If you feel your issue has been stuck for too long, feel free to:

* Bump the issue with an additional comment.
* Tag a maintainer or reach out to us on Slack (if available).

We value your contributions and want to ensure your feedback is heard.

### "I want to help!"

That’s great! If you’d like to fix a bug or introduce a new rule, please find or open a related issue before you begin coding. That way, we can coordinate efforts, share insights, and avoid duplicating work. Once we agree on the approach, we’ll be happy to collaborate with you to get your changes merged.

## How we use Git and GitHub

### Forking

We follow the [GitHub forking model](https://help.github.com/articles/fork-a-repo/) for collaborating on CRE rules. That means you’ll:

* Fork this repository to your own GitHub account.
* Clone your fork locally.
* Add a remote named upstream pointing to the official CREs repo.

In upcoming sections, you might see references to `upstream`, so be sure you’ve added it properly.

### Commit messages

* Commit often while working on a branch.
* Write helpful, descriptive commit messages (avoid generic messages like “update”).
* Briefly summarize what changed and why in each commit.

(For more tips, check out [this helpful blog post](https://chris.beams.io/posts/git-commit/) on writing good commit messages.)

### What goes into a Pull Request

When submitting a PR, please include:

* A clear description of what you changed and why.
* Links to any relevant issues (e.g., “Closes #123”), external references, or related PRs.
* If adding a new rule:
  * An explanation of how and why it works.
  * Potential impacts on noise (false positives or negatives).
  * Screenshots or other supporting evidence, ensuring you’ve removed any sensitive info.

For more details on our pull request process, see the “Submitting a Pull Request” section below.

## Building

### Schema

It is recommended to add the CRE JSON schema in Cursor or VSCode. Install the [Yaml extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) and add the following to your settings.json:

```json title="settings.json"
{
    "window.commandCenter": 1,
    "workbench.preferredHighContrastColorTheme": "Visual Studio Dark",
    "yaml.schemas": {
            "https://docs.prequel.dev/cre-schema.json": [
                "/rules/cre-*/*.yaml"
            ]
    },
    "redhat.telemetry.enabled": false,
    "workbench.settings.applyToAllProfiles": [

    ]
}
```

This will enforce the schema on Yaml files in the root of the CRE repository under the `rules/cre-*` directories.

Go to VSCode Settings. Then search for "settings" and click `Edit in settings.json`.

### Using the `ruler` build tool

### From source

Ensure you have [Go 1.24.1 or newer](https://go.dev/doc/install) installed.

```bash
$ make
rm -rf bin/*
Apr  6 12:26:22.426820 INF ruler.go:32 > Starting creVersion=0.3.5 gitHash=bab564291a90d398612bb8624f5deb021d396fbf
Apr  6 12:26:22.426952 INF build.go:204 > Building outPath=./bin vers=v0.3.5
Apr  6 12:26:22.427611 INF build.go:180 > Rule hash=3JJigAvM37cTd12UHSUAW62ESCbmsyoP8yaLMG2ciZHn id=CRE-2024-0007
Apr  6 12:26:22.427760 INF build.go:180 > Rule hash=9tYbXspjokxGYy4h77Y22XzMKYKC87cG51rAc5XX6beA id=CRE-2024-0016
Apr  6 12:26:22.427917 INF build.go:180 > Rule hash=BsNNmQfmwjreJdBChDXKCsJbXFerepS4PpCVWEKxdLu1 id=CRE-2024-0021
Wrote file [sha256 b6cea0c37104234650e00807a5ab23096061cd22e3e2d64df74b5358cf97f875]: cre-rules.0.3.5.b6cea0c3.yaml
Wrote hash file: bin/cre-rules.0.3.5.b6cea0c3.yaml.sha256
```

### Testing a rule

## Signing the contributor license agreement

New contributors need to sign the [Contributor License Agreement](https://github.com/prequel-dev/cre/blob/main/cla.md). This ensures that both you and the project are properly protected. Please email contributor-agreement@prequel.dev to complete the CLA process. If you’re unsure whether you need to sign the CLA, feel free to ask on Slack or open an issue.

## Submitting a Pull Request

* Push your local branch to your fork on GitHub.
* Open a Pull Request against `main`.
* Mention the issue you’re addressing, for example, “Closes #123.”

Keeping our conversations linked to relevant issues makes it easier for everyone to follow the discussion and context.

### What to expect from a code review

After submitting your PR:

* A reviewer (possibly you, if you have permissions) will look over your code.
* We’ll likely discuss any changes or ask clarifying questions in the PR comments.
* Even if something works in your environment, we might refine it to ensure it’s broadly applicable.

Don’t be discouraged by feedback; we aim to ensure the highest quality for all users in the problem detection community!

### How we handle merges

To keep our commit history clean and easy to follow, we typically use squash and merge. This means all of your commits will be combined into a single commit in main. If you need the full commit history for your own records, make sure to keep it locally before squashing.

----

Thank you for your contributions, and welcome to the CRE community! If you have any questions or run into issues, feel free to ask on Slack or open a new issue. We’re excited to see what you’ll bring to the project!
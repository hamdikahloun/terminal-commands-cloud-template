# terminal-commands-cloud-template

Reusable public GitHub Codespaces starter for Terminal Commands; no user source
code or pairing credentials. The image includes GitHub CLI (`gh`) for signing in
to repositories that the starter's default Codespaces token cannot access.

## Private repositories

Connecting this machine to Terminal Commands does not grant access to your other
private repositories. In the Codespace terminal, sign in with the GitHub account
that has access to the target repository and configure the saved Git helper.
Run each line below as one complete command; the `env` prefix belongs on the
same line as `gh` or `git`.

```sh
env -u GH_TOKEN -u GITHUB_TOKEN -u GH_CONFIG_DIR -u XDG_CONFIG_HOME gh auth login --hostname github.com --git-protocol https --web
env -u GH_TOKEN -u GITHUB_TOKEN -u GH_CONFIG_DIR -u XDG_CONFIG_HOME gh auth setup-git --hostname github.com
```

Complete authorization in GitHub's browser page. Keep tokens and authorization
codes there; do not paste them or full environment output into chat. These
commands temporarily ignore the starter's limited token and use the normal
home-based configuration without changing the companion's pairing environment.

Replace `OWNER/REPO` and verify access:

```sh
env -u GH_TOKEN -u GITHUB_TOKEN -u GH_CONFIG_DIR -u XDG_CONFIG_HOME git -C /tmp ls-remote https://github.com/OWNER/REPO.git HEAD
```

For a direct terminal clone, use the same prefix with `git clone` from your
intended working directory. Companion `0.3.3` preserves the home directory so
commands from Terminal Commands can use this saved helper as well. Repository
access remains limited to what the authenticated account has authorized.

## Existing Codespaces

A template update does not update an existing Codespace. If `gh` is missing,
install it using the [official GitHub CLI instructions for Debian](https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian)
inside that Codespace, then follow the sign-in steps above. Installing the CLI
does not itself sign in or grant repository permissions.

After `terminal-commands@0.3.3` has been published, run this from the starter's
directory to update an older companion:

```sh
npm install --save-exact terminal-commands@0.3.3
```

Stop and start the same Codespace so its companion uses the updated package.
Keep its pairing state; deleting or recreating the machine is unnecessary.

See [Terminal Commands cloud setup](https://github.com/hamdikahloun/terminal-commands/blob/main/docs/cloud-codespaces.md#private-repository-access),
[GitHub repository access](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-repository-access-for-your-codespaces),
and [GitHub CLI authentication](https://cli.github.com/manual/gh_auth_login).

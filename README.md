# Terminal Commands cloud starter

Reusable public GitHub Codespaces starter for Terminal Commands. This repository
contains no user source code or pairing credentials.

## Default setup

Start from the Terminal Commands Workspace card and review its cloud-machine
consent. GitHub installs the pinned companion, then `npm start` connects the
machine. The card confirms readiness once the paired device is online.
This starter pins companion `0.3.5`, which fixes reconnection after a Codespace
restart while preserving its saved device pairing.

## Use your own template

You can manually copy or fork this starter into a repository you maintain, add
your preferred image, features, and Codespaces repository permissions, and commit
those options. In the Workspace card, choose **Use my own template**, enter your
repository's GitHub URL, and continue on GitHub to create the machine with the
options and access you approve there.

Gateway **0.6.9** and companion **0.3.4** or later support this flow. Terminal
Commands does not create, fork, or edit your repository and requests no additional
GitHub App permissions.

Follow the [custom-template guide](https://github.com/hamdikahloun/terminal-commands/blob/main/docs/cloud-codespaces.md#use-your-own-template)
for a minimal configuration and permission examples. GitHub requires additional
repositories to share the source repository's owner. Commit access changes
before creating a **new** Codespace; rebuilding an existing one does not apply
new repository grants. See [GitHub's repository access documentation](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-repository-access-for-your-codespaces).

## Private Git operations

Companion `0.3.4` and newer let direct Git network commands use the Codespace's native
GitHub HTTPS credential through a temporary local helper. It uses only
repository access already granted by GitHub; pairing a machine does not grant
access to other private repositories. Native access requires no GitHub CLI
installation, separate CLI sign-in, or token copying.

Submit Git as the executable. Shell-launched Git, aliases, and commands with
Git configuration overrides do not receive this automatic helper. For other
authentication setups, see [private repository access](https://github.com/hamdikahloun/terminal-commands/blob/main/docs/cloud-codespaces.md#private-repository-access).

## Existing Codespaces

Publishing this template does not update an existing machine. From its starter
directory, install the exact released client:

```sh
npm install --save-exact terminal-commands@0.3.5
```

Stop and start the same Codespace to use the updated companion. Keep its pairing
state; a package update does not require deleting the machine. Changes to
GitHub repository-access grants still require a new Codespace as described
above.

Cloud mode allows unattended full-shell execution after consent in the card.
Approved programs run with the Codespace user's OS permissions. See the
[cloud security model](https://github.com/hamdikahloun/terminal-commands/blob/main/docs/cloud-codespaces.md#security-model)
for the first-pairing trust boundary and credential handling.

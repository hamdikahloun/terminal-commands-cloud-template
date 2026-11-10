# Terminal Commands Cloud Starter

An empty GitHub Codespaces workspace that connects to Terminal Commands in
ChatGPT. This public repository contains only this README and the Dev Container
configuration—no application code, project dependencies, or credentials.

The [Terminal Commands Dev Container Feature](https://github.com/users/hamdikahloun/packages/container/package/terminal-commands%2Fterminal-commands)
installs the companion with its own Node.js runtime. It starts automatically
when the Codespace starts, without changing your project's tools or scripts.

## Start a cloud machine

1. Open the **Terminal Commands Workspace** card in ChatGPT.
2. Choose **Default setup** and approve cloud execution and potential GitHub
   Codespaces charges.
3. Link your GitHub account and start the Codespace. If automatic creation is
   unavailable, use **Continue on GitHub** in the card.
4. Return to ChatGPT. The card shows the machine when pairing succeeds and the
   companion is online.

The Feature installs Terminal Commands `0.3.6` and runs the existing secure
`cloud-start` command. Startup and reconnection require no `package.json`,
`npm install`, or `npm start` script in this repository.

## Use your own Dev Container

To connect a Codespace based on your own repository, add this entry to its
`.devcontainer/devcontainer.json`:

```json
{
  "features": {
    "ghcr.io/hamdikahloun/terminal-commands/terminal-commands:1": {}
  }
}
```

Keep your existing base image, development tools, repository permissions, and
lifecycle commands. Choose **Use my own template** in the Workspace card and
provide the repository's GitHub URL.

## Security and privacy

Terminal Commands requires explicit consent for unattended full-shell cloud
execution. Its gateway verifies your GitHub identity and an authorized,
single-use pairing request before accepting a new device. The Feature does
not grant additional repository permissions or include secrets in the image.

This starter repository is **public**. Never commit private source code,
tokens, or other sensitive files to it. Starting a Codespace does not publish
its working files, but pushing commits to this repository can make them
public. Use your own private repository for private projects.

For Codespaces usage and troubleshooting, see [GitHub Codespaces documentation](https://docs.github.com/en/codespaces).
For customizing the installation, see the [Dev Container Features specification](https://containers.dev/features).

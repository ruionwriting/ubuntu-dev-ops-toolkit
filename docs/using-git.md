# Using Git

## Persist credentials

Just follow [Caching your GitHub credentials in Git](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git) from GitHub Docs. GitHub states:

> If you're cloning GitHub repositories using HTTPS, we recommend you use GitHub CLI or Git Credential Manager (GCM) to remember your credentials.

I recommend [GCM](https://github.com/GitCredentialManager/git-credential-manager). I'm not yet including automation for this configuration as Git configuration is a personal choice in most cases.

### Option 1: Downloading

> **Warning**
> At the present time of this writing this option is broken with the error `is not a Debian format archive`.

1. Download latest [.deb package](https://github.com/GitCredentialManager/git-credential-manager/releases/latest). Example:

   ```shell
   curl -O https://github.com/GitCredentialManager/git-credential-manager/releases/download/v2.0.779/gcm-linux_amd64.2.0.779.deb
   ```
1. Install example:

   ```shell
   sudo dpkg -i gcm-linux_amd64.2.0.779.deb
   ```

1. Then configure, regardless of the version:

   ```shell
   git-credential-manager-core configure
   ```

## Option2: Install from source helper script

> **Warning**
> A better process to explore later.

Run the script:

```shell
curl -LO https://raw.githubusercontent.com/GitCredentialManager/git-credential-manager/main/src/linux/Packaging.Linux/install-from-source.sh &&
sh ./install-from-source.sh &&
git-credential-manager-core configure
```

Them follow [GPG/pass compatible files](https://github.com/GitCredentialManager/git-credential-manager/blob/main/docs/credstores.md#gpgpass-compatible-files).

## Signing commits

1. Generate GPG key pair. Follow [Generating a new GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key) from GitHub Docs.
1. Set global configuration:

   ```shell
   git config --global commit.gpgsign true
   ```
   
   ```shell
   git config --global user.signingkey ***********8D9
   ```
   

# Using Git

## Persist credentials

WIP

## Signing commits

1. Generate GPG key pair. Follow [Generating a new GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key) from GitHub Docs.
1. Set global configuration:

   ```shell
   git config --global commit.gpgsign true
   ```
   
   ```shell
   git config --global user.signingkey ***********8D9
   ```
   

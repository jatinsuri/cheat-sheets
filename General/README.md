# General setup for all environments

## Create/Re-use SSH keys
To create a key
```bash
ssh-keygen -t ed25519 -a 100 -c <email address>
# setup a strong passphrase
```

## Git configuration
```bash
git config --global user.name "<name>"
git config --global user.email "<email>"
git config --global core.pager "less -XF"
```

## GPG Signing
gpg needs to be installed. For example for MacOS, install using:
```bash
brew install gpg-suite
```
Generate or import an existing key:
```bash
gpg --full-generate-key
# OR
gpg --import /path/to/secret.asc
```
Then configure git to use it:
```bash
gpg --list-secret-keys --keyid-format=long
# copy the key id from the 'sec' line
# sec   ed25519/ABAABBAABBAABBAA
git config --global user.signingkey ABAABBAABBAABBAA
git config --global commit.gpgsign true
git config --global gpg.program gpg
```
Export GPG key for adding to servers
```
gpg --armor --export ABAABBAABBAABBAA
```


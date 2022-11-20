# Setup MacOS for general purpose and development use

## Essential applications
- [VS Code](https://code.visualstudio.com/docs/?dv=darwinarm64)

    Use github or other login to sync settings.

- [Warp Terminal](https://app.warp.dev/get_warp).

- [Homebrew](https://brew.sh/). 
  
    Install:
    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

- [Nerd fonts](https://www.nerdfonts.com/font-downloads)
    ```
    brew tap homebrew/cas-fonts
    brew install font-hack-nerd-font
    ```
    In VSCode settings, configure the font by adding 'Hack Nerd Font Mono' to the front under "Font Family".

- [Oh my ZSH](https://ohmyz.sh/#install)
    ```
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```

- [Starship Prompt](https://starship.rs/guide/#%F0%9F%9A%80-installation)
    ```
    curl -sS https://starship.rs/install.sh | sh
    echo "eval $(starship init zsh)" >> ~/.zshrc
    sed -I '' 's/^ZSH_THEME/# ZSH_THEME/' .zshrc
    mkdir -p ~/.config && touch ~/.config/starship.toml
    starship preset pure-preset > ~/.config/starship.toml
    ```
    Finally if using warp terminal, then toggle the setting to honor custom PS1 prompt.

    Further customizations using reference starship.toml and starship.zsh files.

- [GPG Suite](https://gpgtools.org/)
    ```
    brew install gpg-suite
    ```
    Under GPG Suite settings, make sure that "Store in macOS KeyChain" is not selected and, if it ever was, then delete the existing stored password.
    

    

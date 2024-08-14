# Dev-Container-Template
This repository contains a template for development (dev) container which can be used by with the corresponding Visual Studio Code extension.

The configuration used here is based on setups, I have used frequently.
Thus, I created a sort of template which I can re-use and edit, instead of
copy-pasting the lines from different projects all the time.

## Usage
1. Install the extension (if not already installed):
    ```
    code --install-extension ms-vscode-remote.remote-containers
    ```
2. Clone/download this repo.
3. Modify the [Dockerfile](.devcontainer/Dockerfile) towards your needs.
4. Modify the [devcontainer.json](.devcontainer/devcontainer.json) towards your needs.
6. Open the folder (where .devcontainer is located) in VS Code. VS Code should ask you already to open the workspace in a Dev container. If not type in `Ctrl +p` and `> Dev Containers: Reopen in Container`.
7. Start working and adding your code. Note, that the source code and build files will be stored on your host. The current directory is mounted in the Docker container at `/home/<username>/ws`.
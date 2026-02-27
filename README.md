# laravelnew

`laravelnew` is a Docker-first Bash command for creating new Laravel projects without managing local PHP.

## Requirements

- Docker installed and running
- Bash

## Manual install

1. Clone the repository:

```bash
git clone https://github.com/josephmiclaus/laravelnew.git
cd laravelnew
```

2. Copy the script to a directory in your `PATH`:

```bash
cp laravelnew ~/.local/bin/laravelnew
chmod +x ~/.local/bin/laravelnew
```

3. Ensure `~/.local/bin` is in `PATH` (for `zsh`):

```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

4. Verify installation:

```bash
laravelnew --version
```

## Usage

```bash
laravelnew <app-name> [--here] [--using=<starter-kit>]
```

Options:
- `--here`: creates the app in a temporary `<app-name>` directory, then copies it into the current directory and deletes the temporary directory.
- `--using=<starter-kit>`: forwards to `laravel new <app-name> --using=<starter-kit>`.

## Examples

Create a project in its own folder:

```bash
laravelnew blog
```

Create using a starter kit:

```bash
laravelnew blog --using=laravel/blank-livewire-starter-kit
```

Create, then copy into the current directory:

```bash
laravelnew blog --here
```

## License

MIT

# laravelnew

`laravelnew` creates a Laravel project using only Docker.

Keep Docker running, then run `laravelnew <app-name>`. You do not need PHP, Composer, or the Laravel installer installed locally. Node/npm can run through Sail/Docker too.

## Why?

Laravel's [installation docs](https://laravel.com/docs/13.x/installation) and [agent setup](https://laravel.com/for/agents) expect a local toolchain: PHP, Composer, the Laravel installer, and Node/npm or Bun, often via [`php.new`](https://php.new/) or [Herd](https://herd.laravel.com/).

`laravelnew` runs that setup in Docker instead: the Laravel installer, Composer, Sail setup, and optional frontend commands, without installing those tools on your host.

## Only requirement

- Docker installed and running

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
laravelnew <app-name> [--here] [--using=<starter-kit>] [--start]
```

Options:
- `--here`: creates the app in a temporary `<app-name>` directory, then copies it into the current directory and deletes the temporary directory.
- `--using=<starter-kit>`: forwards to `laravel new <app-name> --using=<starter-kit>`.
- `--start`: starts Sail, installs frontend dependencies, and runs the frontend dev server through Sail/Docker after creation.

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

Create and start the project:

```bash
laravelnew blog --start
```

## License

MIT

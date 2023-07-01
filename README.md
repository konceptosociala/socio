# Socio

Zola theme for [Koncepto Sociala website](https://konceptosociala.eu.org/)

Thanks for `README` template to [adidoks](https://github.com/aaranxu/adidoks)

## Demo

[Live Preview](https://konceptosociala.eu.org/socio/).

## Requirements

Before using the theme, you need to install the [Zola](https://www.getzola.org/documentation/getting-started/installation/) ≥ 0.15.0.

## Quick Start

```bash
git clone https://github.com/konceptosociala/socio.git
cd socio
zola serve
# open http://127.0.0.1:1111/ in the browser
```

## Installation

Just earlier we showed you how to run the theme directly. Now we start to
install the theme in an existing site step by step.

### Step 1: Create a new zola site

```bash
zola init mysite
```

### Step 2: Install Socio

Download this theme to your themes directory:

```bash
cd mysite/themes
git clone https://github.com/konceptosociala/socio.git
```

Or install as a submodule:

```bash
cd mysite
git init  # if your project is a git repository already, ignore this command
git submodule add https://github.com/konceptosociala/socio.git themes/socio
```

### Step 3: Configuration

Copy the `config.toml` from the theme directory to your project's
root directory:

```bash
cp themes/socio/config.toml config.toml
```
Then enable the theme in your `config.toml` in the site directory:

```toml
theme = "socio"
```

For more detailed configuration visit [official configuration guide](https://konceptosociala.eu.org/socio/blog/configuration/)

### Step 4: Add new content

You can copy the content from the theme directory to your project:

```bash
cp -r themes/socio/content .
```

You can modify or add new posts in the `content/blog` or other
content directories as needed.

### Step 5: Run the project

Just run `zola serve` in the root path of the project:

```bash
zola serve
```

Socio will start the Zola development web server accessible by default at
`http://127.0.0.1:1111`. Saved changes will live reload in the browser.


## License

**Socio** is distributed under the terms of the
[Unlicense license](https://github.com/konceptosociala/socio/blob/main/LICENSE).
So it is a public domain and you can use it as you wish.

## TODO:
- [x] Main layout
- [x] Blog
- [x] Multilingualism
    - [x] Easy translation
    - [x] Language switcher
- [ ] Search
- [ ] Comments with [`utterances`](https://utteranc.es/)
- [ ] Documentation (TODO)
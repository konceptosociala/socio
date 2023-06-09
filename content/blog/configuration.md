+++
title = "Configuration"
date = 2023-01-07
+++

Socio is a pretty much configurable theme, so you can tweak many website parameters in `config.toml` file. All theme's parameters have prefix `socio_` and are located in `[extra]` section

## General

* `socio_title` - main website title, which is visible in title bar along with page title like: `My page | My site title`
* `socio_favicon` - website favicon path. It can be either relative or absolute (eg. https://...)
* `socio_logo` - website logo path. It is located on the navbar. If not set, website title is displayed instead
* `socio_animations` - enable animations with [animate.css](https://animate.style/)

## Navbar links

* `socio_navbar_links` - array of links, which are displayed on the navbar. They must have following structure:
    - `{ key = "home", link = "/" }` for regular links. `key` must be a valid [translations key](#translations). `link` can be either relative or absolute URL;
    - `{ key = "home" }` for disabled links;
    - `{ key = "about", dropdown = [...] }` for dropdowns. Socio dropdowns are **one-layer only**. `dropdown` array must have the following structure: 
        ```toml 
        dropdown = [
            ["my_link1", "/info/"],
            ["my_link2", "https://google.com"]
        ]
        ```
        where the first element of each array is a **valid translations key** and the second is a **URL**. Example:

        ```toml
        socio_navbar_links = [
            { key = "home", link = "/" },
            { key = "blog", link = "/blog/" },
            { key = "disabled" },
            { key = "about", dropdown = [
                ["info", "/info/"],
                ["socio_on_github", "https://github.com/konceptosociala/socio"]
            ] }
        ]
        ```

## Multilingualism

* `socio_languages` - array of languages, available in a navbar's **language switcher**. If not set, the switcher is not displayed. To configure website languages instead look at [Translations](#translations) section. Example:
    ```toml
    socio_languages = [
        { code = "default", name = "English", flag = "us" },
        { code = "ua", name = "Українська", flag = "ua" },
        { code = "sr", name = "Srpski", flag = "rs" },
    ]
    ```
    - `code` - the language code, displayed in website URL. For example, if it is `"es"`, then base URL will be *https://mysite.com/es/*. `default` value is for default site language, which is set with `config.default_language`
    - `name` - the language title, displayed in language switcher menu
    - `flag` - optional prefix of flag icon, which is displayed in language switcher menu. For available flags prefixes list [look here](https://flagicons.lipis.dev/)

## Homepage banner

* `socio_banner_display` - defines whether homepage banner is displayed
* `socio_banner_logo` - path to logo, which must be displayed on the banner
* `socio_banner_logo_width` - width of the logo
* `socio_banner_animation` - banner fade in animation like `bounce`, `flash` etc. For a full list look at [https://animate.style/](https://animate.style/)

## Social

You can put your social network profile links in footer with **Social** section. Just uncomment lines, that are needed, and put URLs:

```toml
socio_github = "https://github.com/konceptosociala/socio"
socio_mail = "mailto:mymail@example.com"
socio_telegram = "https://t.me/my_tg"
# socio_discord = ""    leave unneeded links commented
# socio_facebook = ""
#...
```

## Colors

Configure color palette of your website

#### Text colors

* `socio_text_color` - color of main text elements of the website (paragraphs, headings etc.)
* `socio_link_color` - color of website links
* `socio_code_color` - blog `code` element text color
* `socio_code_bg` - blog `code` element background color

#### Background colors

* `socio_post_bg` - post block background color at ["Blog"](..) page
* `socio_header_bg` - header color
* `socio_footer_bg` - footer color
* `socio_404_bg` - 404 error page background color
* `socio_page_bg` - default page color
* `socio_banner_bg` - homepage banner background color
* `socio_pill_bg` - pill shortcode background color (bootstrap color class)
* `socio_project_bg` - project shortcode background color (bootstrap color class)

#### Buttons

For now buttons are **bootstrap-styled only**, so you should use bootstrap color class names like `primary`, `success`, `light` etc. Or you can make own `btn-*` class and put a value in place of `*`.

* `socio_pill_btn` - pill shortcode **"Read more"** button color
* `socio_banner_btn` - homepage banner **"Learn more"** button color
* `socio_back_btn` - 404 error page **"Go back"** button color

## Misc

* `socio_forkme` - enables "Fork me on GitHub" ribbon. You can put your own repo link in `repo` and own ribbon label in `label`. Example:
```toml
socio_forkme = { enabled = true, repo = "https://github.com/konceptosociala/socio", label = "Fork me on GitHub"}
```

# Translations

Socio as well as many other themes supports Zola multilingual sites. 

1. Firstly, you have to add `[translations]` section (even if your website is not multilingual), which stands for default language keys translations:

    ```toml
    [translations]
    # required theme keys
    project_page = "Project page"
    read_more = "Read more"
    banner_button = "Learn more"
    banner_heading = "My Awesome Website"
    banner_descr = "Made with love <3"

    # optional custom keys
    #...
    ```

2. Secondly, define all needed languages and their translations for theme keys:

    ```toml
    [languages.ua]

    [languages.ua.translations]
    project_page = "Сторінка проєкту"
    read_more = "Читати далі"
    banner_button = "Дізнатися більше"
    banner_heading = "Мій прекрасний веб-сайт"
    banner_descr = "Зроблено з любов'ю <3"

    [languages.sr]

    [languages.sr.translations]
    project_page = "Stranica projekta"
    read_more = "Opširnije"
    banner_button = "Saznajte više"
    banner_heading = "Moj sjajni veb sajt"
    banner_descr = "Napravljeno s ljubavlju <3"
    ```

    Do not forget to add preferred languages to language switcher with `socio_languages`:
    
    ```toml
    socio_languages = [
        { code = "default", name = "English", flag = "us" },
        { code = "ua", name = "Українська", flag = "ua" },
        { code = "sr", name = "Srpski", flag = "rs" },
    ]
    ```
3. Then add your navbar items translation keys to display their labels. If your navbar is like this:

    ```toml
    socio_navbar_links = [
        { key = "home", link = "/" },
        { key = "blog", link = "/blog/" },
        { key = "disabled" },
        { key = "about", dropdown = [
            ["info", "/info/"],
            ["socio_on_github", "https://github.com/konceptosociala/socio"]
        ] }
    ]
    ```

    ...so add default translations:
    
    ```toml
    [translations]
    # optional custom keys
    #...
    home = "Home"
    blog = "Blog"
    disabled = "Disabled"
    about = "About"
    info = "Info"
    socio_on_github = "Socio on GitHub"
    ```

    ...and then for other languages:

    ```toml
    [languages.ua.translations]
    #...
    home = "Головна"
    blog = "Блог"
    disabled = "Відключено"
    about = "Про нас"
    info = "Інформація"
    socio_on_github = "Socio на GitHub"

    #...

    [languages.sr.translations]
    #...
    home = "Početna"
    blog = "Blog"
    disabled = "Onemogućeno"
    about = "O nama"
    info = "Informacije"
    socio_on_github = "Socio na GitHub"
    ```

    You can also add your own keys and use them in your templates like this:
    ```handlebars
    <h1>{{ trans(key="my_heading", lang=lang) }}</h1>
    ```
4. And for markdown page translations use a translation with a name "name.{code}.md". In this example for homepage translation we will need the following files:
    * `_index.md`
    * `_index.ua.md`
    * `_index.sr.md`

For more detailed guide follow [the official Zola documentation](https://www.getzola.org/documentation/content/multilingual/).

# Comments with [`utterances`](https://utteranc.es)

You can enable your blog posts comments by adding `[extra.socio_utterances]` section to your config toml:

* `label` - GitHub issue label for comments (optional)
* `repo` - GitHub repo in format `organization/example_repo`
* `theme` - utterances theme. Look at [official website](https://utteranc.es/) for a full list
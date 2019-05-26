---
title: "You Should Use a Remote Theme for Your Jekyll Repository"
date: 2019-05-26 21:47:47 +0800
categories: Views
tags: jekyll
---

Normally, there are two ways to use a Jekyll theme.

1. Specifying the Jekyll theme you use in `_config.yml`, for example, `theme: minima`. The disadvantage is that you can't do completely free customization.
2. Copying all needed files from the Jekyll theme into your repository. The disadvantage is that you can't easily track the recent updates of the Jekyll theme.

However, thanks to the [`jekyll-remote-theme`](https://github.com/benbalter/jekyll-remote-theme) plugin, you can use any GitHub-hosted theme. That means if you love a Jekyll theme, you can fork the repository and do your customized modification in there. Then you can use this new theme in your Jekyll site.

For example, I had forked the [`minima`](https://github.com/jekyll/minima) theme and checkouted a branch [`alex`](https://github.com/alexhuangster/minima/tree/alex) to do customization. For using this theme, I just need to 

1. Specify `gem "jekyll-remote-theme"` in `Gemfile`.
2. Add the following to `_config.yml`.

    ```yml
    plugins:
      - jekyll-remote-theme

    remote_theme: alexhuangster/minima@alex
    ```

Now, I finished the separation of theme and contents.

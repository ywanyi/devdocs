---
group: php-developer-guide
subgroup: 03_Build
title: Create your component file structure
menu_title: Create your component file structure
menu_order: 3000
---

在本节中，我们将介绍组件类型的不同文件结构。 Magento应用程序将查找组成组件的文件，包括配置文件，尤其是在组件文件结构内的特定位置。 请遵循要开发的组件类型的预定义文件结构，以确保它可以按预期工作。

{% include php-dev/component-root.md %}

### 模块文件结构

A typical file structure for a Magento 2 [module](https://glossary.magento.com/module) can look like the following:

![Module File Structure]({{ site.baseurl }}/common/images/pdg-config-file-structure.png){:width="300px"}

#### 常用目录
{:.no_toc}
Following are some common module directories:

*  `Block`: contains [PHP](https://glossary.magento.com/php) view classes as part of Model View Controller(MVC) vertical implementation of module logic.
*  `Controller`: contains PHP controller classes as part of MVC vertical implementation of module logic.
*  `etc`: contains configuration files; in particular, `module.xml`, which is required.
*  `Model`: contains PHP model classes as part of MVC vertical implementation of module logic.
*  `Setup`: contains classes for module database structure and data setup which are invoked when installing or upgrading.

#### Additional directories
{:.no_toc}
Additional folders can be added for configuration and other ancillary functions for items like [plugin-ins]({{ page.baseurl }}/extension-dev-guide/plugins.html), localization, and [layout](https://glossary.magento.com/layout) files.

*  `Api`: contains any PHP classes exposed to the [API](https://glossary.magento.com/api).
*  `Console`: contains CLI commands. For more info, see [Add CLI commands]({{ page.baseurl }}/extension-dev-guide/cli-cmds/cli-add.html).
*  `Cron`: contains cron job definitions.
*  `CustomerData`: contains section files.
*  `Helper`: contains aggregated functionality.
*  `i18n`: contains localization files.
*  `Observer`: contains files for executing commands from the listener.
*  `Plugin`: contains any needed [plug-ins]({{ page.baseurl }}/extension-dev-guide/plugins.html).
*  `UI`: contains data generation files.
*  `view`: contains view files, including static view files, design templates, email templates, and layout files.

### Theme file structure

A typical [theme](https://glossary.magento.com/theme) file structure can look like the following:

```tree
├── composer.json
├── etc
│   └── view.xml
├── i18n
│   └── en_US.csv
├── LICENSE_AFL.txt
├── LICENSE.txt
├── media
│   └── preview.jpg
├── registration.php
└── web
    ├── css
    │   ├── email.less
    │   ├── print.less
    │   ├── source
    │   │   ├── _actions-toolbar.less
    │   │   ├── _breadcrumbs.less
    │   │   ├── _buttons.less
    │   │   ├── components
    │   │   │   └── _modals_extend.less
    │   │   ├── _icons.less
    │   │   ├── _layout.less
    │   │   ├── _theme.less
    │   │   ├── _tooltips.less
    │   │   ├── _typography.less
    │   │   └── _variables.less
    │   ├── _styles.less
    │   ├── styles-l.less
    │   └── styles-m.less
    ├── images
    │   └── logo.svg
    └── js
        ├── navigation-menu.js
        ├── responsive.js
        └── theme.js
```

#### Common directories
{:.no_toc}
Typical theme directories are:

*  `etc`: Contains configuration files such as the `view.xml` file which contains image configurations for all images and thumbnails.
*  `i18n`: [Translation dictionaries]({{ page.baseurl }}/frontend-dev-guide/translations/xlate.html#m2devgde-xlate-dictionaries), if any.
*  `media`: Theme preview images (screen capture of your theme) can be put in here.
*  `web`: Optional directory that contains [static files](https://glossary.magento.com/static-files) organized into the following subdirectories:

   *  `css/source`: Contains a theme's `less` configuration files that invoke mixins for global elements from the [Magento UI library]({{ page.baseurl }}/frontend-dev-guide/css-topics/theme-ui-lib.html), and the `theme.less` file that overrides the default variables values.
   *  `css/source/lib`: Contains view files that override the [UI library]({{ page.baseurl }}/frontend-dev-guide/css-topics/theme-ui-lib.html) files stored in `lib/web/css/source/lib`.
   *  `fonts`: The folder to place the different fonts for your theme.
   *  `images`: Static images folder.
   *  `js`: The folder for your JavaScript files.

For more details on the theme folder structure, see [Magento theme structure]({{ page.baseurl }}/frontend-dev-guide/themes/theme-structure.html).

{% include php-dev/lang-pack-file-struct.md %}

**Next**

[Register your component]({{ page.baseurl }}/extension-dev-guide/build/component-registration.html)

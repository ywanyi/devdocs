---
group: architecture-guide
title: Module overview
menu_title: Module overview
---

## 什么是Magento模块? {#arch-modules-overview}

“模块”是一个逻辑组，即包含与特定业务功能相关的块，控制器，助手，模型的目录。 为了遵循Magento对最佳模块化的承诺，[模块](https://glossary.magento.com/module)封装了一个功能，并且对其他模块的依赖性最小。

模块和主题是Magento中的自定义单位。 模块提供业务功能以及支持逻辑，而主题则强烈影响用户体验和[店面](https://glossary.magento.com/storefront)外观。 这两个组件都有生命周期，可以安装，删除和禁用它们。 从商人和[扩展](https://glossary.magento.com/extension)开发人员的角度来看，模块都是Magento组织的核心单位。

Magento框架提供了一组核心逻辑：[PHP](https://glossary.magento.com/php)代码，库以及由模块和其他组件继承的基本功能。

## 模块的目的

模块的目的是通过实现新功能或扩展其他模块的功能来提供特定的产品功能。 每个模块都设计为独立运行，因此包含或排除特定模块通常不会影响其他模块的功能。

## 模块组件

一个模块是包含PHP和[XML](https://glossary.magento.com/xml)文件，这些文件涉及到一个特定的业务功能(块，控制器，助手，型号)，如航运目录。具体而言，Magento的模块由这些软件组件：[主题]({{page.baseurl}}/前端-DEV-引导/主题/主题overview.html)，[库]({{page.baseurl}}/architecture/archi_perspectives/third-party-libs.html)和[语言包]({{page.baseurl}}/前端-DEV-引导/翻译/ xlate.html＃m2devgde-XLATE-languagepack)。

## 模块位置

模块通常位于Magento安装的`vendor`目录中，该目录具有以下PSR-0兼容格式：`vendor/<vendor>/<type>-<module-name>`，其中`<type>` 可以是以下值之一：

-  **`module`** - for modules (`module-customer-import-export`)
-  **`theme`** - for frontend and admin themes (`theme-frontend-luma` or `theme-adminhtml-backend`)
-  **`language`** - for language packs (`language-de_de`)

For example, the Customer Import/Export module of Magento can be found at `vendor/magento/module-customer-import-export`.

If you are creating a new module for distribution, create the `app/code/<vendor>/<type>-<module-name>` directory and the required directories within it.

Inside this folder, you will find all the code related to this module, including the `etc/module.xml` file, which contains the name and version of the module, as well as any dependencies.

### 模块位置约定 {#m2arch-module-conventions-location}

The following table shows the *recommended* location within the Magento file system for specific components.

(A [module](https://glossary.magento.com/module) must include a `registration.php` file in its root folder.)

We refer to a component's root directory as the top-level directory in which you develop component code. Typically, this directory is located in one of the following directories relative to the Magento root directory:

|Entity|Location|
|---|---|
|自定义模块基本代码|`/app/code/<Vendor>/<Module>`|
|自定义主题文件 (storefront)|`/app/design/frontend/<Vendor>/<theme>`|
|自定义主题文件 (modules)|`<Module>/<theme>`|
|如果你想使用一个类库|`/lib/<Vendor_Library>`|

## 使用模块

Magento developers, administrators, and anyone building a Magento website will want to review all relevant topics surrounding their particular goals and use cases.

See [PHP Developer Guide][] for specific instructions on extending modules.

See [Frontend Developer Guide][] for information on implementing themes and other components.

{:.ref-header}
Related topics

[Module dependencies][]

[Modules and areas][]

[Module location and naming conventions][]

<!-- Link Definitions  -->
[Github repo]: https://github.com/magento/magento2/tree/2.3-develop/app/code/Magento
[Module dependencies]: {{page.baseurl}}/architecture/archi_perspectives/components/modules/mod_depend.html
[Modules and areas]: {{page.baseurl}}/architecture/archi_perspectives/components/modules/mod_and_areas.html
[Module location and naming conventions]: {{page.baseurl}}/architecture/archi_perspectives/components/modules/mod_intro.html
[PHP Developer Guide]: {{page.baseurl}}/extension-dev-guide/bk-extension-dev-guide.html
[Frontend Developer Guide]: {{page.baseurl}}/frontend-dev-guide/bk-frontend-dev-guide.html
[themes]: {{page.baseurl}}/frontend-dev-guide/themes/theme-overview.html
[libraries]: {{page.baseurl}}/architecture/archi_perspectives/third-party-libs.html
[language packages]: {{page.baseurl}}/frontend-dev-guide/translations/xlate.html#m2devgde-xlate-languagepack

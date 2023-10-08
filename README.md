# Introduction

**An extremely simple module that enables Magento 2's ability to use Require Css.**\
*(This module is designed as a dependency for making other modules.)*
 - Very useful when you need to load css in `.phtml`.
 - Dynamically load css.
 - Use inside `<head>`(eg: load different external css for different stores).

# Usage
```
<script>
// Load a single css in
// [module root]/view/[area]/web/css/example-01.css
// or
// [theme root]/web/css/example-01.css
require(['require-css!css/example-01']);

// Load multiple css.
require([
    'require-css!css/example-02',
    'require-css!css/example-03'
], function () {
    // Code to run when all css loaded successfully.
});

// Load external css. You don't need the .css extension.
require(['require-css!https://some-cdn.tld/styles']);
</script>
```

# How it works
The core part, which is a RequireJS Plugin, is taken from [here](https://github.com/guybedford/require-css). When the dependency `require-css!css/styles` is required, it will inject a `link` element that contains stylesheet into `<head>`. 

#### Best used with
[wubinworks/HeadContent](https://github.com/wubinworks/HeadContent)

# Requirements
**Magento 2**

# Installation
**`composer require wubinworks/module-require-css`**\
Don't forget to run `php bin/magento setup:upgrade`

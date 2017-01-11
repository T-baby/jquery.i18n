# jquery.i18n.js

[中文文档][3]

A lightweight, internationalization (i18n) plugin based on jQuery.

- Support to set the default language.
- Support to switch languages.
- Support to use json file to storage translation content.

According to user-defined different language versions of the json file, according to demand for rendering language on the page, to achieve internationalization.

## Installation

You can download the latest version at https://github.com/ZOMAKE/jquery.i18n/releases

First of all, import the `jquery.js` file in your project:
```JS
<script src="jquery.js"></script>
```

Then, Include `jquery.i18n.js` after the jQuery library :
```JS
<script src="jquery.i18n.js"></script>
```

## Usage
First, create a new `i18n` folder in the project, Place the `i18n_xx.json` language files in different languages under this folder.
(You can also customize the beginning and end of the file name, such as `BaiduCnLang.js`, the following example to `i18n_` for the file name at the beginning.)

Include the i18n attribute at the DOM structure that needs to use the internationalization feature.(i18n's value is the language file "key", it can be customized.)

```JS
<div i18n="i18n.test">multi-language</div>
<div i18n="i18n.test2">internationalization</div>
```

Then only need to add content in the language file.

For example, the Chinese version of the language file named `i18n_cn.json`, the English version of the language file named ` i18n_en.json`:

`i18n_cn.json`：
```
{
    "i18n.test": "多语言",
    "i18n.test2": "国际化"
}
```

Corresponding to the translation file `i18n_en.json`:
```
{
    "i18n.test": "multi-language",
    "i18n.test2": "internationalization"
}
```

Finally, execute the following method in the script to initialize the plugin:
```JS
$("[i18n]").i18n({
    defaultLang: "en",
    filePath: "/i18n/",
    filePrefix: "i18n_",
    fileSuffix: "",
    forever: true,
    callback: function() {
    }
});
```

## Configuration

#### defaultLang
```JS
defaultLang: defaultLang,
```
Default language name, plugin will automatically `filePrefix` +` defaultLang` + `fileSuffix` spliced together as the language file name.

#### filePath
```JS
filePath: "/i18n/",
```
This parameter specifies the location of the folder where the language files are located in the project.

#### filePrefix
```JS
filePrefix: "i18n_",
```
This parameter specifies the name prefix of the language file.

#### fileSuffix
```JS
fileSuffix: "",
```
This parameter specifies the name suffix of the language file.

#### callback
```javascript
callback:function(){
    //do something
}
```

## i18nOnly
HTML element will be the default placeholder, value, html translation with the replacement, if you only need to replace one, you can declare the HTML tag `i18nOnly` attribute.

```html
<input i18n="i18n.test" i18n-only="placeholder" placeholder="多语言"></input>
```

## Contributors
- [T-baby][1]
- [NiroDu][2]

  [1]: https://github.com/T-baby/
  [2]: https://github.com/NiroDu
  [3]: https://github.com/ZOMAKE/jquery.i18n/blob/master/README-CN.md

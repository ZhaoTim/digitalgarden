---
{"dg-publish":true,"permalink":"/prettier/","dgPassFrontmatter":true,"created":"2023-09-30T14:27:23.194+08:00","updated":"2025-03-18T01:05:13.704+08:00"}
---

所有的代码，都是用prettier来格式化。
```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

除了JavaScript文件，都用prettier来格式化。下面的"[javascript]": 代表着「针对于JavaScript文件」使用特定的formatter。
```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.defaultFormatter": "<another formatter>"
  }
}
```


```bash
npm install prettier -D --save-exact
```
#npm
--save-exact 代表着安装依赖的准确版本。
![Pasted image 20230930143642.png](/img/user/Pasted%20image%2020230930143642.png)
截图里可以看出，版本号的前面没有`^`之类的符号了，代表着我们把版本锁定住了，我们把node_modules文件夹删除以后，重新npm install,就算这期间prettier发布了新的版本，我们也不会采用，而是安装的3.0.3的版本。

原文：
> This extension will use prettier from your project's local dependencies (recommended). When the `prettier.resolveGlobalModules` is set to `true` the extension can also attempt to resolve global modules. Should prettier not be installed locally with your project's dependencies or globally on the machine, the version of prettier that is bundled with the extension will be used.

翻译：prettier-vscode 插件将使用当前项目本地依赖中的 prettier（推荐）。当 prettier.resolveGlobalModules 被设置为 true 时（settings.json），prettier-vscode 插件也可以尝试解析全局 prettier。如果本地依赖和全局都没有安装 prettier，那么将使用 prettier-vscode 插件捆绑的 prettier。

也就是说，如果项目node_modules有prettier，那么就使用它。如果在vscode的setting.json里把resolveGlobalModules设置为true，那么就会使用`npm install prettier -g`安装的prettier，如果啥都没装，没关系，扩展自己本身还捆绑了一个prettier（贴心
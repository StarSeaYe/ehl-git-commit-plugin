# Ehl Git Commit Plugin For VS Code
> 按ehl代码规范在git生成说明并自动提交

## 格式

这个插件创建了一个如下git commit的模板:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

### Type（必填项）

Type | Description
---  | ---
**feat** | 新增功能，可包含其他类型的内容
**fix** | bug 修复，进入测试阶段产生的BUG，可包含其他类型的内容
**merge** | 代码合并
**docs** | 文档更新
**style**: | 不影响程序逻辑的代码修改(修改空白字符，格式缩进，补全缺失的分号等，没有改变代码逻辑)
**refactor** | 重构代码(既没有新增功能，也没有修复 bug)
**perf** | 性能, 体验优化
**test** | 新增测试用例或是更新现有测试
**build** | 主要目的是修改项目构建系统(例如 glup，webpack，rollup 的配置等)的提交
**ci** | 主要目的是修改项目继续集成流程(例如 Travis，Jenkins，GitLab CI，Circle等)的提交
**chore** | 不属于以上类型的其他类，比如构建流程, 依赖管理
**revert** | 回滚某个更早之前的提交

### Scope（必填项）

禅道编号

Type | Description
---  | ---
**feat** | 需求的禅道编号，无时填0。可包含其他类型的内容
**fix** | bug 的禅道编号，无时填0。可包含其他类型的内容
**其它** | 面向禅道任务的填禅道任务编号，无时填0

### Subject（必填项）

subject是 commit 目的的简短描述:

-   首字母不要大写
-   结束时不要使用(`.`)符号

### Body（可选项）

body 部分是对本次 commit 的详细描述，可以分成多行
描述符合30/40原则：第一行不超过30字符，其他行不超过40字符

### Footer（可选项）

保留项，目前暂不设计

## 安装

使用vsix包进行安装插件
  ![open](/assets/install.png)

## 使用

1. 点击按钮打开插件
  ![open](/assets/step1.png)


2. 选择提交的类型
  ![open](/assets/step2.png)


3. 选择分项
  ![open](/assets/step3.png)


4. 输入内容分项
  ![open](/assets/step4.png)


5. 所有内容输入完成后选择**Complete**完成提交的编写
  ![open](/assets/step5.png)
  

6. 最后生成提交内容
  ![open](/assets/step6.png)


## 选项配置

-   `GitCommitPlugin.CustomCommitType`: 自定义提交类型，默认值为 `null`.
    ```json5
    { 
      "GitCommitPlugin.CustomCommitType": [
        "customTypeName"
      ]
    }
    ```
    or
    ```json5
    [
       {
           // If there are duplicate keys, rewrite the config，otherwise add As a new configuration addition
           "key": "customTypeKey", 
           "label": "customTypeName",
           "detail": "customTypeDetail"
       }
    ]
    ```
-   `GitCommitPlugin.MaxSubjectCharacters`: 自定义subject的最大字数，默认值为`20`.
    ```json
    {
      "GitCommitPlugin.MaxSubjectCharacters": 20
    }
    ```
-   `GitCommitPlugin.Template`: 自定义提交模板。
    ```json5
    {
      "GitCommitPlugin.Templates": [
        {
            "templateName": "Ehl",
            "templateContent": "<type>(<scope>):<subject><enter><body><enter><footer>"
        }
      ]
    }
    ```

## License

Released under [MIT](/LICENSE) by [@StarSeaYe](https://github.com/StarSeaYe).

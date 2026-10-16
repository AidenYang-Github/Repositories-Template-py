# The repository template of Python project（With Pixi）

> **本项目使用`pixi`进行项目管理**

## 1. Python project layout

```
# Basic files
my-project/                     
│
├── .github/                    
│   ├── ISSUE_TEMPLATE/         
│   │   ├── bug_report.md      
│   │   ├── feature_request.md 
│   │   └── custom.md          
│   │
│   ├── workflows/              
│   │   └── ci.yml                  
│   │
│   ├── dependabot.yml          
│   └── pull_request_template.md
|
├── tests 
│   └── test_ci.py
|    
├── README.md 
├── LICENSE   
└── .gitignore
```

## 2. 使用`pixi`进行项目初始化
### 2.1 将仓库模板clone到本地
```
git clone git@github.com:AidenYang-Github/Repositories-Template-py.git
```

### 2.2 pixi初始化
```
# VSCode中打开终端（Ctrl+Shift+`），cd到项目路径：
pixi init --format pyproject
```

### 2.3 配置“pyproject.toml”中多个环境（新增一个test环境），流程为：
```
# 给`test`feature添加pytest依赖
pixi add --feature test pytest

# 将默认环境添加到default求解组
pixi workspace environment add default --solve-group default --force

# 新建一个test环境并分配“test”特性，同时将其加入到default求解组
pixi workspace environment add test --feature test --solve-group default

# 添加一个带有“test”特性的task
pixi task add --feature test test "pytest"
```

### 2.4 更新pytest包：
使用`pixi upgrade pytest`将“test”环境中的依赖包进行更新，而不是使用`pixi add --feature test pytest`更新，否则会提示：
```
✔ pytest is already a dependency
    Run `pixi upgrade pytest` to get the newest compatible version
Added these only for feature: test
```

## 3. 初始化完成
完成以上操作后，项目中会多出以下文件（夹），后续便可以开始项目的编写工作。
```
# 以下一个文件夹（src）和两个文件需要使用pixi进行初始化生成
my-project/ 
├── src                    
│   └── my-project/         
│       └── __init__.py
|
├── .gitattributes 
├── pixi.lock  
└── pixi.toml(pyproject.toml) 
```

---
> 本README.md将持续进行修改与更新。  
> 以本项目为仓库模板后，需删除该README.md重新进行编写。
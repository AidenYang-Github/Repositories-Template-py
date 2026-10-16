# Template of Python Project

## Python Project src layout

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
├── README.md 
├── LICENSE   
└── .gitignore

# Pixi files
my-project/ 
├── src                    
│   └── my-project/         
│       └── __init__.py
│
├── tests 
│   └── test_ci.py 
|
├── pixi.lock  
└── pixi.toml(pyproject.toml) 
```


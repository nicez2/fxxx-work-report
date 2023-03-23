# 🚀  QucikWorkReport 🚀 
Python脚本-用于生成指定Git账号在任意时间、指定文件目录下的所有Git仓库的提交记录生成周报、月报。
## 时间都是挤出来的 🏃
### 脚本自带去重提交记录、替换feat: fixed: 等前缀，并去重提交记录
在脚本中配置以下下参数
````python
# 本机git账号
git_username = "nicezz"

# 要查找的git项目路径列表
project_paths = [
    "/Users/nicezz/IdeaProjects/",
    "/Users/nicezz/WebstormProjects/"
]

# 保存记录的路径
output_path = "/Users/nicezz/temp/"
````
执行main方法后，会在output_path指定的目录下生成报告文档。
<img width="200" alt="image" src="https://user-images.githubusercontent.com/22947965/227078731-ab4f526f-e343-4e0d-b6c7-e15f910fdee5.png">

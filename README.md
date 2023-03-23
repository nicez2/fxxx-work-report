# QucikWorkReport
Python脚本-用于生成指定Git账号在任意时间、指定文件目录下的所有Git仓库的提交记录生成周报、月报...
在脚本中配置一下参数
# 本机git账号
git_username = "nicezz"

# 要查找的git项目路径列表
project_paths = [
    "/Users/nicezz/IdeaProjects/",
    "/Users/nicezz/WebstormProjects/"
]

# 保存记录的路径
output_path = "/Users/nicezz/temp/"

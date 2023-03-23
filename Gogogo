import subprocess
import os
import datetime
import re

# 获取本周的周数
week_number = datetime.date.today().isocalendar()[1]

# 本机git账号
git_username = "nicezz"

# 要查找的git项目路径列表
project_paths = [
    "/Users/nicezz/IdeaProjects/",
    "/Users/nicezz/WebstormProjects/"
]

# 保存记录的路径
output_path = "/Users/nicezz/temp/"

# 定义正则表达式来匹配记录中{符号前面的内容
regex = r"^.*?(?=\{)"
# 定义计数器
counter = 1
# 创建一个空集合用于去重
unique_lines = set()
# 遍历所有项目路径
for path in project_paths:
    # 获取当前路径下的所有子目录
    subdirs = next(os.walk(path))[1]
    for subdir in subdirs:
        # 构造git仓库路径
        repo_path = os.path.join(path, subdir)
        if os.path.isdir(os.path.join(repo_path, ".git")):
            # 检查是否有提交记录，没有则进行初始提交
            check_command = "cd {0} && git log --pretty=format:''".format(repo_path)
            check_process = subprocess.Popen(check_command, stdout=subprocess.PIPE, shell=True)
            check_output, check_error = check_process.communicate()
            if not check_output:
                initial_command = "cd {0} && touch README.md".format(
                    repo_path)
                subprocess.Popen(initial_command, stdout=subprocess.PIPE, shell=True)
            # 执行git log命令获取提交记录
            command = "cd {} && git log --author={} --since='7 days ago' --pretty=format:'%s {{}}* %cd'".format(
                repo_path, git_username)
            process = subprocess.Popen(command, stdout=subprocess.PIPE, shell=True)
            output, error = process.communicate()
            # 提取commit的内容，并替换prefix和提交人、提交日期
            output = output.decode("utf-8")
            output = output.replace("feat:", "")
            output = output.replace("fixed:", "")
            # 提取每条记录中{符号前面的内容
            matches = re.findall(regex, output, re.MULTILINE)



            for match in matches:
                # 构造输出文件名
                filename = "week{0}.txt".format(week_number)
                # 将输出写入文件，并去重和加入行号
                out = "{0}".format(match)
                if out not in unique_lines:
                    line = "{0}. {1}".format(counter, match)
                    unique_lines.add(out)
                    with open(os.path.join(output_path, filename), "a") as f:
                        f.write(line + "\n")
                    counter += 1

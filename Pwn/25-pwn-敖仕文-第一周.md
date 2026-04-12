#第一题
###先用nc来将虚拟机连接远程靶机，然后再用ls展开文件里面的内容，发现里面有flag，最后用cat flag获取真正的flag
<img width="1112" height="686" alt="屏幕截图 2026-04-12 180745" src="https://github.com/user-attachments/assets/8ec5e0c8-2b2e-44a1-a90d-53bd5ee69e93" />

# Linux虚拟机指令
## 1.基础文件操作
（这些命令可以对一个文件操作，比如浏览、查找、管理文件）

| 命令 | 功能说明 | 示例或备注 |
| ---- | -------- | -------- |
| ls | 列出目录内容 | ls -la 显示详细文件信息（包括隐藏文件） |
| cd | 切换当前工作目录 | cd /tmp |
| cat | 查看文件内容 | 常用于直接读取flag或 cat /home/ctf/flag.txt |
| find | 查找文件 | find / -name "pwn" 2>/dev/null<br>在根目录下查找名为“pwn”的文件（忽略错误信息） |
| grep | 在文件中搜索特定字符串 | grep -r "flag{" ./ 在当前目录下递归搜索包含”flag{”的文件<br>strings binary | grep "bin/sh" 在二进制文件中查找字符串 |
| file | 查看文件类型 | file pwn_binary 判断文件是ELF32还是ELF64，以及是否stripped |
| objdump | 反汇编二进制文件 | objdump -d ./pwn_binary | grep "system" 反汇编并查找system函数地址 |
| readelf | 显示ELF文件信息 | readelf -s ./pwn_binary 查看符号表<br>readelf -h ./pwn_binary 查看文件头 |
| chmod | 修改文件权限 | 常用来给二进制文件添加可执行权限：chmod +x pwn_binary |
| cp/mv/rm | 复制/移动/删除文件 | |
| touch | 创建空文件 | |
| mkdir | 创建目录 | |

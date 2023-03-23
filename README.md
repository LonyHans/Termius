`termius`破解使用`sftp`

- 安装`termius`

  使用版本7.33.1
  
  下载链接：https://anonfiles.com/Ldbevbg2z3/Termius_zip

- 依赖下载

  1. 安装`node`

     下载地址：https://nodejs.org/en/download/

     历史版本地址：https://nodejs.org/dist/

     **注意：**Linux上安装`Node.js`需要安装`Python2.6/2.7`，不建议安装`Python3.0`以上版本

     - `Windows`上安装`Node.js`

       1. `Windows`安装包（`.msi`）

       ![windows安装node](https://gitee.com/lonyhans/pic/raw/master/image/202303231051729.jpg)

       ![install-node-msi-version-on-windows-step1](https://gitee.com/lonyhans/pic/raw/master/image/202303231051798.png)

       2. 点击`run`

       ![install-node-msi-version-on-windows-step2](https://gitee.com/lonyhans/pic/raw/master/image/202303231051930.png)

       3. 勾选接受协议选项，点击`next`

       ![install-node-msi-version-on-windows-step3](https://gitee.com/lonyhans/pic/raw/master/image/202303231051977.png)

       4. `Node.js`默认安装目录为：`C:\Program Files\nodejs\`

       ![install-node-msi-version-on-windows-step4](https://gitee.com/lonyhans/pic/raw/master/image/202303231051022.png)

       5. 点击树形图标来选择需要安装的模式，然后点击`next`

       ![install-node-msi-version-on-windows-step5](https://gitee.com/lonyhans/pic/raw/master/image/202303231051068.png)

       6. 点击`install`开始安装

       7. 在`cmd`检查`PATH`环境变量是否配置了`Node.js`，输入`PATH`回车

          > PATH=C:\oraclexe\app\oracle\product\10.2.0\server\bin;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;c:\python32\python;C:\MinGW\bin;C:\Program Files\GTK2-Runtime\lib;C:\Program Files\MySQL\MySQL Server 5.5\bin;C:\Program Files\nodejs\;C:\Users\rg\AppData\Roaming\npm

       8. 环境变量已经包含了`C:\Program Files\nodejs\`

       9. 检查`Node.js`版本

       <img src="https://gitee.com/lonyhans/pic/raw/master/image/202303231051119.png" alt="image-20220518220015838" style="zoom:150%;" />

  2. 安装`asar`，用来解压配置文件

     ````shell
     > nmp install -g asar
     ````

- 修改`js`文件解锁

  1. 右键点击`termius`图标打开文件所处位置，进入`termius`配置目录

     ````shell
     > C:\Users\xx\AppData\Local\Programs\Termius\resources
     ````

  2. 解压`asar`文件得到`app`文件夹

     ````shell
     > asar e app.asar app
     ````

  3. 用`VScode`打开文件`app\js\ui-process.js`

     1. 格式化

        `Ctrl+Shift+P`，搜索`format`，选择`format document`，格式化

     2. 搜索字段`isprouser`，对应函数`Ol`的返回值修改为`true`

        ![修改文件1](https://gitee.com/lonyhans/pic/raw/master/image/202303231051163.png)
        
        ![修改文件2](https://gitee.com/lonyhans/pic/raw/master/image/202303231051203.png)
        
     3. 搜索`e.user.username`
     
        ![修改文件3](https://gitee.com/lonyhans/pic/raw/master/image/202303231051247.png)
     
     4. 返回值修改为任意值，保存
     
        ![修改文件4](https://gitee.com/lonyhans/pic/raw/master/image/202303231051292.png)
     
     5. 完成

### 一、安装环境

1、本机系统：Windows 10 （64 位）
2、Node.js：v16.14.2（64 位）

### 二、安装 Node.js 步骤

1、下载 node 安装包
2、选安装目录进行安装
3、环境配置
4、测试

### 三、前期准备

node 安装包阿里云盘下载地址：https://www.aliyundrive.com/s/A4ByK9qorzq

### 四、开始安装

1、下载完成后，双击“node-v16.14.2-x64.msi”，开始安装 Node.js

<img src="https://s2.loli.net/2022/08/15/YSPGCFykMpuslVj.png" alt="02" style="zoom:67%;" />

点击【Next】按钮

<img src="https://s2.loli.net/2022/08/15/9YCJe5lLAd6RnHZ.png" alt="03" style="zoom:67%;" />

勾选复选框，点击【Next】按钮

![image-20220426092701710](https://s2.loli.net/2022/08/15/XB98nz3wHdkCAOr.png)

修改好目录后，点击【Next】按钮

![image-20220426092944998](https://s2.loli.net/2022/08/15/31DMBZtgh9AuFXw.png)

![image-20220426093021412](https://s2.loli.net/2022/08/15/LPS59YNOapeqrvm.png)

安装完后点击【Finish】按钮完成安装

![image-20220426093118477](https://s2.loli.net/2022/08/15/AwpXEjURKCNVkHt.png)

至此 Node.js 已经安装完成，可以先进行下简单的测试安装是否成功了，后面还要进行环境配置
打开 cmd 窗口，检测环境

![image-20220426093248192](https://s2.loli.net/2022/08/15/fjPiDJHGmlwruQs.png)

安装完后的目录如下图所示：

![image-20220426093559689](https://s2.loli.net/2022/08/15/GEmUqxM9HzdrJge.png)

**★ 此处说明下**：新版的 Node.js 已自带 npm，安装 Node.js 时会一起安装，npm 的作用就是对 Node.js 依赖的包进行管理，也可以理解为用来安装/卸载 Node.js 需要装的东西

### 五、环境配置

说明：这里的环境配置主要配置的是 npm 安装的全局模块所在的路径，以及缓存 cache 的路径，之所以要配置，是因为以后在执行类似：npm install express [-g] （后面的可选参数-g，g 代表 global 全局安装的意思）的安装语句时，会将安装的模块安装到【C:\Users\用户名\AppData\Roaming\npm】路径中，占 C 盘空间。

---

**解决方案**：我希望将全模块所在路径和缓存路径放在我 node.js 安装的文件夹中，则在我安装的文件夹【D:\nodejs】下创建两个文件夹【node_global】及【node_cache】如下图：

![image-20220426094054805](https://s2.loli.net/2022/08/15/1E3gRIT56kPiHmM.png)

创建完两个空文件夹之后，打开 cmd 命令窗口，输入

```
npm config set prefix "D:\nodejs\node_global"
npm config set cache "D:\nodejs\node_cache"
```

![image-20220426094338645](https://s2.loli.net/2022/08/15/vHg8aSBniMtEprJ.png)

接下来设置环境变量，关闭 cmd 窗口，“我的电脑”-右键-“属性”-“高级系统设置”-“高级”-“环境变量

![image-20220426094628236](https://s2.loli.net/2022/08/15/9UiYOQr5usptVfD.png)

进入环境变量对话框，在【系统变量】下新建【NODE_PATH】，输入【D:\nodejs\node_global\node_modules】

![image-20220426095023842](https://s2.loli.net/2022/08/15/TChUxwAoiRG9XHZ.png)

将【用户变量】下的【Path】修改为【D:\nodejs\node_global】

![image-20220426095403874](https://s2.loli.net/2022/08/15/AYBWLjU8lbHqfyu.png)

![image-20220426102657051](https://s2.loli.net/2022/08/15/zkHjmdqO6c8SUfl.png)

### 六、测试

配置完后，安装个 module 测试下，我们就安装最常用的 express 模块，打开 cmd 窗口，
输入如下命令进行模块的全局安装：

```
npm install express -g     # -g是全局安装的意思
###cnpm镜像源###
npm install -g cnpm --registry=https://registry.npmmirror.com
```

![image-20220426104458915](https://s2.loli.net/2022/08/15/FqxcMRdJzvghHNV.png)

![image-20220426104301884](https://s2.loli.net/2022/08/15/2ns8AlNpzoc6Yfx.png)

**安装以及配置结束**

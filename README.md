# 倍投策略

[![Logo](https://img.shields.io/badge/KuCoin-KuMex-yellowgreen?style=flat-square)](https://github.com/Kucoin-academy/Guide)
[![GitHub stars](https://img.shields.io/github/stars/Kucoin-academy/double-strategy.svg?label=Stars&style=flat-square)](https://github.com/Kucoin-academy/double-strategy)
[![GitHub forks](https://img.shields.io/github/forks/Kucoin-academy/double-strategy.svg?label=Fork&style=flat-square)](https://github.com/Kucoin-academy/double-strategy)
[![GitHub issues](https://img.shields.io/github/issues/Kucoin-academy/double-strategy.svg?label=Issue&style=flat-square)](https://github.com/Kucoin-academy/double-strategy/issues)

[![](https://img.shields.io/badge/lang-English-informational.svg?longCache=true&style=flat-square)](README_EN.md)
[![](https://img.shields.io/badge/lang-Chinese-red.svg?longCache=true&style=flat-square)](README_CN.md)

## 策略说明

在众多交易策略之中，有一个很有名同时也是号称“**永远不会输钱**”的交易策略——马丁格尔策略。

### 马丁格尔策略

马丁格尔，是一种基于18世纪流行于法国赌场的交易策略，在赌场游戏系统中盛行至今，号称“永远不输钱”的马丁格尔，目前在大多数赌场依然被限制加仓次数。

**马丁格尔策略的操作准则是：你以一单位赌注开始，在每次赔钱后，将赌注加倍，而在任何一次赢钱后，下一次又回归到一单位赌注**。因此，无论在赢钱之前输了多少次，只要概率让下注者赢一次，**不仅会收回先前到损失，还会获得第一次赌注总额的收益**。

马丁格尔策略从赌场被移植到金融交易市场中，创造了许多盈利奇迹和滑铁卢式的交易亏损。

**该策略认为行情永远会回调——即每一次交易盈利或亏损都是随机独立事件**。

从较长的周期来看这也许是对的，但真实情况往往比这更加复杂，**价格行情既不是随机的，交易者也不可能有无限多的筹码。**

**因此马丁格尔策略适用于震荡行情，一旦走出震荡开始单边行情，就会迎来非常大的风险。**

### 反马丁格尔策略

反马丁格尔策略就是将马丁格尔策略反向操作：**你以一单位赌注开始，在每次赚钱后，将赌注加倍，一直到你所「期待赢的次数」达到，就再从一单位赌注开始押注。如果在未达到「期待赢的次数」就输掉了，同样就从头开始，以一单位赌注重新开始押注**。

这是马丁格尔策略在交易市场上的变种，通常是通过一些指标判断行情进入单边趋势后，在趋势前期通过逐步加仓获取高额利润，并且通过限制次数的方式来控制风险。

马丁格尔策略虽然是一种非常好用的仓位策略，但是该策略同样”盈亏同源“——它的根本缺陷在于默认市场是一种单一态的随机概率事件，**因此在使用它的时候，一定要慎重，最好配合上趋势指标一起使用。**  

**KuCoin**拥有**level3交易数据、强大的撮合引擎、针对api用户提供的手续费折扣**，同时提供**sandbox环境**作为数据测试支撑，帮助你规避风险。

我们仅提供一个简单且不完备的交易策略，使用时**请注意规避风险**，我们希望你能够**在sandbox环境配合其他参数或是策略进行测试调整，我们也不想你成为一个慈善家！！！**

当然，如果这个过程中，你遇到任何问题或是有赚钱的策略想要分享，请在**ISSUE**中反映，我们会努力及时响应。

:point_right: 如果你对该策略有兴趣，请点击**右上角star**，我们会根据star数来衡量策略的**受欢迎程度和后续优化优先级**，你也可以点击**右上角watching**通过接收更新通知来持续关注该项目。

## 如何使用

* 安装Python

  * Windows系统请前往[Python](https://www.python.org/downloads/windows/)官网自行安装，64位请选择1，32位请选择2。

    <img src="./img/python_download.png" style="zoom:50%" />

    * 在开始安装时请注意将以下选项勾选：

      <img src="./img/python_win.png" style="zoom:40%" />

  * MAC OS X安装

    * 打开命令终端，输入以下命令安装Homebrew（安装过程中需要输入**电脑密码**）：

      ```shell
      /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
      ```

    * 在命令终端输入以下命令，安装Python3：

      ```shell
      brew install python
      ```

    * 在命令终端输入以下命令，确认是否安装成功：

      ```shell
      python3 --version
      ```

      ![](./img/python_version.gif)

* 确保你已经安装git (mac 自带该软件,终端输入`which git`，查看安装位置)，未安装者请前往官网[git](https://git-scm.com/)安装。

* 在命令终端输入以下命令，安装项目依赖：

  ```shell script
  pip3 install python-kumex
  ```

  ![pip_install](./img/pip_install.gif)
  
* 在你需要跑策略的位置新建文件夹（例如桌面），**右键**点击新建的文件夹选择**“新建位于文件夹位置的终端窗口”**（**windows系统**：在右键点击文件夹点击**git Bash here**），在弹出的窗口中输入以下命令，克隆项目至本地，完成后本地会新增文件夹**double-strategy**：
  
  ```shell
  git clone https://github.com/Kucoin-academy/double-strategy.git
  ```
  
  ![git_clone](./img/git_clone.gif)
  
* 打开克隆好的项目（**double-strategy**）文件夹，将**config.json.example**文件重命名为**config.json**，并用文本编辑器（比如**记事本**）打开**config.json**，然后完善相关的配置信息：

  ```
  {
    "api_key": "api key",
    "api_secret": "api secret",
    "api_passphrase": "api pass phrase",
    // 是否是沙盒环境  
    "is_sandbox": true
  }
  ```
  
* Mac/Linux **在项目目录下**打开命令终端：

  ```shell
  cd double-strategy
  ```
  * 用以下命令让你的策略运行起来：
  
    ```shell
    ./double_strategy.py
    ```
  
* Windows **在项目目录下**打开命令终端：

  ```shell
  cd double-strategy
  ```
  * 用以下命令让你的策略运行起来：
  
    ```shell
    py double_strategy.py
    ```
  
  


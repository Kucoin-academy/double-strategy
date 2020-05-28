# Double_investment_strategy

[![Logo](https://img.shields.io/badge/KuCoin-KuMex-yellowgreen?style=flat-square)](https://github.com/Kucoin-academy/Guide)
[![GitHub stars](https://img.shields.io/github/stars/Kucoin-academy/double-strategy.svg?label=Stars&style=flat-square)](https://github.com/Kucoin-academy/double-strategy)
[![GitHub forks](https://img.shields.io/github/forks/Kucoin-academy/double-strategy.svg?label=Fork&style=flat-square)](https://github.com/Kucoin-academy/double-strategy)
[![GitHub issues](https://img.shields.io/github/issues/Kucoin-academy/double-strategy.svg?label=Issue&style=flat-square)](https://github.com/Kucoin-academy/double-strategy/issues)

[![](https://img.shields.io/badge/lang-English-informational.svg?longCache=true&style=flat-square)](README.md)
[![](https://img.shields.io/badge/lang-Chinese-red.svg?longCache=true&style=flat-square)](README_CN.md)

## Strategy description

Among most of the trading strategies, there is a well-known as 'never lose money' trading strategy-Martingale strategy.  

### Martingale strategy

Originally, martingale referred to a class of betting strategies that was popular in 18th-century France. It is still popular in the casino system, called "never lose mony" Maringale, it is still limited the times of adding to positions.

**The rule of Martingale strategy: The gambler double their bet after every loss so that the first win would recover all previous losses plus win a profit equal to the original stake**.  

Since Martingale's strategy was applied to financial trading market, it is creating many profit miracles and Waterloo-style losses.  

**The principle of this strategy: The market will always call back, which means each trade profit or loss is a random independent event**  

It may be correct for a long term period, but the truth in market is always more complicated, **as the price is neither random, nor traders have unlimited chips**.   

**Therefore, the Martingale strategy may perform good in shock market. Once breaking shock market, traders would face a very big risk**.

## Anti-martingale strategy

The rule of Anti-martingale is to operate the Martingale strategy in reverse: **The gambler double their bet after every win until approaching the wins in hope, then restart from one bet. If losing before the wins in hope, then restart from one bet, too.**

This is the variation of Maringale in market. In general, it obtains high profits by gradually increasing positions in the early stages of the trend after the traders judged that the market has entered a unilateral trend through some indicators, and controlling the number of times to control the risk.

Martingale strategy is a useful postion strategy, but both of gain and lose are from chaos: its fundamental flaw is that the market is defaulted to a single-state random probability, so it's better to careful use it with trend indicators.

**KuCoin** provides **the transaction data of level 3, great matching engine, and the commission discount specially offers to the API customers**. At the same time, we offer the **sandbox environment** as the data testing support to avoid the risks.

Only a simple and incomplete trading strategy is provided here, so please pay attention to **avoiding risks** when using it. We hope that you can **make test adjustments in the sandbox environment with other parameters or strategies,  as we do not want you to become a philanthropist! ! !**

Surely, if you encounter any problems in this process, or you have a profitable strategy to share, please reflect in **ISSUE**, we will try to respond in a timely manner. 

:point_right: If you are interested in this strategy, please click **the star in the upper right corner**, we will  measure **the popularity of this strategy and subsequent optimization prioritie**s based on the amounts of stars. You can also click **watching in the upper right corner** to continue to follow this project by receiving update notifications. 

## How to use

* Download Python

  * Please download python in [Python](https://www.python.org/) official website for other system requirement(Such as **Windows**), if your computer is 64-bit operating system, please click 1, if it is 32-bit operating system, please click 2.

    <img src="./img/python_download.png" style="zoom:50%" />

    * Please note the following options when starting the installation:

      <img src="./img/python_win.png" style="zoom:40%" />

  * For MAC OS

    * Open terminal and enter the following command to download Homebrew(During the installation, you need to enter the **computer password**):

      ```shell
      /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
      ```

    * Enter the following command in terminal to download Python3:

      ```shell
      brew install python
      ```

    * Enter the following command in terminal to confirm if you download successfully:

      ```shell
      python3 --version
      ```

      ![](./img/python_version.gif)

* Confirm that you have already downloaded git(Mac OS  already has this software, enther `which git` in terminal to check the path of the file）, if you did not download this software, please do it through the [git](https://git-scm.com/) official website.

* Enter the following command in terminal to install the dependency:

  ```shell script
  pip3 install python-kumex
  ```

  ![pip_install](./img/pip_install.gif)
  
* Create a new folder (such as the desktop) at the location where you need to run the strategy, right click on the newly created folder and select "**Create a new terminal window at the folder location**"(For Windows, right click the folder and select "**git Bash here**"), enter the following command in the pop-up window to clone the project to the local, and a folder **double-strategy** will be added locally after completion:
  
  ```shell
  git clone https://github.com/Kucoin-academy/double-strategy.git
  ```
  
  ![git_clone](./img/git_clone.gif)
  
* Open the (**double-strategy**) project you have cloned,  rename **config.json.example** as **config.json**, using text editor(e.g., **notebook**) to open **config.json**, then add the relevant configuration information: 

  ```
  {
    "api_key": "api key",
    "api_secret": "api secret",
    "api_passphrase": "api pass phrase",
    // if sandbox  
    "is_sandbox": true
  }
  ```
  
* Mac/Linux open terminal **in the project directory**: 

  ```shell
  cd double-strategy
  ```
  * Using the following command to run your strategy:
  
    ```shell
    ./double_strategy.py
    ```
  
* Windows open terminal **in the project directory**: 

  ```shell
  cd double-strategy
  ```
  * Using the following command to run your strategy:
  
    ```shell
    py double_strategy.py
    ```
  
  


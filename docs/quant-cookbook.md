## docker

### Install using the repository

ubuntu 18.10 暂不支持 docker-ce, 安装 ubuntu 18.04，然后安装 docker

Update the apt package index:

```s
$ sudo apt-get update
```

Install packages to allow apt to use a repository over HTTPS:

```s
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

Add Docker’s official GPG key:

```s
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.

```s
$ sudo apt-key fingerprint 0EBFCD88
```

```
pub   4096R/0EBFCD88 2017-02-22
      Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid                  Docker Release (CE deb) <docker@docker.com>
sub   4096R/F273FCD8 2017-02-22
```

### INSTALL DOCKER CE

Update the apt package index.

```
$ sudo apt-get update
```

Install the latest version of Docker CE, or go to the next step to install a specific version:

```
$ sudo apt-get install docker-ce
```

Verify that Docker CE is installed correctly by running the hello-world image.

```
$ sudo docker run hello-world
```

## python

### 安装 conda

```
$ wget https://repo.anaconda.com/archive/Anaconda3-5.3.1-Linux-x86_64.sh
$ chomd +x Anaconda3-5.3.1-Linux-x86_64.sh
$ ./Anaconda3-5.3.1-Linux-x86_64.sh

Please, press ENTER to continue
>>>

$ source ~/.bashrc

$ conda -V

#设置matplotlib的backend（没有图形化界面的情况下）
$ echo "backend: Agg" > ~/.config/matplotlib/matplotlibrc
```

### 更改 Anaconda 源，提高下载速度

conda 官方的服务器在国外，因此国内的网络环境使用 conda 可能会比较慢，建议您根据自己的网络环境选择是否更换 conda 源。

清华大学提供了 Anaconda 的仓库镜像，我们只需要配置 Anaconda 的配置文件，添加清华的镜像源，然后将其设置为第一搜索渠道即可： 运行以下命令行:
只对 linux 有用，windows 无用

```
conda config --add channels 'https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/'
conda config --set show_channel_urls yes
```

设置好源后，就可以使用 conda install 【包名】 安装需要的 Python 库了。大部分情况下，建议使用 conda 来安装 Python 数据分析相关的库，因为 conda 做了很多的优化和版本依赖关系的管理。如果没有相关的库，则使用 pip install 【包名】 的方式来安装。

### conda 虚拟环境

**创建 conda 虚拟环境 (`env_name` 是您希望创建的虚拟环境名)**

```
$ conda create --name env_name python=3.5

# 如您想创建一个名为rqalpha的虚拟环境
$ conda create --name rqalpha python=3.5
```

**使用 conda 虚拟环境**

```
$ source activate env_name
# 如果是 Windows 环境下 直接执行 activcate
$ activate env_name
```

激活环境后再次

```
python --version
```

检查当前 python 版本

**退出 conda 虚拟环境**

```
$ source deactivate env_name
# 如果是 Windows 环境下 直接执行 deactivate
$ deactivate env_name
```

**删除 conda 虚拟环境**

```
$ conda-env remove --name env_name
```

**查看安装了哪些包**

```
conda list

```

**查看当前存在哪些虚拟环境**

```
conda env list 或 conda info -e
```

**检查更新当前 conda**

```
conda update conda
```

**安装包到虚拟环境中**

```
# tensorflow 为虚拟环境名称
conda install -n tensorflow numpy
```

### 安装 ta-lib

```
conda install -c quantopian ta-lib
```

## conda 环境下修改 notebook 路径

conda 命令行下

```
jupyter notebook --generate-config
```

`C:\Users\用户名\.jupyter` 生成 `jupyter_notebook_config.py`
修改路径

```
c.NotebookApp.notebook_dir='D:/github-projects'
```

## 收益指标

- https://www.ricequant.com/api/python/chn#backtest-results-rqana
- [量化策略的风险评价指标](https://zhuanlan.zhihu.com/p/40853197)
- [量化交易学习笔记 (一) ---- 量化交易基本名词概念](https://blog.csdn.net/u013817676/article/details/80713755)
- [风险指标](https://www.joinquant.com/help/api/help?name=api#%E9%A3%8E%E9%99%A9%E6%8C%87%E6%A0%87)

基准收益

Total Returns
Annual Returns
Alpha 阿尔法
Beta 贝塔
Sharpe 夏普比率
Sortina 索提诺比率
information Ratio 信心比率
Benchmark Returns
Benchmark Annual
Volatility 收益波动率
MaxDrawdown 最大回撤
Tracking Error
Downside Risk
MaxDD/MaxDDD

### Portfolio 对象

cash 可用资金，为子账户可用资金的加总
frozen_cash 冻结资金，为子账户冻结资金加总
total_returns 投资组合至今的累积收益率
daily_returns 投资组合每日收益率
daily_pnl 当日盈亏，子账户当日盈亏的加总
market_value 投资组合当前的市场价值，为子账户市场价值的加总
total_value 总权益，为子账户总权益加总
units 份额。在没有出入金的情况下，策略的初始资金
unit_net_value 单位净值
static_unit_net_value 静态单位权益
transaction_cost 当日费用
pnl 当前投资组合的累计盈亏
start_date 策略投资组合的回测 / 实时模拟交易的开始日期
annualized_returns 投资组合的年化收益率
positions 一个包含所有仓位的字典，以 order_book_id 作为键，position 对象作为值，关于 position 的更多的信息可以在下面的部分找到。

## 量化交易基本名词概念

- [金融量化 alpha 和 beta 值的意义](https://blog.csdn.net/yezi113yezi/article/details/81078128)

### 三大经典指标

1. 夏普比率 (Shape Ratio)，也称夏普指数，它指的是投资回报与风险的比例。夏普比率代表投资人每多承担一份风险，就可以拿到几份回报，若为正值，代表基金报酬率高于波动风险；若为负值，代表基金操作风险大于报酬率。比例越高，投资组合越佳。

2. 詹森指数 (Jensen)，又称为阿尔法值，是衡量基金超额收益大小的一种指标，这个指标综合考虑了基金收益与风险因素，比单纯的考虑基金收益大小要更科学。

3. 特雷诺指数 (Treynor Ratio，TR)，是每单位风险获得的风险溢价。特雷诺指数越大，单位风险溢价越高，绩效越好；相反，特雷诺指数越小，单位风险溢价越低，绩效越差。

**策略收益 (total returns)**，策略实际收益额。

**基准收益 (Benchmark Returns)**，策略最低收益额。

**基准收益率 (Benchmark Yield)**，也称基准折现率，投资项目最低标准的收益水平，即选择特定的投资机会或投资方案必须达到的逾期收益率。

**阿尔法 (Alpha)**，是高于预期收益率的超额收益率。阿尔法策略基于 CAPM 模型。传统阿尔法策略是在基金经理建立 Beta 部位的头寸后，通过衍生品对冲 Beta 部位的风险，从而获得正的阿尔法收益。

**贝塔 (Beta)**，按照 CAPM 模型的规定，Beta 系数是用以度量一项资产系统风险的指数，是用来衡量一种证券或一个投资组合相对总体市场的波动性的一种风险评估工具。

**索提诺比率 (Sortino Ratio，SR)**，与夏普比率类似，所不同的是它区分了波动的好坏，因此在计算波动率时它所采用的不是标准差，而是下行标准差。这其中的隐含条件是投资组合的上涨 (正回报率) 符合投资人的需求，不应该计入风险调整。和夏普比率类似，这个比率越高，表明基金承担相同单位下行风险能获得更高的超额回报率。索提诺比率可以看错是夏普比率在衡量对冲基金 / 私募基金是的一种修正方式。

**信息比率 (Information Ratio,IR)**，也称作绩效评估比率 (Appraisal Ratio)。信息比率是从主动管理角度描述风险调整后的收益，它不同于夏普比率从绝对收益和总风险角度来描述。信息比率越大，说明所获得的超额收益越高，策略收益持续优于大盘的程度越高。计算方式是，将基金报酬率减去同类基金或者大盘报酬率 (剩下的值为超额报酬)，再除以该超额报酬的标准差。

**策略波动 (Algorithm Volatility)**, 是指回报率在策略执行期内所表现出的波动率。

**基准波动率 (Benchmark Volatility)**，基准指数的波动范围，用来测量基准的风险性，波动越大代表基准风险越高。

**下行风险 (Downside Risk)**，是指由于市场环境变化，未来价格走势有可能低于分析师活投资者所预期的目标价位。下行风险是投资有可能出现的最坏的情况，也是投资者可能需要承担的损失。

**最大回撤率 (drawdown)**，是指该金融产品历史上一段时间的最大跌幅。最大回撤率用来描述买入产品后可能出现的最糟糕的情况。最大回撤率是一个重要的风险指标，对于对冲基金和量化策略交易来说，该指标比波动率还重要。

**Alpha 策略与 Beta 策异同**：Alpha 策略与 Beta 策略是两类基于不同出发点来获取超过大盘表现的超额收益的投资策略。Alpha 策略是依靠精选行业和个股来超越大盘；Beta 策略是依靠准确地把握市场大势、准确择时来获得超越大盘的收益。

**Beta 系数**表示的是相对市场收益率变动、个别资产收益率同时发生变动的程度，是一个标准化的度量单项资产对市场组合方差贡献的指标。若一只股票的价格和市场的价格波动性是一致的，那么这只股票的 Beta 值就是 1. 如果一只股票的 Beta 值是 1.8，那么意味着当市场价格上升 10% 时，该股票价格上升 18%；在市场价格下降 10% 时，该股票的价格也会下降 18%。当 Beta 值处于较高位置时，投资者便会因为股票的风险高，而相应提升股票的预期回报率。

**CAPM(Capital Asset Pricing Model, 资本资产定价模型) 模型**，它是为了研究资本的收益与风险之间的定量关系。

E(rD)=rf+βD|E(rM)−rf|E(rD)=rf+βD|E(rM)−rf|
其中：
E(rD)E(rD) - 股票的期望回报率
rfrf - 无风险回报率
βDβD - 该股票的贝塔系数
E(rM)E(rM) - 市场所有股票的平均回报率

示例
如果一只股票的 Beta 值是 2.5，无风险回报率是 2%，市场回报率是 10%，那么市场溢价就是 8%，股票风险溢价为 20%（2.5\*8%，beta 值乘以市场溢价），那么股票的预期回报率为 22%（20%+2%，即股票的风向溢价加上无风险回报率）。

## 报表

```
净利润
总盈利
总亏损
盈利因子
交易次数
胜率
平均利润
平均盈利/平均亏损
最大盈利
最大亏损
最大连续盈利次数
最大连续盈利额
最大连续亏损次数
最大连续亏损额
总交易时间
平均持仓周期
最大使用资金
手续费
滑点
收益率
年化收益
夏普比率
总交易时间
持仓时间
持仓时间比率
最大回撤值
最大回撤值时间
最大回撤比率
最大回撤比率时间
```

Returns out[:]= (close[-1] - close[0]) / close[0]
DailyReturns  
MaxDrawdown

aggregate_returns 累计收益
alpha
alpha_aligned
alpha_beta
alpha_beta_aligned
annual_return 年化收益
annual_volatility 年度波动率
beta
beta_aligned
cagr 复合年增长率
calmar_ratio
capture
conditional_value_at_risk
cum_returns
cum_returns_final
down_alpha_beta
down_capture
downside_risk
excess_sharpe
max_drawdown
omega_ratio
simple_returns

- [empyrical](https://github.com/quantopian/empyrical) Common financial risk and performance metrics. Used by zipline and pyfolio.

## python 模块

- https://www.ricequant.com/api/python/chn#python-lib-modules

## R 平方和 beta 之间的关系是什么？

Beta 和 R 平方是两个相关但不同的度量。具有高 R 平方的共同基金与基准高度相关。如果 beta 也很高，它可能会产生比基准更高的回报，特别是在牛市中。R 平方衡量资产价格的每个变化与基准相关的程度。Beta 测量这些价格变化与基准相关的程度。R-squared 和 beta 一起使用可以让投资者全面了解资产管理者的表现。

### R-Squared 衡量绩效如何与基准相匹配

R 平方是衡量基准产生的资产或基金业绩百分比的指标。它被报告为 0 到 100 之间的数字。假设的 R 平方为 0 的共同基金根本没有与其基准相关。R 平方为 100 的共同基金正好与其基准的表现相匹配。

Beta 是衡量基金或资产对基准相关变动的敏感度的指标。beta 为 1.0 的共同基金与其基准测试完全一样敏感或不稳定。beta 为 0.80 的基金敏感性或波动性降低 20％，beta 为 1.20 的基金敏感度或波动性提高 20％。

Alpha 是第三项指标，它衡量资产管理公司在基准利润也能获利时获取利润的能力。报告的 Alpha 数字小于，等于或大于 1.0。经理的阿尔法越高，他或她从基础基准的移动中获利的能力就越大。一些表现最佳的对冲基金经理使用标准普尔 500 指数作为基准，实现了高达 5 或更高的短期阿尔法。

R 平方数低于 50 的资产的 α 和 β 被认为是不可靠的，因为资产的相关性不足以进行有价值的比较。低 R 平方或 β 不一定使投资成为一个糟糕的选择，它仅仅意味着它的表现在统计上与其基准无关。（有关相关阅读，请参阅：了解波动率测量。）

## 了解波动率测量

在考虑基金的波动性时，投资者可能会发现难以确定哪个基金将提供最佳的风险 - 回报组合。许多网站免费为共同基金提供各种波动性指标; 然而，很难不仅知道数字的含义，还知道如何分析它们。此外，这些数字之间的关系并不总是显而易见的。继续阅读以了解四种最常见的波动率指标以及它们如何应用于基于现代投资组合理论的风险分析类型。

### 最优投资组合理论与共同基金

对投资组合收益与风险之间关系的一种考察是有效前沿，这是现代投资组合理论的一部分。该曲线由绘制波动率表示的回报和风险的图表形成，其由标准偏差表示。根据现代投资组合理论，考虑到波动的数量，位于曲线上的资金正在产生可能的最大回报。

![](https://i.investopedia.com/inv/articles/site/mutualfund/072303_1.gif)

随着标准差的增加，回报也会增加。在上图中，一旦投资组合的预期收益达到一定水平，投资者必须承担大量波动，以获得小幅回报。显然，风险 / 回报关系远远低于曲线的投资组合并不是最优的，因为投资者为了小额回报而承受了大量的不稳定性。为了确定拟议基金是否具有所获得的波动率的最佳回报，投资者需要对基金的标准差进行分析。

现代投资组合理论和波动率并不是投资者用来分析市场中许多不同因素造成的风险的唯一手段。事情就是这样的风险承受能力和投资策略影响投资者如何看待他或她所面临的风险。以下是其他四项措施。（有关相关阅读，请参阅：您的风险承受能力是多少？）

#### 1. 标准偏差

与许多统计测量一样，标准差的计算可能令人生畏，但由于该数字对于那些知道如何使用它的人非常有用，因此有许多免费的共同基金筛选服务可以提供标准的资金偏差。

标准差基本上反映了基金的波动性，表明回报在短时间内大幅上涨或下跌的趋势。易变的安全性也被认为是更高的风险，因为其性能可能随时在任一方向快速变化。基金的标准差通过衡量基金相对于其平均收益波动的程度来衡量这种风险。

例如，四年回报率为 3％的基金平均或平均为 3％。该基金的标准差将为零，因为基金在任何一年的回报与其四年平均值 3％没有差异。另一方面，过去四年每年回报 - 5％，17％，2％和 30％的基金平均回报率为 11％。该基金也会出现高标准差，因为每年基金的回报与平均回报不同。因此，该基金风险较大，因为它在短期内在负收益和正收益之间波动很大。（有关相关阅读，请参阅：使股票成为风险投资的 4 件事。）

请记住，因为波动率只是影响证券的风险的一个指标，基金稳定的过去表现并不一定是未来稳定的保证。由于不可预见的市场因素会影响波动性，因此今年标准差接近或等于零的基金可能在下一年表现不同。

为了确定基金如何最大化其波动性收益，您可以将基金与具有类似投资策略和类似回报的基金进行比较。具有较低标准差的基金将更加优化，因为它最大化了所获得的风险量的收益。请考虑以下图表：

![](https://i.investopedia.com/inv/articles/site/mutualfund/072303_2.gif)

对于标准普尔 500 基金 B，投资者将获得比基金 A 获得相同回报所需的更大波动风险。基金 A 将为投资者提供最佳风险 / 回报关系。（有关更多信息，请参阅： 波动率的使用和限制。）

#### 2. Beta

虽然标准差根据其在一段时间内的回报差异来确定基金的波动性，但 β 是另一种有用的统计指标，它将基金的波动率（或风险）与其指数或基准进行比较。beta 非常接近 1 的基金意味着基金的表现与指数或基准紧密匹配。大于 1 的 beta 表示比整体市场更大的波动率，而小于 1 的 beta 表示波动率低于基准。

例如，如果一只基金的标准普尔 500 指数为 1.05 ，该基金的指数已经比指数上涨了 5％。因此，如果标准普尔 500 指数上涨 15％，该基金预计将增加 15.75％。另一方面，beta 为 2.4 的基金预计将比其相应指数多移动 2.4 倍。因此，如果标准普尔 500 指数上涨 10％，该基金预计将上涨 24％，如果标准普尔 500 指数下跌 10％，该基金预计将下跌 24％。

投资者预计市场看涨可能会选择表现出高赌注的基金，从而增加投资者击败市场的机会。如果投资者预计市场在不久的将来看跌，那么贝塔价格小于 1 的基金是一个不错的选择，因为它们的价值下降幅度低于指数。例如，如果一只基金的 beta 为 0.5，标准普尔 500 指数下跌 6％，那么该基金预计只会下跌 3％。

由于影响基金波动性的市场风险以外的其他因素，Beta 本身是有限的，可能会出现偏差。（有关相关阅读，请参阅： 通过 Beta 构建多样性。）

#### 3. R-Squared

如果共同基金的 beta 值是根据适当的基准来衡量的，那么基金的 R 平方显示投资者。衡量基金走势与指数走势的相关性，R 平方描述了基金波动率与市场风险之间的关联程度，或者更具体地说，是基金波动率是日常交易的程度。整体市场经历的波动。

R 平方值的范围在 0 到 100 之间，其中 0 表示最小相关，100 表示 ​​ 完全相关。如果基金的 beta 值的 R 平方值接近 100，那么基金的 beta 值应该是可信的。另一方面，接近 0 的 R 平方值表明 β 不是特别有用，因为该基金正在与不适当的基准进行比较。

例如，如果债券基金被判断为标准普尔 500 指数，则 R 平方值将非常低。像雷曼兄弟综合债券指数这样的债券指数对于债券基金来说是一个更合适的基准，因此得到的 R 平方值会更高。显然，股市中明显存在的风险与债券市场相关的风险不同。因此，如果债券的 beta 是使用股票指数计算的，那么 beta 就不值得信赖。（有关更多信息，请参阅：如何在 Excel 中计算 R-Squared。）

一个不合适的基准将不仅仅是 beta。Alpha 是使用 beta 计算的，因此如果基金的 R 平方值很低，那么也不要相信给出的 alpha 数字。我们将在下一节中介绍一个例子。

#### 4. Alpha

到目前为止，我们已经学会了如何检验波动率所带来的风险，但我们如何衡量因市场波动以外的因素而承担风险而获得的额外回报呢？输入 alpha，它可以衡量这种额外风险是否有助于基金表现优于相应的基准。使用 beta，alpha 的计算将基金的业绩与基准风险调整后的收益进行比较，并确定基金在给定相同风险的情况下是否跑赢市场。

例如，如果基金的 α 为 1，则意味着该基金的表现优于基准 1％。负面的 alphas 很糟糕，因为它们表明该基金的表现落后于基金投资者承担的额外基金特定风险。

#### 底线

对这四种统计指标的这种解释为您提供了使用它们来应用最优投资组合理论前提的基本知识，该理论利用波动率来确定风险，并提供一个指导方针，用于确定基金波动率中有多少具有更高的回报潜力。这些数字可能难以理解，因此如果您使用它们，了解它们的含义非常重要。

这些计算仅适用于一种风险分析。如果您决定购买共同基金，重要的是要了解影响波动性的因素，并指出共同基金带来的风险。（有关进一步阅读，请参阅： 5 种衡量共同基金风险的方法。）

## empyrical

- simple_returns
- cum_returns
- cum_returns_final
- aggregate_returns
- max_drawdown
- max_drawdown_translation
- annual_ret
- annual_volatility
- calmar
- omega
- sharpe_ratio
- sharpe_translation_same
- sharpe_translation_diff
- sharpe_translation_1
- sharpe_noise
- downside_risk
- downside_risk_noisy
- downside_risk_trans
- downside_risk_std
- sortino

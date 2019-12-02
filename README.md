#### 注意：查表要转化(考试是上侧分位点，课本上的表为下侧分位点)
#### 查表方法
+ N(0,1)
    + 分布表
      $$p\{|N(0,1)|<c\}=2\Phi(c)-1$$

      $$p\{|N(0,1)|>c\}=1-2\Phi(c)$$
    + 分位数表
  
      单侧时，若查$\mu_\alpha$,则在表中找$\mu_{1-\alpha}$;双侧另查
      由于标准分布是对称的，故$\mu_{1-\alpha}=-\mu_\alpha$
+ $\chi^2(n)$

  若要查$\chi_\alpha^2$的值，则在表中找$\chi_{1-\alpha}^2$的值(上侧$\alpha$即下侧$1-\alpha$)
+ $t(n)$dx

  单侧时，若查$t_\alpha(n)$,则在表中找$t_{1-\alpha}(n)$;双侧另查。
  由于t分布是对称的，故$t_{1-\alpha}(n)=-t_\alpha(n)$
+ $F(n1,n2)$

  若要查$F_\alpha(n1,n2)$的值，则在表中找$F_{1-\alpha}(n1,n2)$的值(上侧$\alpha$即下侧$1-\alpha$)
  $F_{1-\alpha}(n_1,n_2)=\frac{1}{F_\alpha(n_2,n_1)}$
#### 卡方检验(离散)
总体X有k个取值$a_i$

$H_0:p\{X=a_i\}=p_i,1\leq i\leq k$,也即服从题中某分布，可写作$H_0:F(x)=F_0(x),H_1:F(x)\neq F_0(x),F_0(x)$为某分布\{可以是泊松等有名离散分布(含参一定是)，也可以是知概率的无名离散分布\}的分布函数
+ 不含参数

    先计算出$p_i$
    + 检验统计量
      $$K^2=\frac{1}{n}\sum_{i=1}^k\frac{v_i^2}{p_i}-n \quad (v_i是a_i取值的个数,n为样本总个数)$$
    + 拒绝域
      $$K^2>\chi_\alpha^2(k-1)$$
+ 含r个未知参数

    计算出这r个参数的极大似然估计值，然后计算出$\hat{P}_i$(估计值)
    + 检验统计量
      $$K^2=\frac{1}{n}\sum_{i=1}^k\frac{v_i^2}{\hat{p}_i}-n \quad (v_i是a_i取值的个数，n为样本总个数)$$
    + 拒绝域
      $$K^2>\chi_\alpha^2(k-r-1)$$
#### 列联表检验(卡方分析)
+ 检验统计量
$$K^2=N[\sum_{i=1}^s\sum_{j=1}^t\frac{n_{ij}^2}{n_{i.}n_{.j}}-1]$$
+ 拒绝域
$${K^2>\chi_\alpha^2((s-1)(t-1))}$$
+ 四格表检验统计量
$$K^2=\frac{n(n_{11}n_{22}-n_{12}n_{21})^2}{n_{1.}n_{2.}n_{.1}n_{.2}}$$
+ 拒绝域
$${K^2>\chi_\alpha^2(1)}$$

$$\chi_{0.01}^2(1)=6.63  \quad  \chi_{0.05}^2(1)=3.84 $$

#### 单因素方差分析
+ 假设
$H_0:\alpha_1=...=\alpha_r$,即分类变量x对数值变量y没有显著影响。
+ 统计量
$$(总平方和)TSS=\sum_{i=1}^r\sum_{j=1}^{n_i}(y_{ij}-\overline{y})^2$$

$$(自变量平方和)CSS=\sum_{i=1}^r n_i(\overline{y_i}-\overline{y})^2$$

$$(残差平方和)RSS=\sum_{i=1}^r\sum_{j=1}^{n_i}(y_{ij}-\overline{y_i})^2$$

$$F比=\frac{n-r}{r-1}\frac{CSS}{RSS} \quad F\sim(r-1,n-r)$$

+ 单因素方差分析表
  
$$ CMS=\frac{CSS}{r-1} \quad RMS=\frac{RSS}{n-r} \quad F-比=\frac{CSM}{RMS}$$

<table style="margin-left:25%">
  <tr>
    <th>方差来源</th>
    <th>平方和</th>
    <th>自由度</th>
    <th>均方</th>
    <th>F-比</th>
  </tr>
  <tr>
    <td>分类变量</td>
    <td>CSS</td>
    <td>r-1</td>
    <td>CMS</td>
    <td rowspan="2">F-比值</td>
  </tr>
  <tr>
    <td>残差变量</td>
    <td>RSS</td>
    <td>n-r</td>
    <td>RMS</td>
  </tr>
  <tr>
    <td>总计</td>
    <td>TSS</td>
    <td>n-1</td>
    <td></td>
    <td></td>
  </tr>
</table>

+ 拒绝域
$${F\geq F_\alpha(r-1,n-r)}$$

满足拒绝域，这说明有显著影响；不满足拒绝域则无显著影响。

#### 贝叶斯估计
+ 课后28题定理
  
  损失函数为$L(\theta,d)=\lambda(\theta)(\theta-d)^2$时，
  则$\theta$的贝叶斯估计量为

  $$\hat{d}(x_1,...,x_n)=\frac{E[\theta\lambda(\theta)|x_1,...,x_n]}{E[\lambda(\theta)|x_1,...,x_n]}$$

+ 课后30题定理
  
  损失函数为$L(\theta,d)=|\theta-d|$时，
  则$\theta$的贝叶斯估计量为
  $\hat{d}(x_1,...,x_n)=\theta$的后验分布的`中位数`
  
#### 后验可能的分布
+ $\beta$分布
  $$f(x)=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}x^{\alpha-1}(1-x)^{\beta-1}$$

  $$x\sim Beta(\alpha,\beta)$$

  $$E(X)=\frac{\alpha}{\alpha+\beta} \quad D(X)=\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$$

+ $\Gamma$分布$(P_{8})$
  $$f(x)=\frac{\lambda^\alpha }{\Gamma(\alpha)}x^{\alpha-1}e^{-\lambda x}$$

  $$x\sim\Gamma(\alpha,\lambda)$$

  $$E(X)=\frac{\alpha}{\lambda} \quad D(X)=\frac{\alpha}{\lambda^2} \quad E(X^2)=\frac{\alpha(\alpha+1)}{\lambda^2}$$ 

  参数$\lambda$的指数分布是$\Gamma(1,\lambda)$&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 自由度n的$\chi^2(n)$是$\Gamma(\frac{n}{2},\frac{1}{2})$ 

+ $I\Gamma$分布$(P_{73})$
  $$f(x)=\frac{\lambda^\alpha x^{\alpha-1}}{\Gamma(\alpha)}e^{-\lambda x} \quad (x>0)$$

  $$\frac{1}{X}\sim I\Gamma(\alpha,\lambda)$$

  $$E(\frac{1}{X})^k=\frac{\lambda^k\Gamma(\alpha-k)}{\Gamma(\alpha)}\quad E(\frac{1}{X})=\frac{\lambda}{\alpha-1}$$ 

#### 抽样分布
+ 三大抽样分布
  
    + $\chi^2$分布
      $$E(X)=n,D(X)=2n$$

      $$如果X,Y独立,X+Y \sim \chi^2(n_1+n_2)$$
    + t分布
      $$t=\frac{X}{\sqrt{\frac{Y}{n}}} \quad (X\sim N(0,1),Y\sim\chi^2(n)=>t\sim t(n))$$

      $$E(t(n))=0 \quad D(t(1))=\frac{n}{n-2}(n\geq3)$$
    + F分布
      $$ F=\frac{X/n_1}{Y/n_2} \quad (X\sim \chi^2(n_1),Y\sim \chi^2(n_2))$$
      $$ 若F\sim F(n_1,n_2),则\frac{1}{F}\sim F(n_2,n_1)$$
      $$ 若T\sim t(n),则T^2 \sim F(1,n) $$
+ 定理
  
    前提：正态总体$X\sim N(\mu,\sigma^2)$。
    $$\frac{\sqrt{n}(\overline{X}-\mu)}{\sigma}\sim N(0,1)$$
    $$\frac{\sum_{i=1}^n (x_i-\overline{x})^2}{\sigma^2}=\frac{(n-1)S^2}{\sigma^2}\sim\chi^2(n-1)\quad (也可用作\sigma的检验,习题三第7题)$$
    $$\frac{\sqrt{n}(\overline{X}-\mu)}{S}\sim t(n-1)$$
    $$\overline{X}与S^2独立$$

#### 最小无偏估计
+ fisher信息
+ R-C下界
+ 有效率
  
#### 区间估计(置信度为1-$\alpha$)
+ 思想
    + 单正态总体
    + 双正态总体
    + 指数分布
    + 0-1分布总体
+ 常见的枢轴量和置信区间
    + 单正态总体
    + 双正态总体
    + 指数分布
    + 0-1分布总体

#### 假设检验(显著性水平为$\alpha$)
+ 思想
  - 单边

    假设所检验的估计量为$\theta$,它的一个良好的点估计为$\hat{\theta}$,根据对立假设可给出一个范围，`假设`是$\hat{\theta}>C_1$(小于同理),则需满足$P\{\hat{\theta}>C_1\}=\alpha$,但由于我们并不知道$\hat{\theta}$的分布，故无法确定$C_1$,所以需要我们找一个统计量(由$\hat{\theta}$变化得到),假设为$F\sim F(n_1,n_2)$,则会有$p\{F>C_2\}=\alpha$,这样很明显可以得到$C_2=F_\alpha(n1,n2)$,故得到拒绝域为$F>F_\alpha(n1,n2)$
  - 双边(针对$H_1$：$\theta \neq \theta_0$)
  
    假设所检验的估计量为$\theta$,它的一个良好的点估计为$\hat{\theta}$,根据对立假设可给出一个范围。`假设`是$|\hat{\theta}-\theta_0|>C_1$,则需满足$P\{|\hat{\theta}-\theta_0|>C_1\}=\alpha$,但由于我们并不知道$|\hat{\theta}-\theta_0|$的分布，故无法确定$C_1$,所以需要我们找一个统计量(由$\hat{\theta}$变化得到)，统计量我个人分一下两种情况。
      - 正态/t分布(对称)
  
        假设统计量为$U\sim N(0,1)$,则会有$p\{|N|>C_2\}=\alpha$,这样很明显可以得到$C_2=\mu_{\alpha/2}(0,1)$,故得到拒绝域为$|U|>\mu_{\alpha/2}(0,1)$,也即$\{U>\mu_{\alpha/2}(0,1)\quad or \quad U<-\mu_{\alpha/2}(0,1)=\mu_{1-\alpha/2}(0,1)\}$
      - $\chi^2或者F分布$(不对称)

        假设统计量为$\chi^2(n)$,但由于其肯定大于0，所以它的拒绝域的形式不是类似于上面的绝对值形式，而是$p\{\chi^2(n)>C_1\}+p\{\chi^2(n)<C_2\}=\alpha$这种形式，但是上述两个概率哪个大哪个小通常不确定(而上述对称的就没有这种顾虑)，所以就对半分，即最终拒绝域为$\{\chi^2(n)>\chi^2_{\alpha/2}(n)\quad or \quad \chi^2(n)<\chi^2_{1-\alpha/2}(n)\}$

+ 常见的统计量和拒绝域(查)
    + 单正态总体
      + 估计均值
        + $\sigma^2$已知
        + $\sigma^2$未知
      + 估计方差
        + $\mu$已知
        + $\mu$未知
    + 双正态总体
    + 指数分布总体
    + 0-1分布总体

+ 非正态总体均值的假设检验

#### 线性回归
+ 最小二乘估计
  $$S=X^TX$$
  $$\hat{\beta}=(X^TX)^{-1}X^TY=S^{-1}X^TY$$  
  $$\hat{\sigma}^2=\frac{1}{n-k-1}Y^T(I_n-XS^{-1}X^T)Y$$
  > + 最小二乘估计是无偏估计，上述计算过程见PPT
  > + $\hat{\sigma}^2$的估计经过修正，修正原因见PPT
+ 估计量的分布
  $$\hat{\beta}\sim N(\beta,\sigma^2S^{-1})$$
  $$\frac{n-k-1}{\sigma^2}\hat{\sigma}^2\sim\chi^2(n-k-1)$$
  $$\hat{\beta}与\hat{\sigma}^2相互独立$$
#### 一元线性回归
+ 基本知识
  $$L_{xx}=\sum_{i=1}^n(x_i-\overline{x})^2$$
  $$L_{yy}=\sum_{i=1}^n(y_i-\overline{y})^2$$
  $$L_{xy}=\sum_{i=1}^n(x_i-\overline{x})(y_i-\overline{y})=\sum_{i=1}^nx_iy_i-n\overline{x}\,\overline{y}$$
  - 参数的估计量
    $$\hat{\beta}_0=\overline{y}-\hat{\beta}_1\overline{x} \quad \hat{\beta}_1=\frac{L\_{xy}}{L\_{xx}}$$

    $$\hat{\sigma}^2=\frac{1}{n-2}(L_{yy}-\hat{\beta}_1 L\_{xy})$$
  > 上述参数的计算过程见PPT左侧笔记（比较重要）
  - 变量关系强度的量化
    $$r=\frac{L_{xy}}{\sqrt{L_{xx}L_{yy}}}$$
    $$r^2=\frac{L_{xy}^2}{L_{xx}L_{yy}}$$
  > 在产生因变量变化的所有因素中，该自变量占据了其中$r^2*100$%的份额


+ 估计量的分布
  1. $$\hat{\beta_0}\sim N(\beta_0,\sigma^2(\frac{1}{n}+\frac{\overline{x}^2}{L_{xx}}))$$

  2. $$\hat{\beta_1}\sim N(\beta_1,\frac{\sigma^2}{L_{xx}})$$

  3. $\hat{\beta_0}$与$\hat{\beta_1}$不独立，协方差为
  $$Cov(\hat{\beta_0},\hat{\beta_1})=-\sigma^2\frac{\overline{x}}{L_{xx}}$$

  4. $\sigma^2$与$\hat{\beta_0}$和$\hat{\beta_1}$都独立，并且
  $$\frac{n-2}{\sigma^2}\hat{\sigma}^2\sim\chi^2(n-2)$$
  
+ 检验回归关系是否显著(对$\hat{\beta}_1$的参数检验)
  - $H_0:\beta_1=0$,即回归不成立 $\quad H_1:\beta_1 \ne 0$,即回归成立
  - 统计量(最原始的，由良好的点估计$\hat{\beta}\_1$转化得到): 
     $$\frac{\hat{\beta}\_1}{\hat{\sigma}}\sqrt{\sum\_{i=1}^n(x_i-\overline{x})^2}\sim t(n-2)$$
    更多的是采用: (原理: $t^2(n)\sim F(1,n)$。原因:绝对值太烦了不好计算)
    $$\frac{\hat{\beta}\_1^2}{\hat{\sigma}^2}L\_{xx}\sim F(1,n-2)$$
    即,(代入)
    $$\frac{(n-2)L\_{xy}^2}{L_{xx}L_{yy}-L_{xy}^2}\sim F(1,n-2)$$
    则，统计量如下
    $$F=\frac{(n-2)r^2}{(1-r^2)}$$
  - 否定域
    $${F>F_\alpha(1,n-2)}$$
    若满足否定域，即$H_0$被否定，则认为回归方程成立
  > + 此处构造出的否定域形式不满足我们上面假设检验思想，因为F是原始统计量平方得到的，已经不是最初的统计量，所以本应该是双边的否定域，由于平方的缘故变成了单边。
  > + 上述统计量的构造思路？
  > + 此处可以思考对$\hat{\beta}_0$的参数检验，统计量该如何构造？
+ 区间估计(PPT上是对$\hat{\beta}_1$的区间估计)
  - 枢轴量：(掌握构造枢轴量的思路)
    $$\frac{\hat{\beta}\_1-\beta_1}{\hat{\sigma}}\sqrt{\sum\_{i=1}^n(x_i-\overline{x})^2}\sim t(n-2)$$
  - 置信区间:
    $$(\hat{\beta}\_1\pm \frac{\hat{\sigma}}{\sqrt{\sum\_{i=1}^n(x_i-\overline{x})^2}}t_{\alpha/2}(n-2))$$

  > + 上述枢轴量的构造思路？
  > + 此处可以思考对$\hat{\beta}_0$的区间估计，枢轴量该如何构造？
  > + 以及16年的最后一题？








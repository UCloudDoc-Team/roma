

# VPC（阿里云）手动接入

*即阿里云私有网络接入罗马*

**注：由于手动接入阿里云 VPC 到罗马时，操作较为繁琐，且对其他 VPC 的接入及撤消流程都制造了额外的操作步骤，因此，接入阿里云 VPC
到罗马时，强烈建议使用 [VPC（阿里云）自动接入](roma/operation/ali_auto_access)**

## 步骤一、私有网络接入

\!**<span class="underline">此步骤需在 UCloud 控制台操作</span>**

从 UCloud 控制台进入罗马，点击“**私有网络接入**”。

![](/images/operation/私有网络接入.png)

进入“**私有网络接入**”页面，依次选择“**阿里云**” \> “**手动接入**” \>
“**地域**”，填入“**VPC名称**”、“**VPC
ID**”、“**子网网段**（注：子网网段对应于阿里云平台中的**交换机的目标网段**，非VPC的目标网段，一个VPC可能有多个）”（[点击我，前往阿里云平台查看VPC名称，VPC
ID及子网网段，请注意切换到相应地域](https://vpc.console.aliyun.com)），然后调整“**接入带宽**”，最后进行购买。

![](/images/operation/ali_manual_access/step11.png)

购买成功后，会跳转至“**已接入私有网络详情**”页面（如下图）。

![](/images/operation/ali_manual_access/step12.png)

请等待私有网络详情页出现**阿里云账号ID（罗马侧）**，**阿里云路由器ID（罗马侧）**，**阿里云路由器接口ID（罗马侧）**，如下图所示（若页面长时间不出现相关信息，请点击页面中的刷新按钮）。

![](/images/operation/ali_manual_access/step15.png)

请**不要关闭页面**，继续进行“**步骤二、创建阿里云高速通道**”的操作。

## 步骤二、创建阿里云高速通道

:\!:**<span class="underline">此步骤需在阿里云平台操作</span>**

进入“**高速通道**”\>“**专有网络连接**”\>“**路由器接口**”页面后，点击“**创建路由器接口**”按钮进行路由器接口的创建。

![](/images/operation/ali_manual_access/step1.png)

进入创建页面后，依次选择“**后付费**(付费方式)”\>“**跨账号**(账号类型)”\>“**VPC 连接**(连接
场景)”\>“**只创建接收端**(创建路由器场景)”\>“需要接入的 VPC **所在地域**”\>“**本端
VPC ID**”\>“**对端地域**”，然后点击“**立即购买**”。 说明:“需要接入的 VPC
所在地域”与“对端地域”**必须相同**(如下图中 **5** 与
**5’**所示)，否则无法接入，且会产生不必要的费用。

![](/images/operation/ali_manual_access/step2.png)

完成后，会在“**路由器接口**”页面中的表格中会产生一条路由器接口记录。

## 步骤三、添加对端路由器接口

:\!:**<span class="underline">此步骤需在阿里云平台操作</span>**

点击上一步中生成的路由器接口记录的“**添加**”，弹出“**添加对端路由器接口信息**”弹窗。

![](/images/operation/ali_manual_access/step3.png)

在弹窗中选择“**其他账号**”，依次填入“**对端账号 ID**”，“**对端路由器 ID**”和 “**对端路由器接口
ID**”（如何获取这些信息，请看下方备注），填写完毕后点击弹窗中的“**确定**”按钮。

![](/images/operation/ali_manual_access/step4.png)

**注**：对端账号ID、对端路由器ID、对端路由器接口ID 就是“ UCloud
控制台中**已接入私有网络详情**”页面中的“阿里云账号ID（罗马侧）”、“阿里云路由器ID（罗马侧）”、“阿里云路由器接口ID（罗马侧）”，如下图，若页面中仍未生成相关信息，请点击页面中的刷新按钮）

![](/images/operation/ali_manual_access/step15.png)

添加“**对端路由器接口信息**”后，表格中的路由器接口记录状态仍为“**未连接**”，请继续后面操作。

![](/images/operation/ali_manual_access/step5.png)

## 步骤四、保存高速通道等信息

:\!:**<span class="underline">此步骤需在 UCloud 控制台操作</span>**

将上面在阿里云平台生成的路由器接口记录中的“**路由器接口ID**”和“**路由器ID**”，以及“**阿里云安全设置**”页面（[点击我，前往阿里云平台查看账号ID](https://account.console.aliyun.com/#/secure)）

![](/images/operation/ali_manual_access/step13.png)

![](/images/operation/ali_auth/step1.png)

中的“**账号ID**”（注：必须为主账号ID）保存到“**步骤一、私有网络接入**”最后跳转到的“**已接入私有网络详情**”页面中。

![](/images/operation/ali_manual_access/step14.png)

保存后，请在**阿里云控制台**查看路由器接口表格中路由器接口状态是否已变为**已激活**（若未变成已激活，请点击页面中的**刷新**按钮）

![](/images/operation/ali_manual_access/step5.1.png)

路由器接口状态变成**已激活**后，请继续后面的操作。

## 步骤五、配置路由规则

:\!:**<span class="underline">此步骤需在阿里云平台操作</span>**

### 5.1 进入配置路由管理页面

点击上一步中，路由器接口记录的“**路由配置**”。

![](/images/operation/ali_manual_access/step6.png)

浏览器会打开专有网络(VPC)路由表页面，点击路由表的“**管理**”，进入路由表的详情页面。

![](/images/operation/ali_manual_access/step7.png)

### 5.2 查看已接入罗马的VPC的子网网段

在UCloud平台中查看已接入罗马的所有 VPC 的子网网段。 ![](/images/operation/私有网络列表.png)

注：若暂无 VPC 接入罗马，则不需要进行后面的5.3的操作，若有多个 VPC 或单个 VPC 有多个子网网段，请重复5.3的操作。

### 5.3 为子网网段添加路由条目

在路由表详情页面中点击“**添加路由条目**”按钮，弹出“**添加路由条目**”弹窗。

![](/images/operation/ali_manual_access/step8.png)

在弹窗中填入“**目标网段**”(某个已接入罗马的 VPC
占用的**子网网段**)，选择“**路由器接口(专有网络方向)**”作为下一跳类型，选择“**专有网络**”，然后点击“**确定**”，即可添加一条路由条目。

![](/images/operation/ali_manual_access/step9.png)

下图为创建了一条路由条目的示例。

![](/images/operation/ali_manual_access/step10.png)

**重复5.3**，直至为每个已接入罗马的 VPC 的子网网段都创建一条路由条目。

注:如果想连通已接入罗马的其他 VPC，那么需要为每个要连通的 VPC
分别添加一条路由条目，添加路由条目的方法与上面相同，即点击“**添加路由条目**”按钮，在弹窗中填写“**目标网段**”(此处根据
VPC 占用的网段不同，填入的内容不同)，“**下一跳类型**”与“**专有网络**”选项与上面相同。

## 步骤六、完成

以上即为将阿里云私有网络手动接入罗马的操作步骤，由于操作较为繁琐，**强烈建议使用
[VPC（阿里云）自动接入](/roma/operation/ali_auto_access)**。



# 授权（阿里云）

**<span class="underline">以下操作需在阿里云平台操作</span>**

### 查看主账号 ID

进入“**账号管理**”\>“**安全设置**”页面（[点击我，前往阿里云平台安全设置页面](https://account.console.aliyun.com/#/secure)）后，可查看“**账号
ID**”，此账号 ID 即为“**主账号 ID**”。

![](/images/operation/ali_auth/step1.png)

### 创建子账号

进入“**访问控制
RAM**”\>“**用户管理**”页面（[点击我，前往阿里云平台用户管理页面](https://ram.console.aliyun.com/#/user/list)），点击“**新建用户**”，弹出“**创建用户**”弹窗。

![](/images/operation/ali_auth/step2.png)

在弹窗中填入相关信息，点击进入“**确定**”按钮。

![](/images/operation/ali_auth/step3.png)

### 对子账号授权

在“**创建用户**”后，用户管理页面中的表格中会产生一条记录，点击该记录中的“**授权**”，弹出“**编辑个人授权策略**”弹窗。

![](/images/operation/ali_auth/step4.png)

在弹窗中找到“**AliyunVPCFullAccess**”和“**AliyunExpressConnectFullAccess**”授权策略并添加。

![](/images/operation/ali_auth/step5.png)

### 创建 AccessKey

进入刚创建的子账号“**详情页**”，找到“**用户 AccessKey**”部分，点击“**创建
AccessKey**”按钮，会提示您进行验证。

![](/images/operation/ali_auth/step6.png)

验证后，弹出“**新建用户 AccessKey**”弹窗，展开“**AccessKey 详情**”，即可看
到“**AccessKeyID**”和“**AccessKeySecret**”。

![](/images/operation/ali_auth/step7.png)

**<span class="underline">以下操作需在 UCloud 控制台操作</span>**

最后，将前面第一步找到的“**主账号 ID**” 和最后一步查看到的“**AccessKeyID**”和
“**AccessKeySecret**”信息填写至罗马。

注:罗马中可填写以上信息的地方有两处，一为私有网络接入处(未授权时可看到)，二为接入管理页面中的“**设置**”弹窗里。

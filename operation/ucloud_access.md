

# VPC（UCloud）接入

*即 UCloud 私有网络接入罗马*

## 步骤一、私有网络接入

\!**<span class="underline">此步骤需在 UCloud 控制台操作</span>**

从 UCloud 控制台进入罗马，点击“**私有网络接入**”。

![](/images/operation/私有网络接入.png)

进入“**私有网络接入**”页面，依次选择“**UCloud**” \> “**地域**” \>
需要接入的“**私有网络**”，最后进行购买即可。

![](/images/operation/ucloud_access/ucloud私有网络接入.png)

## 步骤二、手动添加路由条目

若当前没有**手动接入**到罗马的阿里云 VPC，则请忽略此步骤。

若当前已有**手动接入**到罗马的阿里云 VPC ，则需要在阿里云平台对该 VPC 进行路由配置（创建路由条目，注：只需对步骤一接入的 VPC
的子网网段进行创建），具体参见 [VPC（阿里云）手动接入
\#步骤五：配置路由规则](/roma/operation/ali_manual_access#%E6%9F%A5%E7%9C%8B%E5%B7%B2%E6%8E%A5%E5%85%A5%E7%BD%97%E9%A9%AC%E7%9A%84vpc%E7%9A%84%E5%AD%90%E7%BD%91%E7%BD%91%E6%AE%B5)

**注：由于手动接入阿里云 VPC 到罗马时，操作较为繁琐，且对其他 VPC 的接入及撤消流程都制造了额外的操作步骤，因此，接入阿里云 VPC
到罗马时，强烈建议使用 [](roma/operation/ali_auto_access)**

## 步骤三、选择开通线路

进入任意已接入的vpc，选择需要开通的线路，点击“**开通**”

![](/images/operation/开通.png)

调整带宽，支付后即可开通。

![](/images/operation/开通支付.png)

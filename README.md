TUIKit 是基于 IM SDK 的一款 UI 组件库，可通过 UI 组件快速实现聊天、会话、搜索、关系链、群组等功能。本文介绍如何快速集成 TUIKit 并实现核心功能。

## 关键概念

针对用户不同场景的诉求和体积要求，我们推出了多个版本的 UI 组件 ，您可以根据实际业务需求选择集成最适合的版本。
<table>
<tr>
<td rowspan="1" colSpan="1" >功能区分</td>

<td rowspan="1" colSpan="1" >精简版</td>

<td rowspan="1" colSpan="1" >标准版</td>

<td rowspan="1" colSpan="1" >完整版</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >登录&登出</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >用户资料与管理</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >消息列表</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >文本&自定义消息</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >图片&视频消息</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >历史消息</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >会话列表</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >未读消息计数</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >语音&文件消息</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >消息引用/撤回/转发</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >消息已读回执</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >群组功能</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >联系人列表</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >云端搜索</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >-</td>

<td rowspan="1" colSpan="1" >✓</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >体积大小</td>

<td rowspan="1" colSpan="1" >0.2 MB</td>

<td rowspan="1" colSpan="1" >0.51 MB</td>

<td rowspan="1" colSpan="1" >1.30 MB</td>
</tr>
</table>


## 前提条件
- HBuilderX 需要升级到最新版本

- TypeScript / JavaScript （**TUIKit 使用 ts 语言开发，支持在 js 或者 ts 项目中集成**）

- Vue3

- sass（sass-loader 版本 ≤ 10.1.1）

- node（12.13.0 ≤ node，推荐使用 Node.js 官方 LTS 版本 16.17.0）

- npm（版本请与 node 版本匹配）


## 创建项目 
1. 打开 HBuilderX，在菜单栏中选择 “文件 > 创建 > 项目”，创建一个名为 **chat-example** 的 uni-app 项目。

   ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/891bd2f7975f11f093df52540099c741.png)

2. 在终端输入`npm init -y`，创建`package.json`文件。

   ``` bash
   npm init -y
   ```

## 下载并导入组件

### 步骤1：安装依赖
1. 下载组件。


   

【Vue3】
``` bash
npm i tuikit-atomicx-uniapp-wx
```

【Vue2】
``` bash
npm i tuikit-atomicx-uniapp-wx@vue2
```

2. 拷贝源码。

【MacOS 端】
``` bash
mkdir -p ./TUIKit && cp -r node_modules/tuikit-atomicx-uniapp-wx/ ./TUIKit && cp node_modules/@trtc/call-engine-lite-wx/RTCCallEngine.wasm.br ./static
```

【Windows 端】
``` bash
xcopy node_modules\tuikit-atomicx-uniapp-wx .\TUIKit /i /e
xcopy node_modules\@trtc\call-engine-lite-wx\RTCCallEngine.wasm.br .\static
```

### 步骤2：获取 SDKAppID、userID 和 userSig

> **注意：**
> 

> 本文示例代码采用在 [即时通信 IM 控制台](https://console.cloud.tencent.com/im) 获取 UserSig 的方案，**该方法仅适合本地跑通功能调试**。 正确的 UserSig 签发方式请参见 [服务端生成 UserSig](https://cloud.tencent.com/document/product/269/32688)。
> 

- SDKAppID：在 [即时通信 IM 控制台 > 应用管理](https://console.cloud.tencent.com/im) 单击**创建新应用**，获取 SDKAppID。

   ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027380991/4a1fa0a7ae5e11f0b5345254005ef0f7.png)

- userID：单击 [即时通信 IM 控制台 > 消息服务 Chat > 账号管理](https://console.cloud.tencent.com/im/account-management)，切换至目标应用所在账号，您可以创建 2～3 个账号用于体验单聊、群聊的功能。

   ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027380991/4a1f2f75ae5e11f09b75525400bf7822.png)

- userSig：单击 [即时通信 IM 控制台 > 开发工具 > UserSig生成校验](https://console.cloud.tencent.com/im/tool-usersig)，切换至目标应用所在账号，填写创建的 userID，即可生成 userSig。

   ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027380991/4a247af9ae5e11f0b5345254005ef0f7.png)


## 运行和测试
![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/85f89e3d8c8411f0814e525400bf7822.png)


#### 1. 开通服务

在使用腾讯云提供的音视频服务前，您需要前往控制台，为应用开通音视频服务。具体步骤请参见 [开通服务。](https://write.woa.com/document/139743928960860160)

#### 2. 配置微信开放平台
- 开通企业类小程序


   小程序推拉流标签不支持个人小程序，只支持企业类小程序。需要在 [注册](https://developers.weixin.qq.com/community/business/doc/000200772f81508894e94ec965180d) 时填写主体类型为企业，如下图所示：

   ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/bea8943c8efd11f0bd05525400454e06.jpeg)

- 在小程序控制台开启实时音视频接口

  - 小程序推拉流标签使用权限暂时只开放给有限类目，[具体支持类目参见该地址](https://developers.weixin.qq.com/miniprogram/dev/component/live-pusher.html#%E7%94%B3%E8%AF%B7%E5%BC%80%E9%80%9A)。

  - 符合类目要求的小程序，需要在 [微信公众平台](https://mp.weixin.qq.com/) > **开发 **> **开发管理 **>** 接口设置**中自助开通该组件权限。

      ![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/be9ca9da8efd11f0818a52540099c741.png)


#### 3. 在小程序控制台配置域名

在 [微信公众平台](https://mp.weixin.qq.com/) > **开发** > **开发管理 **> **开发设置 **> **服务器域名**中设置 **request 合法域名**和** socket 合法域名**。

![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/bebb21638efd11f0818a52540099c741.png)

- 将以下域名添加到 socket 合法域名：

<table>
<tr>
<td rowspan="1" colSpan="1" >域名</td>

<td rowspan="1" colSpan="1" >说明</td>

<td rowspan="1" colSpan="1" >是否必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`wss://${SDKAppID}w4c.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >v3.4.6起，SDK 支持独立域名，可更好地保障服务稳定性。<br>例如您的 SDKAppID 是 1400xxxxxx，则独立域名为： `wss://1400xxxxxxw4c.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`wss://wss.im.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`wss://wss.tim.qq.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`wss://wssv6.im.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>
</table>

- 将以下域名添加到 request 合法域名：

<table>
<tr>
<td rowspan="1" colSpan="1" >域名</td>

<td rowspan="1" colSpan="1" >说明</td>

<td rowspan="1" colSpan="1" >是否必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://web.sdk.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://boce-cdn.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://api.im.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://events.im.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://webim.tim.qq.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://wss.im.qcloud.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://wss.tim.qq.com`</td>

<td rowspan="1" colSpan="1" >Web IM 业务域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>
</table>

- 将以下域名添加到 uploadFile 合法域名：

<table>
<tr>
<td rowspan="1" colSpan="1" >域名</td>

<td rowspan="1" colSpan="1" >说明</td>

<td rowspan="1" colSpan="1" >是否必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://${SDKAppID}-cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >从 2024年9月10日起，新增应用默认分配 COS 独立域名。<br>例如您的 SDKAppID 是 1400xxxxxx，则 COS 独立域名为：`https://1400xxxxxx-cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >文件上传域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cn.imrich.qcloud.com`</td>

<td rowspan="1" colSpan="1" >文件上传域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-shanghai.myqcloud.com`</td>

<td rowspan="1" colSpan="1" >文件上传域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-shanghai.tencentcos.cn`</td>

<td rowspan="1" colSpan="1" >文件上传域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-guangzhou.myqcloud.com`</td>

<td rowspan="1" colSpan="1" >文件上传域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>
</table>

- 将以下域名添加到 downloadFile 合法域名：

<table>
<tr>
<td rowspan="1" colSpan="1" >域名</td>

<td rowspan="1" colSpan="1" >说明</td>

<td rowspan="1" colSpan="1" >是否必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://${SDKAppID}-cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >从 2024年9月10日起，新增应用默认分配 COS 独立域名。<br>例如您的 SDKAppID 是 1400xxxxxx，则 COS 独立域名为：`https://1400xxxxxx-cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cn.rich.my-imcloud.com`</td>

<td rowspan="1" colSpan="1" >文件下载域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cn.imrich.qcloud.com`</td>

<td rowspan="1" colSpan="1" >文件下载域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-shanghai.myqcloud.com`</td>

<td rowspan="1" colSpan="1" >文件下载域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-shanghai.tencentcos.cn`</td>

<td rowspan="1" colSpan="1" >文件下载域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>

<tr>
<td rowspan="1" colSpan="1" >`https://cos.ap-guangzhou.myqcloud.com`</td>

<td rowspan="1" colSpan="1" >文件下载域名</td>

<td rowspan="1" colSpan="1" >必须</td>
</tr>
</table>


## 常见问题

### 如何移除音视频通话功能

移除 `static/RTCCallEngine.wasm.br` 文件。



【移除通话功能】

移除 TUIKit/index.ts 中的模块导出

![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/f0b448709ce411f0a90152540099c741.png)


【移除通话按钮】

移除 TUIKit/components/MessageInput/MessageInput.vue 中的通话按钮

![](https://write-document-release-1258344699.cos.ap-guangzhou.tencentcos.cn/100027131298/05bbb87b9ce511f09936525400e889b2.png)


【移除配置的页面路由】

移除在 pages.json 中为音视频通话添加的全局页面监听配置。


【选项一】
``` bash
  // {
	//    "path": "TUIKit/components/CallView/CallView",
	//	  "style": {
	//		  "navigationBarTitleText": "uni-app"
	//	  }
	// }

```

### Debug 脚本的作用

出于体积和安全双重因素考虑，请在发布前删除项目目录下 `/TUIKit/debug` 文件夹。在开发阶段为了方便开发，项目提供生成本地 UserSig 的脚本文件存放于`TUIKit/debug`文件夹中，但这并不安全，该方法中 SECRETKEY 很容易被反编译逆向破解，一旦您的密钥泄露，攻击者就可以盗用您的腾讯云流量，因此**该方法仅适合本地跑通 Demo 和功能调试**。因此，请在项目发布前删除 Debug 脚本，使用后台生成 UserSig，具体原因和操作步骤请参考文档：[生成 UserSig](https://write.woa.com/document/107052240244191232)。

## 联系我们

如遇任何问题，可联系 [官网售后](https://cloud.tencent.com/act/event/connect-service#/) 反馈，享有专业工程师的支持，解决您的难题。
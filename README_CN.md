<p align="center">
  <img src="Assets/Img/Logo.png" alt="DMA Engine" width="160"/>
</p>

<h1 align="center">DMA Engine</h1>

<p align="center">
  <strong>免费开源的多游戏 DMA 透视引擎</strong>
</p>

<p align="center">
  <a href="https://github.com/Skeelloo/releases/latest"><img src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD-%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC-0d1117?style=for-the-badge&logo=windows&logoColor=white" alt="下载"/></a>
  &nbsp;
  <a href="https://t.me/DMA_HUB"><img src="https://img.shields.io/badge/Telegram-%E9%A2%91%E9%81%93-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"/></a>
  &nbsp;
  <a href="https://github.com/Skeelloo"><img src="https://img.shields.io/badge/GitHub-%E4%BB%93%E5%BA%93-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/></a>
</p>

<p align="center">
  <a href="./README.md">English</a>
  &nbsp;&middot;&nbsp;
  <a href="./README_CN.md">中文</a>
</p>

<br/>

---

<br/>

## 关于

DMA Engine 是一款基于 FPGA DMA 硬件的独立透视覆盖工具。它以单个可移植可执行文件的形式发布 -- 无需安装、无需 .NET SDK、无需编译工具。解压即可运行。

应用程序提供简洁的游戏中心界面。选择你的游戏后，引擎会自动完成 DMA 初始化、进程检测和附加操作。

<br/>

## 支持的游戏

<table align="center">
  <thead>
    <tr>
      <th align="left">游戏</th>
      <th align="center">状态</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>暗区突围：无限</td>
      <td align="center"><img src="https://img.shields.io/badge/%E5%AE%8C%E5%85%A8%E6%94%AF%E6%8C%81-2ea043?style=flat-square" alt="支持"/></td>
    </tr>
    <tr>
      <td>反恐精英2</td>
      <td align="center"><img src="https://img.shields.io/badge/%E5%AE%8C%E5%85%A8%E6%94%AF%E6%8C%81-2ea043?style=flat-square" alt="支持"/></td>
    </tr>
    <tr>
      <td>三角洲行动</td>
      <td align="center"><img src="https://img.shields.io/badge/%E5%8D%B3%E5%B0%86%E6%8E%A8%E5%87%BA-e3b341?style=flat-square" alt="即将推出"/></td>
    </tr>
  </tbody>
</table>

<p align="center"><em>更多游戏将陆续添加。</em></p>

<br/>

## 功能特性

| 功能 | 说明 |
|:---|:---|
| **自动配置** | DMA 初始化、游戏检测和进程附加全部自动完成，首次启动无需手动配置。 |
| **ESP 透视** | 支持玩家方框、名称、距离、血量以及骨骼渲染（视游戏而定）。 |
| **网页雷达** | 内置暗区突围网页雷达，可通过局域网内任何设备访问。 |
| **输入支持** | Makcu 设备集成，支持硬件级输入转发。 |
| **UPnP 端口映射** | 自动端口转发，用于雷达和网络功能。 |
| **独立游戏配置** | 每个游戏的设置保存在 `%AppData%\DMAEngine` 中，跨会话持久保存。 |
| **轻量级** | 单文件可执行程序，资源占用极低。完全自包含，无需安装 .NET 运行时。 |

<br/>

## 系统要求

| 要求 | 详情 |
|:---|:---|
| **操作系统** | Windows 10 或 Windows 11（64 位） |
| **硬件** | 基于 FPGA 的 DMA 设备（Squirrel、CaptainDMA 等） |
| **固件** | 设备必须已刷入可用固件 |
| **显卡** | 任何支持 DirectX 11 的 GPU |

> 无需安装 .NET 运行时。发布版本完全自包含。

<br/>

## 快速开始

```
1. 从 Releases 页面下载最新版本
2. 将 .zip 解压到任意文件夹
3. 运行 DMAEngine.exe
4. 从游戏中心选择你的游戏
5. 引擎将自动初始化 DMA 设备并完成附加
```

附加完成后，透视覆盖层将自动激活，ESP 功能根据游戏配置启用。

<br/>

## 配置文件

所有设置存储在：

```
%AppData%\DMAEngine\<游戏名称>\config.json
```

通过应用内设置面板修改 ESP 开关、颜色、距离和按键绑定。更改会自动保存。

<br/>

## 文件结构

```
DMA Engine/
  |-- DMAEngine.exe          主程序
  |-- Assets/                字体、图标、雷达资源
  |-- vmm.dll                VMM 库
  |-- leechcore.dll          LeechCore 库
  |-- FTD3XX.dll             FTDI 驱动
  |-- (其他本机 DLL 文件)
```

> 请勿删除文件夹中的任何 `.dll` 文件，它们是 DMA 通信和渲染所必需的。

<br/>

## 常见问题

<details>
<summary><strong>"找不到 DMA 设备"</strong></summary>
<br/>
确保 FPGA 设备已连接、通电并刷入可用固件。在设备管理器中检查 FTDI 设备。
</details>

<details>
<summary><strong>透视覆盖层未显示</strong></summary>
<br/>
以管理员身份运行 <code>DMAEngine.exe</code>。部分带有反作弊的游戏可能需要提升权限才能渲染覆盖层。
</details>

<details>
<summary><strong>OBS / Discord 无法捕获覆盖层</strong></summary>
<br/>
确保 OBS 或 Discord 与 DMA Engine 以相同权限级别运行。在游戏可执行文件上禁用"全屏优化"。
</details>

<details>
<summary><strong>杀毒软件误报</strong></summary>
<br/>
这是由单文件发布和 DMA 库签名引起的误报。请将文件夹添加到杀毒软件的排除列表中。
</details>

<br/>

## 致谢

| | |
|:---|:---|
| **Mambo** | [MamboDMA](https://github.com/Mambo-Noob/MamboDMA) 原作者 -- 本项目基于其工作分叉而来 |
| **Lone** | [VmmSharpEx](https://github.com/LonePointer/VmmSharpEx) |
| **Marazm** | 地图和雷达资源 |

<br/>

## 免责声明

> 本软件仅供教育目的使用。作者不对其使用方式承担任何责任。使用风险自负，请遵守相关服务条款。

<br/>

---

<p align="center">
  <a href="https://github.com/Skeelloo/releases/latest"><img src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD-%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC-0d1117?style=for-the-badge&logo=windows&logoColor=white" alt="下载"/></a>
  &nbsp;
  <a href="https://t.me/DMA_HUB"><img src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"/></a>
  &nbsp;
  <a href="https://github.com/Skeelloo"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/></a>
</p>

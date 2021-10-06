---
layout: 邮政
title: 网络生活
description: 健康网站的基本指标
hero: 图像/管理员/BHaoqqR73jDWe6FL2kfw.png
authors:
  - 菲利普沃尔顿
date: '2020-04-30'
updated: '2020-07-21'
tags:
  - 指标
  - 表现
  - 网络生活
---

优化用户体验质量是网络上任何网站取得长期成功的关键。无论您是企业主、营销人员还是开发人员，Web Vitals 都可以帮助您量化网站体验并确定改进机会。

## 概述

Web Vitals 是 Google 的一项举措，旨在为质量信号提供统一指导，这些信号对于在网络上提供出色的用户体验至关重要。

多年来，Google 提供了许多工具来衡量和报告性能。一些开发人员是使用这些工具的专家，而另一些开发人员则发现工具和指标的丰富程度难以跟上。

网站所有者不必成为性能专家才能了解他们为用户提供的体验质量。 Web Vitals 计划旨在简化环境，并帮助站点专注于最重要的指标，即**Core Web Vitals** 。

## 核心网络生命体征

Core Web Vitals 是适用于所有网页的 Web Vitals 子集，应由所有网站所有者衡量，并将在所有 Google 工具中显示。每个 Core Web Vitals 都代表了用户体验的一个独特方面，[在该领域](/user-centric-performance-metrics/#how-metrics-are-measured)是可衡量的，并反映了以[用户为中心](/user-centric-performance-metrics/#how-metrics-are-measured)的关键结果的真实体验。

构成 Core Web Vitals 的指标会随着时间的推移[而发展。](#evolving-web-vitals) 2020 年的当前设置侧重于用户体验的三个方面——*加载*、*交互性*和*视觉稳定性*——并包括以下指标（及其各自的阈值）：

<div class="w-stack w-stack--center w-stack--md">
<img src="lcp_ux.svg" width="400px" height="350px" alt="最大内容绘制阈值建议"><img src="fid_ux.svg" width="400px" height="350px" alt="首次输入延迟阈值建议"><img src="cls_ux.svg" width="400px" height="350px" alt="累积布局偏移阈值建议">
</div>

- **[Largest Contentful Paint (LCP)](/lcp/)** ：测量*加载*性能。为了提供良好的用户体验，LCP 应在页面首次开始加载**后的 2.5 秒内发生。**
- **[首次输入延迟 (FID)](/fid/)** ：测量*交互性*。为了提供良好的用户体验，页面的 FID 应小于**100 毫秒**。
- **[累积布局偏移 (CLS)](/cls/)** ：测量*视觉稳定性*。为了提供良好的用户体验，页面应保持小于**0.1 的 CLS。**

对于上述每个指标，为了确保您达到为大多数用户推荐的目标，一个很好的衡量阈值是**页面加载的第 75 个百分点**，跨移动和桌面设备进行细分。

评估 Core Web Vitals 合规性的工具应考虑页面通过，如果它满足上述所有三个指标的 75% 的建议目标。

{% Aside %} 要了解有关这些建议背后的研究和方法的更多信息，请参阅：[定义 Core Web Vitals 指标阈值](/defining-core-web-vitals-thresholds/){% endAside %}

### 衡量和报告 Core Web Vitals 的工具

Google 认为 Core Web Vitals 对所有网络体验都至关重要。因此，它致力于[在其所有流行工具中](/vitals-tools/)显示这些指标。以下部分详细介绍了哪些工具支持 Core Web Vitals。

#### 测量核心 Web 生命值的现场工具

[Chrome 用户体验报告](https://developers.google.com/web/tools/chrome-user-experience-report)为每个 Core Web Vital 收集匿名的真实用户测量数据。这些数据使网站所有者能够快速评估其性能，而无需他们在其页面上手动检测分析，并为[PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)和 Search Console 的[Core Web Vitals 报告等工具提供支持](https://support.google.com/webmasters/answer/9205520)。

<div class="w-table-wrapper">
  <table>
    <tr>
      <td> </td>
      <td>LCP</td>
      <td>外国投资署</td>
      <td>CLS</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/web/tools/chrome-user-experience-report">Chrome 用户体验报告</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/speed/pagespeed/insights/">PageSpeed 洞察力</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://support.google.com/webmasters/answer/9205520">Search Console（核心网络生命力报告）</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
  </table>
</div>

{% Aside %} 有关如何使用这些工具以及哪种工具适合您的用例的指导，请参阅：[开始测量 Web Vitals](/vitals-measurement-getting-started/) {% endAside %}

Chrome 用户体验报告提供的数据提供了一种评估网站性能的快速方法，但它没有提供详细的、按页面查看的遥测数据，而这通常是准确诊断、监控和快速对回归做出反应所必需的。因此，我们强烈建议网站设置自己的真实用户监控。

#### 在 JavaScript 中测量核心 Web Vitals

每个 Core Web Vitals 都可以使用标准 Web API 在 JavaScript 中进行测量。

衡量所有 Core Web Vitals 的最简单方法是使用[web-vitals](https://github.com/GoogleChrome/web-vitals) JavaScript 库，这是一个围绕底层 Web API 的小型、生产就绪包装器，它以准确匹配所有指标报告方式的方式衡量每个指标。上面列出的谷歌工具。

使用[web-vitals](https://github.com/GoogleChrome/web-vitals)库，衡量每个指标就像调用单个函数一样简单（有关完整[用法](https://github.com/GoogleChrome/web-vitals#usage)和[API](https://github.com/GoogleChrome/web-vitals#api)详细信息，请参阅文档）：

```js
import {getCLS, getFID, getLCP} from 'web-vitals';

function sendToAnalytics(metric) {
  const body = JSON.stringify(metric);
  // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
  (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
      fetch('/analytics', {body, method: 'POST', keepalive: true});
}

getCLS(sendToAnalytics);
getFID(sendToAnalytics);
getLCP(sendToAnalytics);
```

一旦您将站点配置为使用[web-vitals](https://github.com/GoogleChrome/web-vitals)库来衡量您的 Core Web Vitals 数据并将其发送到分析端点，下一步就是汇总和报告该数据，以查看您的页面是否满足建议的阈值至少 75% 的页面访问。

虽然一些分析提供商内置了对 Core Web Vitals 指标的支持，但即使是那些不应该包含基本自定义指标功能的分析提供商，这些功能允许您在他们的工具中衡量 Core Web Vitals。

其中一个例子是[Web Vitals Report](https://github.com/GoogleChromeLabs/web-vitals-report) ，它允许网站所有者使用 Google Analytics 来衡量他们的核心 Web Vitals。有关使用其他分析工具测量核心 Web 指标的指南，请参阅[在现场测量 Web 指标的最佳实践](/vitals-field-measurement-best-practices/)。

[您还可以使用 Web Vitals Chrome 扩展程序](https://github.com/GoogleChrome/web-vitals-extension)报告每个 Core Web Vitals，而无需编写任何代码。此扩展使用[web-vitals](https://github.com/GoogleChrome/web-vitals)库来衡量这些指标中的每一个，并在用户浏览网络时将它们显示给用户。

此扩展程序有助于了解您自己的网站、竞争对手的网站和整个网络的性能。

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>外国投资署</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals">网络生活</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals-extension">Web Vitals 扩展</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

或者，更喜欢直接通过底层 Web API 衡量这些指标的开发人员可以参考这些指标指南了解实现细节：

- [在 JavaScript 中测量 LCP](/lcp/#measure-lcp-in-javascript)
- [在 JavaScript 中测量 FID](/fid/#measure-fid-in-javascript)
- [在 JavaScript 中测量 CLS](/cls/#measure-cls-in-javascript)

{% Aside %} 有关如何使用流行的分析服务（或您自己的内部分析工具）衡量这些指标的更多指导，请参阅：[在该领域衡量 Web Vitals 的最佳实践](/vitals-field-measurement-best-practices/){% endAside %}

#### 测量核心 Web 生命值的实验室工具

虽然所有的 Core Web Vitals 首先都是现场指标，但其中许多也可以在实验室中进行测量。

实验室测量是在开发过程中测试功能性能的最佳方式——在功能发布给用户之前。这也是在性能回归发生之前捕捉它们的最佳方式。

以下工具可用于在实验室环境中测量 Core Web Vitals：

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>外国投资署</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://developers.google.com/web/tools/chrome-devtools">Chrome 开发者工具</a></td>
        <td>✔</td>
        <td>✘（使用<a href="/tbt/">TBT</a>代替）</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://developers.google.com/web/tools/lighthouse">灯塔</a></td>
        <td>✔</td>
        <td>✘（使用<a href="/tbt/">TBT</a>代替）</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

{% Aside %} 像 Lighthouse 这样在没有用户的情况下在模拟环境中加载页面的工具无法测量 FID（没有用户输入）。但是，总阻塞时间 (TBT) 指标是实验室可测量的，并且是 FID 的绝佳代表。在实验室中改进 TBT 的性能优化应该改进现场的 FID（请参阅下面的性能建议）。 {% endAside %}

虽然实验室测量是提供出色体验的重要组成部分，但它不能替代现场测量。

根据用户的设备功能、他们的网络状况、设备上可能正在运行的其他进程以及它们与页面的交互方式，站点的性能可能会有很大差异。事实上，每个 Core Web Vitals 指标的得分都会受到用户交互的影响。只有实地测量才能准确捕捉全貌。

### 提高分数的建议

一旦您测量了 Core Web Vitals 并确定了需要改进的领域，下一步就是优化。以下指南提供了有关如何针对每个 Core Web Vitals 优化页面的具体建议：

- [优化 LCP](/optimize-lcp/)
- [优化 FID](/optimize-fid/)
- [优化 CLS](/optimize-cls/)

## 其他网络重要信息

虽然 Core Web Vitals 是理解和提供出色用户体验的关键指标，但还有其他重要指标。

这些其他 Web Vitals 通常用作 Core Web Vitals 的代理或补充指标，以帮助获取大部分体验或帮助诊断特定问题。

例如，第[一个字节时间 (TTFB)](/time-to-first-byte/)和[首次内容绘制 (FCP) 指标](/fcp/)*都是加载*体验的重要方面，并且在诊断 LCP 问题时都很有用（分别是缓慢的[服务器响应时间](/overloaded-server/)或[渲染阻塞资源](/render-blocking-resources/)） .

同样，[总阻塞时间 (TBT)](/tbt/)和[交互时间 (TTI)](/tti/)等指标是实验室指标，对于捕捉和诊断将影响 FID 的*潜在交互问题至关重要。*然而，它们不是 Core Web Vitals 集的一部分，因为它们不可现场测量，也不反映以[用户为中心的](/user-centric-performance-metrics/#how-metrics-are-measured)结果。

## 不断发展的 Web Vitals

Web Vitals 和 Core Web Vitals 代表了当今开发人员用来衡量整个网络体验质量的最佳可用信号，但这些信号并不完美，应该期待未来的改进或添加。

**Core Web Vitals**与所有网页相关，并且在相关的 Google 工具中都有特色。这些指标的变化将产生广泛的影响；因此，开发人员应该期望 Core Web Vitals 的定义和阈值是稳定的，并且更新会提前通知和可预测的年度节奏。

其他 Web Vitals 通常是特定于上下文或工具的，并且可能比 Core Web Vitals 更具实验性。因此，它们的定义和阈值可能会更频繁地改变。

对于所有 Web Vitals，更改将清楚地记录在此公共[CHANGELOG 中](http://bit.ly/chrome-speed-metrics-changelog)。

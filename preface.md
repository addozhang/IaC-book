

Ten years ago, a CIO at a global bank scoffed when I suggested they look into private cloud technologies and infrastructure automation tooling: “That kind of thing might be fine for startups, but we’re too large and our requirements are too complex.” Even a few years ago, many enterprises considered using public clouds to be out of the question.
These days cloud technology is pervasive. Even the largest, most hidebound organiza‐ tions are rapidly adopting a “cloud-first” strategy. Those organizations that find themselves unable to consider public clouds are adopting dynamically provisioned infrastructure platforms in their data centers.1 The capabilities that these platforms offer are evolving and improving so quickly that it’s hard to ignore them without risking obsolescence.
Cloud and automation technologies remove barriers to making changes to produc‐ tion systems, and this creates new challenges. While most organizations want to speed up their pace of change, they can’t afford to ignore risks and the need for gov‐ ernance. Traditional processes and techniques for changing infrastructure safely are not designed to cope with a rapid pace of change. These ways of working tend to throttle the benefits of modern, Cloud Age technologies—slowing work down and harming stability.2


In Chapter 1 I use the terms “Iron Age” and “Cloud Age” (“From the Iron Age to the Cloud Age” on page 2) to describe the different philosophies that apply to managing physical infrastructure, where mistakes are slow and costly to correct, and managing virtual infrastructure, where mistakes can be quickly detected and fixed.
Infrastructure as Code tools create the opportunity to work in ways that help you to deliver changes more frequently, quickly, and reliably, improving the overall quality of your systems. But the benefits don’t come from the tools themselves. They come from how you use them. The trick is to leverage the technology to embed quality, reliability, and compliance into the process of making changes.

## Why I Wrote This Book

I wrote the first edition of this book because I didn’t see a cohesive collection of guid‐ ance on how to manage Infrastructure as Code. There was plenty of advice scattered across blog posts, conference talks, and documentation for products and projects. But a practitioner needed to sift through everything and piece a strategy together for themselves, and most people simply didn’t have time.
The experience of writing the first edition was amazing. It gave me the opportunity to travel and to talk with people around the world about their own experiences. These conversations gave me new insights and exposed me to new challenges. I learned that the value of writing a book, speaking at conferences, and consulting with clients is that it fosters conversations. As an industry, we are still gathering, sharing, and evolv‐ ing our ideas for managing Infrastructure as Code.

## What’s New and Different in This Edition

Things have moved along since the first edition came out in June 2016. That edition was subtitled “Managing Servers in the Cloud,” which reflected the fact that most infrastructure automation until that point had been focused on configuring servers. Since then, containers and clusters have become a much bigger deal, and the infra‐ structure action has moved to managing collections of infrastructure resources provi‐ sioned from cloud platforms—what I call stacks in this book.

As a result, this edition involves more coverage of building stacks, which is the remit of tools like CloudFormation and Terraform. The view I’ve taken is that we use stack management tools to assemble collections of infrastructure that provide application runtime environments. Those runtime environments may include servers, clusters, and serverless execution environments.

I’ve changed quite a bit based on what I’ve learned about the evolving challenges and needs of teams building infrastructure. As I’ve already touched on in this preface, I see making it safe and easy to change infrastructure as the key benefit of Infrastructure as Code. I believe people underestimate the importance of this by thinking that infrastructure is something you build and forget.
But too many teams I meet struggle to meet the needs of their organizations; they are not able to expand and scale quickly enough, support the pace of software delivery, or provide the reliability and security expected. And when we dig into the details of their challenges, it’s that they are overwhelmed by the need to update, fix, and improve their systems. So I’ve doubled down on this as the core theme of this book.
This edition introduces three core practices for using Infrastructure as Code to make changes safely and easily:

```
Define everything as code
This one is obvious from the name, and creates repeatability and consistency.
Continuously test and deliver all work in progress
Each change enhances safety. It also makes it possible to move faster and with more confidence.
Build small, simple pieces that you can change independently
These are easier and safer to change than larger pieces.
```

These three practices are mutually reinforcing. Code is easy to track, version, and deliver across the stages of a change management process. It’s easier to continuously test smaller pieces. Continuously testing each piece on its own forces you to keep a loosely coupled design.
These practices and the details of how to apply them are familiar from the world of software development. I drew on Agile software engineering and delivery practices for the first edition of the book. For this edition, I’ve also drawn on rules and practi‐ ces for effective design.
In the past few years, I’ve seen teams struggle with larger and more complicated infrastructure systems, and I’ve seen the benefits of applying lessons learned in soft‐ ware design patterns and principles, so I’ve included several chapters in this book on how to do this.
I’ve also seen that organizing and working with infrastructure code is difficult for many teams, so I’ve addressed various pain points. I describe how to keep codebases well organized, how to provide development and test instances for infrastructure, and how to manage the collaboration of multiple people, including those responsible for governance.

## What’s Next

I don’t believe we’ve matured as an industry in how we manage infrastructure. I’m hoping this book gives a decent view of what teams are finding effective these days. And a bit of aspiration of what we can do better.
I fully expect that in another five years the toolchains and approaches will evolve. We could see more general-purpose languages used to build libraries, and we could be dynamically generating infrastructure rather than defining the static details of envi‐ ronments at a low level. We certainly need to get better at managing changes to live infrastructure. Most teams I know are scared when applying code to live infrastruc‐ ture. (One team referred to Terraform as “Terrorform,” but users of other tools all feel this way.)

## 本书的内容

本书的论题是，探索使用工具实现基础设施的不同方法，这些基础设施可以帮助我们提高所我们提供的服务质量。我们的目标是利用交付的速度和频率来提高我们所交付的可靠性和质量。
所以本书的重点不在于具体的工具，而在于如何使用这些工具。
虽然我提到了配置服务器和配置堆栈等特定功能的工具示例，但你不会找到如何使用特定工具或云平台的细节。你会发现与任何你使用的工具和平台所契合的模式、实践和技术。
你不会找到现实中的工具或云的代码例子。在这个领域，工具变化太快，无法保持代码例子的准确性，但本书中的建议应该更缓慢地老化，并且适用于各种工具。相反，我为虚构的工具写了一些伪代码例子来说明概念。有关示例项目和代码的参考资料，请参见本书的配套网站（https://infrastructure-as-code.com）。
本书不会指导你如何使用 Linux 操作系统、Kubernetes 集群配置或网络路由。本书的范围包括提供基础设施资源来创建这些东西的方法，以及如何使用代码来交付它们。我分享了不同的集群拓扑模式和以代码定义和管理集群的方法。我描述了使用代码提供、配置和更改服务器实例的模式。
你应该用具体的操作系统、集群技术和云平台的资源来补充本书中的实践。同样，本书解释了使用这些工具和技术的方法，这些方法与特定工具无关。

本书在可操作性方面的内容也不多，比如监控和可观察性、日志聚合、身份管理，以及在云环境中支持服务所需的其他问题。书中的内容应该可以帮助你以代码的形式管理这些服务所需的基础设施，但具体服务的细节，你可以在更具体的资源中找到。

## 基础设施即代码的前生

基础设施即代码工的具和实践在这个词出现之前就已经出现了。系统管理员从一开始就使用脚本来帮助他们管理系统。Mark Burgess 在 1993 年创建了开创性的 CFEngine（https://cfengine.com）系统。我在 2000 年初从 Infrastructures.org（http://www.infrastructures.org）的网站上第一次了解到使用代码来完全自动化配置和更新服务器的做法。
基础架构即代码伴随着 DevOps 运动而发展。Andrew Clay-Shafer 和 Patrick Debois 在 2008 敏捷大会上的演讲引发了 DevOps 运动（https://oreil.ly/ermR3）。我发现“基础设施即代码”这个词的第一次使用是来自 Clay-Shafer 在 2009 年 Velocity 会议上发表的一篇名为“敏捷的基础设施”的演讲（https://oreil.ly/qnJKX），以及 John Willis 写的一篇总结该演讲的文章（https://oreil.ly/2F6y_）。Chef 的联合创始人 Adam Jacob 和 Puppet 的创始人 Luke Kanies 也在这个时候使用这个词。

## 本书适合谁

本书是为那些参与提供和使用基础设施来交付和运行软件的人准备的。你可能有系统和基础设施的背景，或者有软件开发和交付的背景。你的角色可能是工程、测试、架构或管理。我假设你或多或少接触了云或虚拟化基础设施和使用代码自动化基础设施的工具。
刚接触基础设施即代码的读者应该会发现这本书是一个很好的主题介绍，尽管你熟悉基础设施云平台的工作方式，以及至少一种基础设施编码工具的基础知识，你仍会得到很大的收获。
对于那些有更多使用这些工具经验的人来说，应该会发现熟悉的、新的概念与方法的组合。这些内容应创造一种通用的语言，并以有经验的从业人员和团队认为有用的方式阐明挑战和解决方案。

## Principles, Practices, and Patterns

I use the terms principles, practices, and patterns (and antipatterns) to describe essen‐ tial concepts. Here are the ways I use each of these terms:

```
Principle
A principle is a rule that helps you to choose between potential solutions.
Practice
A practice is a way of implementing something. A given practice is not always the only way to do something, and may not even be the best way to do it for a particular situation. You should use principles to guide you in choosing the most appropriate practice for a given situation.
Pattern
A pattern is a potential solution to a problem. It’s very similar to a practice in that different patterns may be more effective in different contexts. Each pattern is described in a format that should help you to evaluate how relevant it is for your problem.
Antipattern
An antipattern is a potential solution that you should avoid in most situations. Usually, it’s either something that seems like a good idea or else it’s something that you fall into doing without realizing it.
```

```
Why I Don’t Use the Term “Best Practice”
Folks in our industry love to talk about “best practices.” The problem with this term is that it often leads people to think there is only one solution to a problem, no matter what the context.
I prefer to describe practices and patterns, and note when they are useful and what their limitations are. I do describe some of these as being more effective or more appropriate, but I try to be open to alternatives. For practices that I believe are less effective, I hope I explain why I think this.
```

## The ShopSpinner Examples

I use a fictional company called ShopSpinner to illustrate concepts throughout this book. ShopSpinner builds and runs online stores for its customers.
ShopSpinner runs on FCS, the Fictional Cloud Service, a public IaaS provider with services that include FSI (Fictional Server Images) and FKS (Fictional Kubernetes Service). It uses the Stackmaker tool—an analog of Terraform, CloudFormation, and Pulumi—to define and manage infrastructure on its cloud. It configures servers with the Servermaker tool, which is much like Ansible, Chef, or Puppet.
ShopSpinner’s infrastructure and system design may vary depending on the point I’m using it to make, as will the syntax of the code and command-line arguments for its fictional tools.

## Conventions Used in This Book

The following typographical conventions are used in this book:
Italic
Indicates new terms, URLs, email addresses, filenames, and file extensions.
Constant width
Used for program listings, as well as within paragraphs to refer to program ele‐ ments such as variable or function names, databases, data types, environment variables, statements, and keywords.
Constant width bold
Shows commands or other text that should be typed literally by the user.
Constant width italic
Shows text that should be replaced with user-supplied values or by values deter‐ mined by context.
 This element signifies a tip or suggestion.
This element signifies a general note.
This element indicates a warning or caution.
  


## ref

1 For example, many government and financial organizations in countries without a cloud presence are pre‐ vented by law from hosting data or transactions abroad.
2 The research published by DORA in the State of DevOps Report (https://oreil.ly/ysk9n) finds that heavyweight change-management processes correlate to poor performance on change failure rates and other measures of software delivery effectiveness.


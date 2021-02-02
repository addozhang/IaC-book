

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

## What This Book Is and Isn’t

The thesis of this book is that exploring different ways of using tools to implement infrastructure can help us to improve the quality of services we provide. We aim to use speed and frequency of delivery to improve the reliability and quality of what we deliver.
So the focus of this book is less on specific tools, and more on how to use them.
Although I mention examples of tools for particular functions like configuring servers and provisioning stacks, you won’t find details of how to use a particular tool or cloud platform. You will find patterns, practices, and techniques that should be relevant to whatever tools and platforms you use.
You won’t find code examples for real-world tools or clouds. Tools change too quickly in this field to keep code examples accurate, but the advice in this book should age more slowly, and be applicable across tools. Instead, I write pseudocode examples for fictional tools to illustrate concepts. See the book’s companion website (https://infrastructure-as-code.com) for references to example projects and code.
This book won’t guide you on how to use the Linux operating system, Kubernetes cluster configuration, or network routing. The scope of this book does include ways to provision infrastructure resources to create these things, and how to use code to deliver them. I share different cluster topology patterns and approaches for defining and managing clusters as code. I describe patterns for provisioning, configuring, and changing server instances using code.
You should supplement the practices in this book with resources on the specific oper‐ ating systems, clustering technologies, and cloud platforms. Again, this book explains approaches for using these tools and technologies that are relevant regardless of the particular tool.

This book is also light on operability topics like monitoring and observability, log aggregation, identity management, and other concerns that you need to support serv‐ ices in a cloud environment. What’s in here should help you to manage the infra‐ structure needed for these services as code, but the details of the specific services are, again, something you’ll find in more specific resources.

## Some History of Infrastructure as Code

Infrastructure as Code tools and practices emerged well before the term. Systems administrators have been using scripts to help them manage systems since the begin‐ ning. Mark Burgess created the pioneering CFEngine (https://cfengine.com) system in 1993. I first learned practices for using code to fully automate provisioning and updates of servers from the Infrastructures.org (http://www.infrastructures.org) web‐ site in the early 2000s.3
Infrastructure as Code has grown along with the DevOps movement. Andrew Clay- Shafer and Patrick Debois triggered the DevOps movement with a talk at the Agile 2008 conference (https://oreil.ly/ermR3). The first uses I’ve found for the term “Infra‐ structure as Code” are from a talk called “Agile Infrastructure” (https://oreil.ly/ qnJKX) that Clay-Shafer gave at the Velocity conference in 2009, and an article (https://oreil.ly/2F6y_) John Willis wrote summarizing the talk. Adam Jacob, who cofounded Chef, and Luke Kanies, founder of Puppet, were also using the phrase around this time.

## Who This Book Is For

This book is for people who are involved in providing and using infrastructure to deliver and run software. You may have a background in systems and infrastructure, or in software development and delivery. Your role may be engineering, testing, architecture, or management. I’m assuming you have some exposure to cloud or vir‐ tualized infrastructure and tools for automating infrastructure using code.
Readers new to Infrastructure as Code should find this book a good introduction to the topic, although you will get the most out of it if you are familiar with how infra‐ structure cloud platforms work, and the basics of at least one infrastructure coding tool.
Those who have more experience working with these tools should find a mixture of familiar and new concepts and approaches. The content should create a common lan‐ guage and articulate challenges and solutions in ways that experienced practitioners and teams find useful.

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



Table of Contents
 Preface. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . xv
Part I. Foundations
1. What Is Infrastructure as Code?. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 1
 From the Iron Age to the Cloud Age
Infrastructure as Code
Benefits of Infrastructure as Code
Use Infrastructure as Code to Optimize for Change
Objection: “We don’t make changes often enough to justify automating them”
Objection: “We should build first and automate later”
Objection: “We must choose between speed and quality” The Four Key Metrics
Three Core Practices for Infrastructure as Code
2 4 4 4
5 6 7 9 9
Core Practice: Define Everything as Code 10 Core Practice: Continuously Test and Deliver All Work in Progress 10 Core Practice: Build Small, Simple Pieces That You Can Change
Independently 11 Conclusion 11
2. Principles of Cloud Age Infrastructure. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 13
Principle: Assume Systems Are Unreliable 14 Principle: Make Everything Reproducible 14 Pitfall: Snowflake Systems 15 Principle: Create Disposable Things 16 Principle: Minimize Variation 17
v
 
   Configuration Drift 18 Principle: Ensure That You Can Repeat Any Process 20 Conclusion 21
3. Infrastructure Platforms. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
The Parts of an Infrastructure System 23 Infrastructure Platforms 25 Infrastructure Resources 27
Compute Resources 28 Storage Resources 29 Network Resources 31
Conclusion 33
4. Core Practice: Define Everything as Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 35
Why You Should Define Your Infrastructure as Code 35 What You Can Define as Code 36 Choose Tools with Externalized Configuration 36 Manage Your Code in a Version Control System 37 Infrastructure Coding Languages 38 Infrastructure Scripting 39 Declarative Infrastructure Languages 41 Programmable, Imperative Infrastructure Languages 43 Declarative Versus Imperative Languages for Infrastructure 44 Domain-Specific Infrastructure Languages 44 General-Purpose Languages Versus DSLs for Infrastructure 46 Implementation Principles for Defining Infrastructure as Code 46 Separate Declarative and Imperative Code 47 Treat Infrastructure Code Like Real Code 47 Conclusion 48
Part II. Working with Infrastructure Stacks
 vi
|
5.
Building Infrastructure Stacks as Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 51
What Is an Infrastructure Stack? 51 Stack Code 53 Stack Instance 53 Configuring Servers in a Stack 54 Low-Level Infrastructure Languages 54 High-Level Infrastructure Languages 55
Patterns and Antipatterns for Structuring Stacks 56 Antipattern: Monolithic Stack 56
Table of Contents
   
   Pattern: Application Group Stack 59 Pattern: Service Stack 60 Pattern: Micro Stack 62
Conclusion 63
6. Building Environments with Stacks. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 65
What Environments Are All About 65 Delivery Environments 66 Multiple Production Environments 66 Environments, Consistency, and Configuration 67
Patterns for Building Environments 68 Antipattern: Multiple-Environment Stack 68 Antipattern: Copy-Paste Environments 70 Pattern: Reusable Stack 72
Building Environments with Multiple Stacks 74 Conclusion 75
7. Configuring Stack Instances. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 77
Using Stack Parameters to Create Unique Identifiers Example Stack Parameters
Patterns for Configuring Stacks
Antipattern: Manual Stack Parameters Pattern: Stack Environment Variables Pattern: Scripted Parameters
Pattern: Stack Configuration Files Pattern: Wrapper Stack
Pattern: Pipeline Stack Parameters
Pattern: Stack Parameter Registry Configuration Registry
Implementing a Configuration Registry
Single or Multiple Configuration Registries Handling Secrets as Parameters
Encrypting Secrets Secretless Authorization Injecting Secrets at Runtime Disposable Secrets
Conclusion
8. Core Practice: Continuously Test and Deliver. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
  79
  79
  80
  81
  82
  84
  87
  90
  93
  96
  99
 100
 102
 102
 102
 103
 103
 104
 104
105
106 106 108
| vii
Why Continuously Test Infrastructure Code? What Continuous Testing Means
What Should We Test with Infrastructure?
 Table of Contents
  
   Challenges with Testing Infrastructure Code 110 Challenge: Tests for Declarative Code Often Have Low Value 110 Challenge: Testing Infrastructure Code Is Slow 113 Challenge: Dependencies Complicate Testing Infrastructure 114
Progressive Testing 115 Test Pyramid 116 Swiss Cheese Testing Model 118
Infrastructure Delivery Pipelines 119 Pipeline Stages 120 Scope of Components Tested in a Stage 121 Scope of Dependencies Used for a Stage 121 Platform Elements Needed for a Stage 122 Delivery Pipeline Software and Services 123
Testing in Production 125 What You Can’t Replicate Outside Production 125 Managing the Risks of Testing in Production 126
Conclusion 128
9. Testing Infrastructure Stacks. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 129
Example Infrastructure 129 The Example Stack 130 Pipeline for the Example Stack 131
Offline Testing Stages for Stacks 131 Syntax Checking 132 Offline Static Code Analysis 132 Static Code Analysis with API 133 Testing with a Mock API 133
Online Testing Stages for Stacks 134 Preview: Seeing What Changes Will Be Made 134 Verification: Making Assertions About Infrastructure Resources 135 Outcomes: Proving Infrastructure Works Correctly 137
Using Test Fixtures to Handle Dependencies 137 Test Doubles for Upstream Dependencies 139 Test Fixtures for Downstream Dependencies 139 Refactor Components So They Can Be Isolated 141
Life Cycle Patterns for Test Instances of Stacks 142 Pattern: Persistent Test Stack 142 Pattern: Ephemeral Test Stack 143 Antipattern: Dual Persistent and Ephemeral Stack Stages 145 Pattern: Periodic Stack Rebuild 146 Pattern: Continuous Stack Reset 147
Test Orchestration 149
viii | Table of Contents
   
   Support Local Testing 149 Avoid Tight Coupling with Pipeline Tools 150 Test Orchestration Tools 150
Conclusion 151
Part III. Working with Servers and Other Application Runtime Platforms
10. Application Runtimes. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 155
Cloud Native and Application-Driven Infrastructure 156 Application Runtime Targets 157 Deployable Parts of an Application 157 Deployment Packages 158 Deploying Applications to Servers 159 Packaging Applications in Containers 159 Deploying Applications to Server Clusters 160 Deploying Applications to Application Clusters 161 Packages for Deploying Applications to Clusters 162 Deploying FaaS Serverless Applications 163 Application Data 164 Data Schemas and Structures 164 Cloud Native Application Storage Infrastructure 165 Application Connectivity 165 Service Discovery 166 Conclusion 168
11. Building Servers as Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 169
What’s on a Server 170 Where Things Come From 171 Server Configuration Code 172
Server Configuration Code Modules 173 Designing Server Configuration Code Modules 174 Versioning and Promoting Server Code 175 Server Roles 175
Testing Server Code 176 Progressively Testing Server Code 177 What to Test with Server Code 177 How to Test Server Code 178
Creating a New Server Instance 179 Hand-Building a New Server Instance 180 Using a Script to Create a Server 181 Using a Stack Management Tool to Create a Server 181
Table of Contents | ix
    
   Configuring the Platform to Automatically Create Servers 182
Using a Networked Provisioning Tool to Build a Server 182 Prebuilding Servers 183 Hot-Cloning a Server 184 Using a Server Snapshot 184 Creating a Clean Server Image 185 Configuring a New Server Instance 185 Frying a Server Instance 186 Baking Server Images 187 Combining Baking and Frying 188 Applying Server Configuration When Creating a Server 189 Conclusion 189
12. Managing Changes to Servers. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 191
Change Management Patterns: When to Apply Changes 192 Antipattern: Apply On Change 192 Pattern: Continuous Configuration Synchronization 194 Pattern: Immutable Server 195
How to Apply Server Configuration Code 198 Pattern: Push Server Configuration 198 Pattern: Pull Server Configuration 200
Other Server Life Cycle Events 202 Stopping and Restarting a Server Instance 202 Replacing a Server Instance 203 Recovering a Failed Server 204
Conclusion 205
13. Server Images as Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 207
Building a Server Image 208 Why Build a Server Image? 208 How to Build a Server Image 209 Tools for Building Server Images 209 Online Image Building Process 210 Offline Image Building Process 213
Origin Content for a Server Image 214 Building from a Stock Server Image 215 Building a Server Image from Scratch 215 Provenance of a Server Image and its Content 215
Changing a Server Image 216 Reheating or Baking a Fresh Image 216 Versioning a Server Image 217 Updating Server Instances When an Image Changes 218
x | Table of Contents
   
   Providing and Using a Server Image Across Teams 220
Handling Major Changes to an Image 220 Using a Pipeline to Test and Deliver a Server Image 221 Build Stage for a Server Image 222 Test Stage for a Server Image 223 Delivery Stages for a Server Image 224 Using Multiple Server Images 225 Server Images for Different Infrastructure Platforms 225 Server Images for Different Operating Systems 225 Server Images for Different Hardware Architectures 226 Server Images for Different Roles 226 Layering Server Images 226 Sharing Code Across Server Images 228 Conclusion 228
14. Building Clusters as Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 229
Application Cluster Solutions 230 Cluster as a Service 230 Packaged Cluster Distribution 231
Stack Topologies for Application Clusters 232 Monolithic Stack Using Cluster as a Service 233 Monolithic Stack for a Packaged Cluster Solution 234 Pipeline for a Monolithic Application Cluster Stack 235 Example of Multiple Stacks for a Cluster 238
Sharing Strategies for Application Clusters 241 One Big Cluster for Everything 242 Separate Clusters for Delivery Stages 242 Clusters for Governance 243 Clusters for Teams 244 Service Mesh 244
Infrastructure for FaaS Serverless 246 Conclusion 248
Part IV. Designing Infrastructure
15. Core Practice: Small, Simple Pieces. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 251
Designing for Modularity 252 Characteristics of Well-Designed Components 252 Rules for Designing Components 253 Use Testing to Drive Design Decisions 256
Modularizing Infrastructure 256
Table of Contents | xi
    
   Stack Components Versus Stacks as Components 257
Using a Server in a Stack 259 Drawing Boundaries Between Components 262 Align Boundaries with Natural Change Patterns 262 Align Boundaries with Component Life Cycles 263 Align Boundaries with Organizational Structures 265 Create Boundaries That Support Resilience 265 Create Boundaries That Support Scaling 266 Align Boundaries to Security and Governance Concerns 269 Conclusion 270
16. Building Stacks from Components. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 271
Infrastructure Languages for Stack Components 272 Reuse Declarative Code with Modules 272 Dynamically Create Stack Elements with Libraries 273
Patterns for Stack Components 274 Pattern: Facade Module 274 Antipattern: Obfuscation Module 276 Antipattern: Unshared Module 277 Pattern: Bundle Module 279 Antipattern: Spaghetti Module 280 Pattern: Infrastructure Domain Entity 283
Building an Abstraction Layer 285 Conclusion 286
17. Using Stacks as Components. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 287
Discovering Dependencies Across Stacks 287 Pattern: Resource Matching 288 Pattern: Stack Data Lookup 291 Pattern: Integration Registry Lookup 294 Dependency Injection 296
Conclusion 299
Part V. Delivering Infrastructure
 18.
xii |
Organizing Infrastructure Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 303
Organizing Projects and Repositories 303 One Repository, or Many? 304 One Repository for Everything 304 A Separate Repository for Each Project (Microrepo) 307 Multiple Repositories with Multiple Projects 308
Table of Contents
   
   Organizing Different Types of Code Project Support Files
Cross-Project Tests
Dedicated Integration Test Projects Organize Code by Domain Concept Organizing Configuration Value Files
Managing Infrastructure and Application Code Delivering Infrastructure and Applications Testing Applications with Infrastructure
Testing Infrastructure Before Integrating
Using Infrastructure Code to Deploy Applications
Conclusion
19. Delivering Infrastructure Code. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
Delivering Infrastructure Code
Building an Infrastructure Project
Packaging Infrastructure Code as an Artifact Using a Repository to Deliver Infrastructure Code
Integrating Projects
Pattern: Build-Time Project Integration Pattern: Delivery-Time Project Integration Pattern: Apply-Time Project Integration
Using Scripts to Wrap Infrastructure Tools Assembling Configuration Values Simplifying Wrapper Scripts
Conclusion
20. Team Workflows. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .
 309
 309
 310
 311
 312
 312
 313
 314
 315
 316
 317
 319
321
 321
 322
 323
 323
 326
 327
 330
 333
 335
 336
 337
 338
339
 340
 342
 344
 344
 345
 347
 348
 349
 349
 350
 350
 351
 352
 352
| xiii
The People
Who Writes Infrastructure Code? Applying Code to Infrastructure
Applying Code from Your Local Workstation Applying Code from a Centralized Service Personal Infrastructure Instances
Source Code Branches in Workflows
Preventing Configuration Drift Minimize Automation Lag Avoid Ad Hoc Apply
Apply Code Continuously Immutable Infrastructure
Governance in a Pipeline-based Workflow Reshuffling Responsibilities
 Table of Contents
  
Shift Left 353
An Example Process for Infrastructure as Code with Governance 353 Conclusion 354
21. Safely Changing Infrastructure. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 355
Reduce the Scope of Change 355 Small Changes 358 Example of Refactoring 359
Pushing Incomplete Changes to Production 361 Parallel Instances 361 Backward Compatible Transformations 364 Feature Toggles 366
Changing Live Infrastructure 368 Infrastructure Surgery 370 Expand and Contract 372 Zero Downtime Changes 375
Continuity 376 Continuity by Preventing Errors 377 Continuity by Fast Recovery 378 Continuous Disaster Recovery 379 Chaos Engineering 379 Planning for Failure 380
Data Continuity in a Changing System 382 Lock 382 Segregate 382 Replicate 383 Reload 383 Mixing Data Continuity Approaches 384
Conclusion 384
Index. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 385
## 5 Things I’ve Learned in 20 Years of Programming - Erik Dietrich

1.  **Duplication of Knowledge is the Worst**. Avoid duplicating code when you can make something more reusable.
    
2.  **Code is a Liability**. It might feel good to write good, clean code. But we need to remember that it is a _liability_. Erik consulted on over one thousand codebases and found that the most undesirable property was the _size of the codebase_. Use as little code as humanly possible.
    
3.  **Senior Developers: Trust but Verify**. You can learn a lot from senior developers. It is, however, important that you trust what they say but validate their claims as well.
    
4.  **TDD is a Game-Changer**. Learn to love TDD. Erik was skeptical at first, and then became a proponent when first using it himself. You can ensure that what you code will work the first time around by catching mistakes early.
    
5.  **Evidence is King**. Support any claims or opinions that you have with facts and evidence. This can pertain to anything from the work that you perform to your career progression.

## Technical Debt - Jon Thornton (Squarespace Engineering)

Tech debt is defined as _work that will have to be done in the future_**_._** So we can either track spending in terms of the time that will be sent on future work, or we can invest time in the work now. Three good kinds of technical debt are:‌

**1. Scaffolding**

Validate the riskiest parts of building an application **first**. This means anything that is easiest to get wrong, because they are:
-   Complicated
-   Difficult to define
-   Not well understood

Scaffold the risky parts of the application, and just **make it work**. Doing so allows you to obtain real-world feedback quickly. Commit to an estimate to ensure you aren't taking on too much complexity. Understand the scaffold's limitations - avoid using it where failure would cause harm.

> Scaffolding can help you adjust the order in which you build parts of your application by filling in for dependencies, so that you’re not stuck building components before you have a way to validate them. Our throw-away email sender got us feedback on the email editor while the code was still fresh in our minds, helping us iterate faster and perfect our hardest problem. When it came time to build the real email sender, we did it with lessons learned from building the scaffolding.

**2. Hardcoding Things**

-   Can changes take several hours to take effect? Changes require deploying new code into production
    
-   Is Git an acceptable update UI? Is there someone involved in the process who knows Git?
    
-   Are there existing UI, validation, and data patterns? If your app has patterns that solve your problem, hardcoding may not be the best approach‌

**3. Not Fixing All the Edge Cases**


Bugs are just tech debt that users can see. What is the effort of fixing a bug versus intentionally not fixing it? Verify the impact and take a decision accordingly.


**Good technical debt is intentional**. Be intentional about what you invest time in and aware of the costs you're taking on. Build less, because you can always build more. Good tech debt has clear, well-known limitations.

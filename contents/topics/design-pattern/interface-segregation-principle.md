## Interface Segregation Principle
- The Interface Segregation Principle states that clients should not be forced to implement interfaces they don't use.
    - That also include not imposing the clients with the burden of implementing methods that they don’t actually need. 
- ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. 
    - Such shrunken interfaces are also called role interfaces. 
- Correct abstraction is the key to Interface Segregation Principle
- With this approach, concrete classes implement only as much as those abstractions require them to. 
    - So we end up with satisfying the Interface Segregation Principle even without knowing that it exists.  
- Think about whether your abstractions are reusable and composable, and whether your objects are encapsulated and cohesive.
- This principle is very much related to the Single Responsibility Principle.
- Keep your interfaces thin or fine-grained and don’t attach to them unused methods. 
- You will have to be more resourceful with the naming as you will have to name a few more types than you do already. 
- Such thin interfaces are also called role interfaces as its easier to refactor, change, and redeploy something that it has a very defined role or purpose.
- Fat interfaces lead to inadvertent coupling between classes and you should avoid them. 
    - Do I really need all the methods on this interface I’m using? 
    - If not how can I break them into smaller interfaces?
- That’s fine because it gives you the flexibility to compose thinner interfaces into bigger ones if you need to.      
- Instead of one fat interface many small interfaces are preferred based on groups of methods, each one serving one submodule.
- Like every principle Interface Segregation Principle is one principle which require additional time and effort spent to apply it during the design time 
    - and increase the complexity of code. 
    - But it produce a flexible design. 
- If we are going to apply it more than is necessary it will result a code containing a lot of interfaces with single methods, 
    - so applying should be done based on experience 
    - and common sense in identifying the areas where extension of code are more likely to happens in the future.
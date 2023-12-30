# Strategy Design Pattern
Lyman expalnation : When we some functionality in base class which is not used by child classes and multiple classes are implementing thier own specialized method which is common in them slef but because iti is not avaialble in the parent class they are duplicating the code 

## to solve this problem we used Starategy pattern where we created a diffrent Interface where we just declared all the posible capabilities.methods now insted of assign ning a specific class object to the proerty of higher level class we are just decalsreinf the interface propertey and by using the constructor injection we are allowing to pass lower level calsses which capabilitiew they wanted to use .

### It is similar to what we have done in dependency inversion example of Mackbook , keyboard and Mouse 

![Example Image](example.jpg)
![Example Image](example.jpg)


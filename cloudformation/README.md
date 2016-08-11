Advanced Infrastructure as Code: Building Modular, Dynamic AWS CloudFormation Stacks
====================================================================================

### Agenda
* Cloudformation fundamentals
* Advanced best practices
* Other shit.

### Best Practices
* Naming conventions
    * Don't use "launch wizard" actually name your shit right.
    * Develop a comprehensive naming standard and use it.
* Stack orginization
    * Layered architecture, super stacks passing down via parameters and outputs.
        * The blast radius here is bad
        * You can accidentally blow up all of your environments if you don't do automation
        * If you do CICD then Layered is OK.
    * Service Oriented Architecture
        * If you do things in paralell, then your stacks don't talk to eachother.
    * Which do you use? __Both__
    * You can use the layered approach as a mechanism of governance.
* *Service catalog.* You can quickly get a bunch of stuff straight out of the box.
    * Is this too much to manage? Probably.
    * Cloudformation is just a dataformat language, but we need a better way to do this. We need a *framework* to handle this appropriately.

### Frameworks

We want to generate our json, we don't want to write it. We've seen a bunch of different libraries here in different language

1. [Troposphere](https://github.com/cloudtools/troposphere)
    * This thing is way way way better.
1. [SparkleFormation](http://www.sparkleformation.io)

    
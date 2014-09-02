WPezBoilerStrap
===============

Getting Started: 0.0.1
======================

Alpha / Draft - That is, there could be typos, misspellings, etc.
-----------------------------------------------------------------

###Overview

WPezBoilerStrap (Uno) isn't so much a single theme as it is a working demonstration of the re-invention of the WordPress theme architecture and workflow, as enabled by WPezClasses (https://github.com/WPezClasses). 


### IMPORTANT - This is a different - dare I say new & improved - way to think about WordPress theme design and theme development. If you're looking for just add water simplicity please move on. Actually, the concepts here are quite simple. However, within the context of tradtional WP thinking it might be a bit much for some to want to swallow. This is not meant to offend everyone. It's simply nore a mass market product / architecture.

=========================================================================================================


1. "Why should I care? What's in it for me?"
-------------------------------------------

If you're an agency or an independent WordPress developer and you're developing six or more bespoke WordPress based products per year, and you want to optimize resources (time and money) yet also develop superior, more robust products then please continue reading. 

This tool is not intended for commercial themes and/or themes for the WP.org theme repo. 


2. "Where should I start?"
-------------------------

First, get familiar with WPezClasses. You don't have to be intimate with the details, yet. But understanding its basic whys and hows will help. 
- https://github.com/WPezClasses/wp-ezclasses-docs-getting-started


3. "Okay. Great. Now what?"
--------------------------

Great. Let's do a quick overview of some of the programming concepts that went into the DNA of this new architecture. 

- DRY - Don't Repeat Yourself: http://en.wikipedia.org/wiki/Don't_repeat_yourself

- SRP - Single Responsibility Principle: http://en.wikipedia.org/wiki/Single_responsibility_principle

- OOP - Object Oriented Programming: http://en.wikipedia.org/wiki/Object-oriented_programming

- MVC - Model View Controler: http://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller


4. "Why do you use Modl Vue Ctrlr instead of Model View Controler?"
-------------------------------------------------------------------

Frankly, I didn't want pushback from MVC purists. The goal was to embrace the MVC ideal but bend it a bit in the context of "The WordPress Way." 


5. "Make sense. What next?"
---------------------------

Open up the theme's functions.php and then work your way down. As you hit these other components, open them and have a look...

- ezbsGlobal - Stores and manages key global variables. This is useful when you have a child theme. 

- ezbsModl - Used to communicate details to the vue(s). Notice it extends another class. In this new archtiecture, the theme is simply the raw structure (with some bits of logic). The Modl is used to fill in the blanks of the theme (i.e., vue(s)). In other words, a theme (read: structure) can have multiple Modls. The other key innovation is that the values supplied to a vue by the Modl can be manipulated on the fly. That is, business rules / logic as it relates to the structure are centralized in the Modl.  

- ez_gtp() is a reworking of WordPress' get_template_part(). It's more or less the same but now it also has a bool that act as a switch. If you have a biz rule and don't want a particualr TP, just set the bool to false. 

- The use of ez_gtp() in the functions.php to define the theme's "gut" now means it's ez to reconfigure each module in a child theme. 


6. "That's it?"
---------------

Yup. Believe it or not, that's it. The magic is how most everything has been reorganized, as well as how the Modl becomes the centralized brains that manages and manipulates the structure (i.e., theme).

While I don't want use the word "decoupled" - and suffer the wrath of OOP purists - I will say that how the architecture "thinks" does feels more natural and logical. This is especially true if you want to reuse previous work and/or improve your workflow. 


7. "But I still feel a bit overwhelmed..."
------------------------------------------

Understood. Not to cloud the waters but also keep in mind the Holy Grail of this effort is to enable TREATRT: "The Right Experience At The Right Time," as well as providing granular control of reusable modules of code. 

That is, to make it easier to reuse vue(s), as well as be able to easily manipulate how and when you use a theme's given set of vues.

This architecture wants to configure more and code less. It wants to reuse code as much as possible. And it wants to provide more robust control - via the Modl - of the experience being delivered.
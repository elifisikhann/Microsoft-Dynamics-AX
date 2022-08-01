# Develop object-oriented code in Finance and Operations apps


# Implement Chain of Command

Chain of Command (CoC) is a functionality for class extensions.
When you wrap a method, you can also access the base class's protected methods, public methods, and variables. It is important to understand this concept, as **base code cannot be changed in Dynamics 365 Finance and Operations** apps development.

 If the method uses a hookable attribute that is set to false, `[Hookable(false)]`, or a wrappable attribute that is set to false, `[Wrappable(false)]`, the method cannot be wrapped. Methods that use the final keyword cannot be wrapped in an extension class. Private methods are also excluded from extensibility.

Access identifiers are  `[public]`,  `[protected]`, and  `[private]`.

# Implement X++ scoping and access identifiers

-   **Public**  - Methods that are declared as public can be called from anywhere that the class is accessible. In addition, a public method can be overridden by a subclass unless the method is declared as final.
-   **Protected**  - Methods that are protected can be overridden in subclasses. Methods that are declared as protected can be called only from:
    -   Methods in the class.
    -   Methods in a subclass of the class that contains the protected method.
-   **Private**  - Methods that are declared as private can be called only from methods in the class where the private method is declared. No private method can be overridden in a subclass. When you create a new method, the default accessor keyword that appears in the code editor is private. This is the most conservative default for maximum security.

## Internal
When you select a class or method as internal, it can only be accessed from within the model where it is defined.

# Interfaces
An _interface_ is a specification for a set of public instance methods. An interface defines and enforces similarities between unrelated classes without having to derive one class from the other. All interfaces are public. When you add the `implements` keyword on a class declaration, the class must declare the methods that are specified by the interface.


**1. What methods can you extend to use Chain of Command?**

Methods declared with the keyword final
Private methods
**Protected and public methods**
Methods tagged with the attribute hookable(false)

**2.** **Which of the following statements is NOT true about variable declarations?**

You can use var to declare local variables for declarations of for loop counters
You can declare a variable wherever statements can be provided.
**You can declare a variable after the variable is used.**
You can declare variables in smaller scopes, outside which the variables can’t be referenced.


Object-oriented programming (OOP) is a programming paradigm that is modeled around objects and how you manipulate them. Objects can be physical objects, such as a car or a bicycle, or more abstract concepts, such as messages, collections, and parameters. Objects have attributes (data) and behavior (methods).


-------------------------------------------
The `SysObsoleteAttribute(message,setError)` attribute can be used on methods or classes that should no longer be used. During the build process, the user will be notified with a detailed message that appears in the output windows.

**[SysObsoleteAttribute("The Automobile class might have faster performance.", false)]** 
class  Bicycle 
{ 
// Members of the Bicycle class go here. 
}

**Attributes** have many uses, including the following:

-   Using the  `WebMethod`  attribute in Web services to indicate if the method should be callable over the Simple Object Access Protocol (SOAP) to exchange information.
-   Using  `DLLImportAttribute`  to call unmanaged code.
-   Describing the title, version, description, or trademark of an assembly.
-   Describing how to map between classes, members, and eXtensible Markup Language (XML) nodes for serialization.
-   Describing the security requirements for methods.
-   Specifying characteristics to enforce security.
-   Getting information about the caller to a method.

> 
> public class PracticeAttribute extends SysAttribute  
> {    // Fields in the classDeclaration.    
	> StartEnd startEndEnum;   
	  str reason;
> 
>    // Constructor.    
>    public void new(StartEnd _startEndEnum, str
> _reason)   
> {
>     startEndEnum = _startEndEnum;
>     reason = _reason;   
>     }  
>     } 
>     [PracticeAttribute(StartEnd::End, "Use the RegularClass class at the end.")]  
>     public class RegularClass  
>     {
>     [PracticeAttribute(Startend::Start, "Use the rehearse method at the start.")] 	
>     public int rehearse()
>     {
>       // Logic goes here.
>     }
>       // More fields and methods belong here. 
>       }





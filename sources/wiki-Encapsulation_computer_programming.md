---
source: https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)
fetched: 2026-06-19
---

Bundling of data For other uses, see [Encapsulation](./Encapsulation_(disambiguation)). 

In software systems, **encapsulation** refers to the bundling of data with the mechanisms or methods that operate on the data.  It may also refer to the limiting of direct access to some of that data, such as an object's components.[[1]](./Encapsulation_(computer_programming)#cite_note-Rogers01-1) Essentially, encapsulation prevents external code from being concerned with the internal workings of an object.

 

Encapsulation allows developers to present a consistent interface that is independent of its internal implementation. As one example, encapsulation can be used to hide the values or state of a structured data object inside a [class](./Class_(programming)). This prevents clients from directly accessing this information in a way that could expose hidden implementation details or violate [state](./State_(computer_science)) invariance maintained by the methods.

 

Encapsulation also encourages programmers to put all the code that is concerned with a certain set of data in the same class, which organizes it for easy comprehension by other programmers. Encapsulation is a technique that encourages [decoupling](./Coupling_(computer_programming)).

 

All [object-oriented programming](./Object-oriented_programming) (OOP) systems support encapsulation,[[2]](./Encapsulation_(computer_programming)#cite_note-2)[[3]](./Encapsulation_(computer_programming)#cite_note-3) but encapsulation is not unique to OOP. Implementations of [abstract data types](./Abstract_data_types), [modules](./Module_(programming)), and [libraries](./Library_(computing)) also offer encapsulation. The similarity has been explained by programming language theorists in terms of [existential types](./Existential_types).[[4]](./Encapsulation_(computer_programming)#cite_note-4)

 

## Meaning

 

In [object-oriented programming languages](./Object-oriented_programming_languages), and other related fields,  [[object&#x2D;oriented programming language]]  and related fields, like [[OODMBS]], encapsulation refers to one of two related but distinct notions, and sometimes to the combination thereof:[[5]](./Encapsulation_(computer_programming)#cite_note-5)[[6]](./Encapsulation_(computer_programming)#cite_note-Dale-6)

 
- A language mechanism for restricting direct access to some of the [object](./Object_(computer_science))'s components.[[7]](./Encapsulation_(computer_programming)#cite_note-7)[[8]](./Encapsulation_(computer_programming)#cite_note-Pierce-8)
- A language construct that facilitates the bundling of data with the [methods](./Method_(computer_programming))  I object to the word method being used here because in lisp languages programmers cannot distinguish methods from normal functions at the [[call site]].  Behavior equivalent to methods may be implemented as normal functions. encapsulation is not dependent on implementation but on behavior (or other functions) operating on those data.[[1]](./Encapsulation_(computer_programming)#cite_note-Rogers01-1)[[9]](./Encapsulation_(computer_programming)#cite_note-9)

 

Some programming language researchers and academics use the first meaning alone or in combination with the second as a distinguishing feature of [object-oriented programming](./Object-oriented_programming), while some programming languages that provide [lexical closures](./Closure_(computer_programming)) view encapsulation as a feature of the language [orthogonal](./Orthogonality#Computer_science) to object orientation.

 

The second definition reflects that in many object-oriented languages, and other related fields, the components are not hidden automatically and this can be overridden. Thus, [information hiding](./Information_hiding) is defined as a separate notion by those who prefer the second definition.

 this is based on all the refs given above, so no inline cite here 

The features of encapsulation are supported using [classes](./Class_(programming)) in most object-oriented languages, although other alternatives also exist.

 

Encapsulation may also refer to containing a repetitive or complex process in a single unit to be invoked. Object-oriented programming facilitates this at both the method and class levels. This definition is also applicable to [procedural programming](./Procedural_programming).[[10]](./Encapsulation_(computer_programming)#cite_note-10)

 

### Encapsulation and inheritance

 

The authors of *[Design Patterns](./Design_Patterns)* discuss the tension between [inheritance](./Inheritance_(object-oriented_programming)) and encapsulation at length and state that in their experience, designers overuse inheritance. They claim that inheritance often breaks encapsulation, given that inheritance exposes a subclass to the details of its parent's implementation.[[11]](./Encapsulation_(computer_programming)#cite_note-GoF-11) As described by the [yo-yo problem](./Yo-yo_problem), overuse of inheritance and therefore encapsulation, can become too complicated and hard to debug.

 

## Information hiding

 Main article: [Information hiding](./Information_hiding) 

Under the definition that encapsulation "can be used to hide data members and member functions", the internal representation of an [object](./Object_(computer_science)) is generally hidden outside of the object's definition. Typically, only the object's own methods can directly inspect or manipulate its fields. Hiding the internals of the object protects its integrity by preventing users from setting the internal data of the component into an invalid or inconsistent state. A supposed benefit of encapsulation is that it can reduce system complexity, and thus increase [robustness](./Robustness_(computer_science)), by allowing the developer to limit the interdependencies between software components.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Some languages like [Smalltalk](./Smalltalk) and [Ruby](./Ruby_(programming_language)) only allow access via object methods, but most others (e.g., [C++](./C++), [C#](./C_Sharp_(programming_language)), [Delphi](./Delphi_(programming_language)) or [Java](./Java_(programming_language))[[12]](./Encapsulation_(computer_programming)#cite_note-FOOTNOTEBloch201873–77Chapter_§4_Item_15_Minimize_the_accessibility_of_classes_and_members-12)) offer the programmer some control over what is hidden, typically via keywords like `public` and `private`.[[8]](./Encapsulation_(computer_programming)#cite_note-Pierce-8) ISO C++ standard refers to `protected`, `private` and `public` as "[access specifiers](./Access_specifiers)" and that they do not "hide any information". Information hiding is accomplished by furnishing a compiled version of the source code that is interfaced via a header file.

 

Almost always, there is a way to override such protection – usually via [reflection](./Reflection_(computer_programming)) API (Ruby, Java, C#, etc.), sometimes by mechanism like [name mangling](./Name_mangling) ([Python](./Python_(programming_language))), or special keyword usage like `friend` in C++. Systems that provide object-level [capability-based security](./Capability-based_security) (adhering to the [object-capability model](./Object-capability_model)) are an exception, and guarantee strong encapsulation.

 

### Examples

 

#### Restricting data fields

 

Languages like [C++](./C++), [C#](./C_Sharp_(programming_language)), [Java](./Java_(programming_language)),[[12]](./Encapsulation_(computer_programming)#cite_note-FOOTNOTEBloch201873–77Chapter_§4_Item_15_Minimize_the_accessibility_of_classes_and_members-12) [PHP](./PHP), [Swift](./Swift_(programming_language)), and [Delphi](./Delphi_(programming_language)) offer ways to restrict access to data fields.

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1c/UML_encapsulation.svg/960px-UML_encapsulation.svg.png)](./File:UML_encapsulation.svg)

 

Below is an example in [C#](./C_Sharp_(programming_language)) that shows how access to a data field can be restricted through the use of a `private` keyword:

 
```
class Program
{
    public class Account
    {
        private decimal _accountBalance = 500.00m;

        public decimal CheckBalance()
        {
            return _accountBalance;
        }
    }

    static void Main()
    {
        Account myAccount = new();
        decimal myBalance = myAccount.CheckBalance();

        /* This Main method can check the balance via the public
         * "CheckBalance" method provided by the "Account" class 
         * but it cannot manipulate the value of "accountBalance" */
    }
}

```
 

Below is an example in [Java](./Java_(programming_language)):

 
```
public class Employee {
    private BigDecimal salary = new BigDecimal(50000.00);
    
    public BigDecimal getSalary() {
        return this.salary;
    }

    public static void main() {
        Employee e = new Employee();
        BigDecimal sal = e.getSalary();
    }
}

```
 Below is an example in [[PHP]]:

<syntaxhighlight lang="php"&#x3E;
class Account
{
    /**
     * How much money is currently in the account
     * @var float
     */
    private $accountBalance;

    /**
     * @param float $currentAccountBalance Initialize account to this dollar amount
     */
    public function __construct($currentAccountBalance)
    {
        $this&#x2D;&#x3E;accountBalance = $currentAccountBalance;
    }

    /**
     * Add money to account
     * @param float $money Dollars to add to balance
     * @return void
     */
    public function deposit($money): null
    {
        $this&#x2D;&#x3E;accountBalance += $money;
    }

    /**
     * Remove money from account
     * @param float $money Dollars to subtract from balance
     * @throws Exception
     * @return void
     */
    public function withdraw($money): null
    {
        if ($this&#x2D;&#x3E;accountBalance < $money) {
            throw new Exception('Cannot withdraw $' . $money . ' from account as it contains $' . $this&#x2D;&#x3E;accountBalance);
        }
        $this&#x2D;&#x3E;accountBalance &#x2D;= $money;
    }

    /**
     * Get current account balance, that takes all additions and subtractions into consideration.
     * @return float
     */
    public function getAccountBalance() {
        return $this&#x2D;&#x3E;accountBalance;
    }
}

// Create a new object from the Account class with a starting balance of $500.00
$myAccount = new Account(500.00);

// We have clearly defined methods for adding and subtracting money from the Account
// If we didn't have a method for withdraw(), nothing would prevent us from withdrawing more money than was available in the account
$myAccount&#x2D;&#x3E;deposit(10.24);
$myAccount&#x2D;&#x3E;withdraw(4.45);

// Get the current balance
$accountBalance = $myAccount&#x2D;&#x3E;getAccountBalance();
echo 'My Account Balance: $' . $accountBalance; // 505.79

// Our code forbids us from withdrawing more than we have
$myAccount&#x2D;&#x3E;withdraw(600.00); // Exception Message: Cannot withdraw $600 from account as it contains $505.79
</syntaxhighlight&#x3E;

Below is an example in [[Swift (programming language)|Swift]]. The <code&#x3E;balance</code&#x3E; property cannot be accessed directly; a merchant can only check whether the requested amount is available for spending using the <code&#x3E;isAvailable(_:)</code&#x3E; method.

<syntaxhighlight lang="swift"&#x3E;
struct CreditCard {
    
    private var balance: Double
    
    init(withBalance balance: Double) {
        self.balance = balance
    }
    
    func isAvailable(_ amount: Double) &#x2D;&#x3E; Bool {
        return balance &#x3E;= amount
    }
    
}

var myCard = CreditCard(withBalance: 100)
myCard.balance // Error: 'balance' is inaccessible due to 'private' protection level
myCard.isAvailable(100) // true
myCard.isAvailable(101) // false
</syntaxhighlight&#x3E; 

Encapsulation is also possible in non-object-oriented languages. In [C](./C_(programming_language)), for example, a structure can be declared in the public API via the header file for a set of functions that operate on an item of data containing data members that are not accessible to clients of the API with the `extern` keyword.[[13]](./Encapsulation_(computer_programming)#cite_note-13)

 
```
// Header file "api.h"
#pragma once

typedef struct Entity Entity; // Opaque structure with hidden members

// API functions that operate on 'Entity' objects
Entity* openEntity(int id);
int processEntity(Entity* e);
void closeEntity(Entity* e);

```
 

Clients call the API functions to allocate, operate on, and deallocate objects of an [opaque data type](./Opaque_data_type). The contents of this type are known and accessible only to the implementation of the API functions; clients cannot directly access its contents. The source code for these functions defines the actual contents of the structure:

 
```
// Implementation file "api.c"

#include "api.h"

typedef struct Entity {
    int ent_id; // ID number
    char ent_name[20]; // Name
    ... and other members ...
} Entity;

// API function implementations
Entity* openEntity(int id) { 
    // ... 
}

int processEntity(Entity* e) {
    // ... 
}

void closeEntity(Entity* e) {
    // ... 
}

```
 

#### Name mangling

 Main article: [Name mangling](./Name_mangling) 

Below is an example of [Python](./Python_(programming_language)), which does not support variable access restrictions. However, the convention is that a variable whose name is prefixed by an underscore should be considered private.[[14]](./Encapsulation_(computer_programming)#cite_note-14)

 
```
class Car: 
    def __init__(self) -> None:
        self._maxspeed = 200
 
    def drive(self) -> None:
        print(f"Maximum speed is {self._maxspeed}.")
 
redcar: Car = Car()
redcar.drive()  # This will print 'Maximum speed is 200.'

redcar._maxspeed = 10
redcar.drive()  # This will print 'Maximum speed is 10.'

```
 

## See also

 
- [Inheritance (object-oriented programming)](./Inheritance_(object-oriented_programming))
- [Object-oriented programming](./Object-oriented_programming)
- [Software design pattern](./Software_design_pattern)
- [Facade pattern](./Facade_pattern)

 

## Citations

  
1. [1](./Encapsulation_(computer_programming)#cite_ref-Rogers01_1-0) [2](./Encapsulation_(computer_programming)#cite_ref-Rogers01_1-1) Rogers, Wm. Paul (18 May 2001). ["Encapsulation is not information hiding"](https://www.infoworld.com/article/2075271/encapsulation-is-not-information-hiding.html). *[JavaWorld](./JavaWorld)*. Retrieved 2020-07-20.
2. [↑](./Encapsulation_(computer_programming)#cite_ref-2) ["What is Object-Oriented Programming (OOP)?"](https://www.techtarget.com/searchapparchitecture/definition/object-oriented-programming-OOP). *App Architecture*. Retrieved 2024-03-02.
3. [↑](./Encapsulation_(computer_programming)#cite_ref-3) ["Encapsulation in Object Oriented Programming (OOPS)"](https://www.enjoyalgorithms.com/blog/encapsulation-in-oops/). *www.enjoyalgorithms.com*. Retrieved 2024-03-02.
4. [↑](./Encapsulation_(computer_programming)#cite_ref-4) [Pierce 2002](./Encapsulation_(computer_programming)#CITEREFPierce2002), § 24.2 Data Abstraction with Existentials
5. [↑](./Encapsulation_(computer_programming)#cite_ref-5) Scott, Michael Lee (2006). *Programming language pragmatics* (2 ed.). Morgan Kaufmann. p. 481. [ISBN](./ISBN_(identifier)) [978-0-12-633951-2](./Special:BookSources/978-0-12-633951-2). Encapsulation mechanisms enable the programmer to group data and the subroutines that operate on them together in one place, and to hide irrelevant details from the users of an abstraction
6. [↑](./Encapsulation_(computer_programming)#cite_ref-Dale_6-0) Dale, Nell B.; Weems, Chip (2007). *Programming and problem solving with Java* (2nd ed.). Jones & Bartlett. p. 396. [ISBN](./ISBN_(identifier)) [978-0-7637-3402-2](./Special:BookSources/978-0-7637-3402-2).
7. [↑](./Encapsulation_(computer_programming)#cite_ref-7) [Mitchell, John C.](./John_C._Mitchell) (2003). *Concepts in programming languages*. Cambridge University Press. p. 522. [ISBN](./ISBN_(identifier)) [978-0-521-78098-8](./Special:BookSources/978-0-521-78098-8).
8. [1](./Encapsulation_(computer_programming)#cite_ref-Pierce_8-0) [2](./Encapsulation_(computer_programming)#cite_ref-Pierce_8-1) [Pierce, Benjamin](./Benjamin_C._Pierce) (2002). [*Types and Programming Languages*](./Types_and_Programming_Languages). MIT Press. p. 266. [ISBN](./ISBN_(identifier)) [978-0-262-16209-8](./Special:BookSources/978-0-262-16209-8).
9. [↑](./Encapsulation_(computer_programming)#cite_ref-9) Connolly, Thomas M.; Begg, Carolyn E. (2005). "Ch. 25: Introduction to Object DMBS § Object-oriented concepts". *Database systems: a practical approach to design, implementation, and management* (4th ed.). Pearson Education. p. 814. [ISBN](./ISBN_(identifier)) [978-0-321-21025-8](./Special:BookSources/978-0-321-21025-8).
10. [↑](./Encapsulation_(computer_programming)#cite_ref-10) McDonough, James E. (2017). "Encapsulation". *Object-Oriented Design with ABAP: A Practical Approach*. [Apress](./Apress). [doi](./Doi_(identifier)):[10.1007/978-1-4842-2838-8](https://doi.org/10.1007%2F978-1-4842-2838-8). [ISBN](./ISBN_(identifier)) [978-1-4842-2837-1](./Special:BookSources/978-1-4842-2837-1) – via [O'Reilly](./O'Reilly_Media).
11. [↑](./Encapsulation_(computer_programming)#cite_ref-GoF_11-0) Gamma, Erich; Helm, Richard; Johnson, Ralph; Vlissides, John (1994). [*Design Patterns*](https://archive.org/details/designpatternsel00gamm). Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0-201-63361-0](./Special:BookSources/978-0-201-63361-0).
12. [1](./Encapsulation_(computer_programming)#cite_ref-FOOTNOTEBloch201873–77Chapter_§4_Item_15_Minimize_the_accessibility_of_classes_and_members_12-0) [2](./Encapsulation_(computer_programming)#cite_ref-FOOTNOTEBloch201873–77Chapter_§4_Item_15_Minimize_the_accessibility_of_classes_and_members_12-1) [Bloch 2018](./Encapsulation_(computer_programming)#CITEREFBloch2018), pp. 73–77, Chapter §4 Item 15 Minimize the accessibility of classes and members.
13. [↑](./Encapsulation_(computer_programming)#cite_ref-13) King, K. N. (2008). *C Programming: A Modern Approach* (2nd ed.). W. W. Norton & Company. p. 464. [ISBN](./ISBN_(identifier)) [978-0393979503](./Special:BookSources/978-0393979503).
14. [↑](./Encapsulation_(computer_programming)#cite_ref-14) Bader, Dan. ["The Meaning of Underscores in Python"](https://dbader.org/blog/meaning-of-underscores-in-python). *Improve Your Python Skills*. Retrieved 1 November 2019.

 

## References

 
- Bloch, Joshua (2018). *"Effective Java: Programming Language Guide"* (third ed.). Addison-Wesley. [ISBN](./ISBN_(identifier)) [978-0134685991](./Special:BookSources/978-0134685991).
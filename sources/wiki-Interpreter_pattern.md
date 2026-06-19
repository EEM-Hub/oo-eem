---
source: https://en.wikipedia.org/wiki/Interpreter_pattern
fetched: 2026-06-19
---

Approach in computer programming 
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Interpreter pattern"–news·newspapers·books·scholar·JSTOR(November 2008)(Learn how and when to remove this message) |
| --- | --- |

 

In [computer programming](./Computer_programming), the **interpreter pattern** is a [design pattern](./Design_pattern_(computer_science)) that specifies how to evaluate sentences in a language.
The basic idea is to have a [class](./Class_(computer_science)) for each symbol ([terminal](./Terminal_symbol) or [nonterminal](./Nonterminal_symbol)) in a [specialized computer language](./Domain_specific_languages). The [syntax tree](./Abstract_syntax_tree) of a sentence in the language is an instance of the [composite pattern](./Composite_pattern) and is used to evaluate (interpret) the sentence for a client.[[1]](./Interpreter_pattern#cite_note-GoF-1): 243  See also [Composite pattern](./Composite_pattern).

 

## Overview

 

The Interpreter
[[2]](./Interpreter_pattern#cite_note-GoF2-2)
design pattern is one of the twenty-three well-known 
*[GoF design patterns](./Design_Patterns)* 
that describe how to solve recurring design problems to design flexible and reusable object-oriented software, that is, objects that are easier to implement, change, test, and reuse.

 

### What problems can the Interpreter design pattern solve?

 

Source:[[3]](./Interpreter_pattern#cite_note-3)

 
- A [grammar](./Backus-Naur_form) for a simple language should be defined
- so that sentences in the language can be interpreted.

 

When a problem occurs very often, it could be considered to represent it as a sentence in a simple language
([Domain Specific Languages](./Domain-specific_language)) so that an interpreter can solve the problem
by interpreting the sentence.

 

For example, when many different or complex search expressions must be specified.
Implementing (hard-wiring) them directly into a class is inflexible
because it commits the class to particular expressions and makes it impossible to specify new expressions or change existing ones independently from (without having to change) the class.

 

### What solution does the Interpreter design pattern describe?

 
- Define a grammar for a simple language by defining an `Expression` class hierarchy and implementing an `interpret()` operation.
- Represent a sentence in the language by an abstract syntax tree (AST) made up of `Expression` instances.
- Interpret a sentence by calling `interpret()` on the AST.

 

The expression objects are composed recursively into a composite/tree structure that is called
*abstract syntax tree* (see [Composite pattern](./Composite_pattern)).

The Interpreter pattern doesn't describe how
to build an abstract syntax tree. This can
be done either manually by a client or automatically by a [parser](./Parser).

 

See also the UML class and object diagram below.

 

## Uses

 
- Specialized database query languages such as [SQL](./SQL).
- Specialized computer languages that are often used to describe communication protocols.
- Most general-purpose computer languages actually incorporate several specialized languages[*[citation needed](./Wikipedia:Citation_needed)*].

 

## Structure

 

### UML class and object diagram

 [![](//upload.wikimedia.org/wikipedia/commons/3/33/W3sDesign_Interpreter_Design_Pattern_UML.jpg)](./File:W3sDesign_Interpreter_Design_Pattern_UML.jpg)A sample UML class and object diagram for the Interpreter design pattern.[[4]](./Interpreter_pattern#cite_note-4) 

In the above [UML](./Unified_Modeling_Language) [class diagram](./Class_diagram), the `Client` class refers to the common `AbstractExpression` interface for interpreting an expression
`interpret(context)`.

The `TerminalExpression` class has no children and interprets an expression directly.

The `NonTerminalExpression` class maintains a container of child expressions
(`expressions`) and forwards interpret requests
to these `expressions`.

 

The object collaboration diagram 
shows the run-time interactions: The `Client` object sends an interpret request to the abstract syntax tree.
The request is forwarded to (performed on) all objects downwards the tree structure.

The `NonTerminalExpression` objects (`ntExpr1,ntExpr2`) forward the request to their child expressions.

The `TerminalExpression` objects (`tExpr1,tExpr2,…`) perform the interpretation directly.

 

### UML class diagram

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Interpreter_UML_class_diagram.svg/960px-Interpreter_UML_class_diagram.svg.png)](./File:Interpreter_UML_class_diagram.svg)

 

## Example

  Wikipedia is not a list of examples. Do not add examples from favorite programming languages here; this page exists to explain the design pattern, not to show how it interacts with subtleties of every language extant. Feel free to add examples at: http://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Interpreter  

This C++23 implementation is based on the pre C++98 sample code in the book.

 
```
import std;

using String = std::string;
template <typename K, typename V>
using TreeMap = std::map<K, V>;
template <typename T>
using UniquePtr = std::unique_ptr<T>;

class BooleanExpression {
public:
    BooleanExpression() = default;
    virtual ~BooleanExpression() = default;
    virtual bool evaluate(Context&) = 0;
    virtual UniquePtr<BooleanExpression> replace(String&, BooleanExpression&) = 0;
    virtual UniquePtr<BooleanExpression> copy() const = 0;
};

class VariableExpression;

class Context {
private:
    TreeMap<const VariableExpression*, bool> m;
public:
    Context() = default;

    [[nodiscard]]
    bool lookup(const VariableExpression* key) const { 
        return m.at(key); 
    }

    void assign(VariableExpression* key, bool value) { 
        m[key] = value; 
    }
};

class VariableExpression : public BooleanExpression {
private:
    String name;
public:
    VariableExpression(const String& name):
        name{name} {}

    virtual ~VariableExpression() = default;

    [[nodiscard]]
    virtual bool evaluate(Context& context) const {
        return context.lookup(this);
    }

    [[nodiscard]]
    virtual UniquePtr<VariableExpression> replace(const String& name, BooleanExpression& exp) {
        if (this->name == name) {
            return std::make_unique<VariableExpression>(exp.copy());
        } else {
            return std::make_unique<VariableExpression>(name);
        }
    }

    [[nodiscard]]
    virtual UniquePtr<BooleanExpression> copy() const {
        return std::make_unique<BooleanExpression>(name);
    }

    VariableExpression(const VariableExpression&) = delete;
    VariableExpression& operator=(const VariableExpression&) = delete;
};

class AndExpression : public BooleanExpression {
private:
    UniquePtr<BooleanExpression> operand1;
    UniquePtr<BooleanExpression> operand2;
public:
    AndExpression(UniquePtr<BooleanExpression> op1, UniquePtr<BooleanExpression> op2):
        operand1{std::move(op1)}, operand{std::move(op2)} {}

    virtual ~AndExpression() = default;

    [[nodiscard]]
    virtual bool evaluate(Context& context) const {
        return operand1->evaluate(context) && operand2->evaluate(context);
    }

    [[nodiscard]]
    virtual UniquePtr<BooleanExpression> replace(const String& name, BooleanExpression& exp) const {
        return std::make_unique<AndExpression>(
            operand1->replace(name, exp),
            operand2->replace(name, exp)
        );
    }

    [[nodiscard]]
    virtual UniquePtr<BooleanExpression> copy() const {
        return std::make_unique<AndExpression>(operand1->copy(), operand2->copy());
    }

    AndExpression(const AndExpression&) = delete;
    AndExpression& operator=(const AndExpression&) = delete;
};

int main(int argc, char* argv[]) {
    UniquePtr<BooleanExpression> expression;
    Context context;
    UniquePtr<VariableExpression> x = std::make_unique<VariableExpression>("X");
    UniquePtr<VariableExpression> y = std::make_unique<VariableExpression>("Y");
    UniquePtr<BooleanExpression> expression; = std::make_unique<AndExpression>(x, y);

    context.assign(x.get(), false);
    context.assign(y.get(), true);
    bool result = expression->evaluate(context);
    std::println("{}", result);

    context.assign(x.get(), true);
    context.assign(y.get(), true);
    result = expression->evaluate(context);
    std::println("{}", result);
    
    return 0;  
}

```
 

The program output is:

 
```
0
1

```
 

## See also

 
- [Backus–Naur form](./Backus–Naur_form)
- [Combinatory logic in computing](./Combinator#Combinatory_logic_in_computing)
- *[Design Patterns](./Design_Patterns)*
- [Domain-specific language](./Domain-specific_language)
- [Interpreter (computing)](./Interpreter_(computing))

 

## References

 
1. [↑](./Interpreter_pattern#cite_ref-GoF_1-0) [Gamma, Erich](./Erich_Gamma); [Helm, Richard](./Richard_Helm); Johnson, Ralph; Vlissides, John (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](./Design_Patterns). Addison-Wesley. [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).
2. [↑](./Interpreter_pattern#cite_ref-GoF2_2-0) Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides (1994). [*Design Patterns: Elements of Reusable Object-Oriented Software*](https://archive.org/details/designpatternsel00gamm/page/243). Addison Wesley. pp. [243ff](https://archive.org/details/designpatternsel00gamm/page/243). [ISBN](./ISBN_(identifier)) [0-201-63361-2](./Special:BookSources/0-201-63361-2).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
3. [↑](./Interpreter_pattern#cite_ref-3) ["The Interpreter design pattern - Problem, Solution, and Applicability"](http://w3sdesign.com/?gr=b03&ugr=proble). *w3sDesign.com*. Retrieved 2017-08-12.
4. [↑](./Interpreter_pattern#cite_ref-4) ["The Interpreter design pattern - Structure and Collaboration"](http://w3sdesign.com/?gr=b03&ugr=struct). *w3sDesign.com*. Retrieved 2017-08-12.

 

## External links

   [![Wikibooks logo](//upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Wikibooks-logo.svg/40px-Wikibooks-logo.svg.png)](./File:Wikibooks-logo.svg) The Wikibook *[Computer Science Design Patterns](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns)* has a page on the topic of: ***[Interpreter](https://en.wikibooks.org/wiki/Computer%20Science%20Design%20Patterns/Interpreter)***  
- [Interpreter implementation](https://lukaszwrobel.pl/blog/interpreter-design-pattern) in [Ruby](./Ruby_(programming_language))
- [Interpreter implementation](https://github.com/jamesdhutton/Interpreter) in [C++](./C++)
- [SourceMaking tutorial](https://sourcemaking.com/design_patterns/interpreter)
- [Interpreter pattern description from the Portland Pattern Repository](http://c2.com/cgi/wiki?InterpreterPattern)

 
| vteSoftware design patterns |
| --- |
| Gang of Fourpatterns | CreationalAbstract factoryBuilderFactory methodPrototypeSingletonStructuralAdapterBridgeCompositeDecoratorFacadeFlyweightProxyBehavioralChain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor | Creational | Abstract factoryBuilderFactory methodPrototypeSingleton | Structural | AdapterBridgeCompositeDecoratorFacadeFlyweightProxy | Behavioral | Chain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor |
| Creational | Abstract factoryBuilderFactory methodPrototypeSingleton |
| Structural | AdapterBridgeCompositeDecoratorFacadeFlyweightProxy |
| Behavioral | Chain of responsibilityCommandInterpreterIteratorMediatorMementoObserverStateStrategyTemplate methodVisitor |
| Concurrencypatterns | Active objectBalkingBinding propertiesDouble-checked lockingEvent-based asynchronousGuarded suspensionJoinLockMonitorProactorReactorRead–write lockSchedulerScheduled-task patternSemaphoreThread poolThread-local storage |
| Architecturalpatterns | Front controllerInterceptorMVCMVPMVVMADRECSn-tierSpecificationPublish–subscribeNaked objectsService locatorActive recordIdentity mapData access object (DAO)Data transfer object (DTO)Inversion of controlModel 2Broker |
| Otherpatterns | BlackboardBusiness delegateComposite entityComposition over inheritanceDependency injectionGuard clauseIntercepting filterLazy loadingMock objectNull objectObject poolServantTwinType tunnelMethod chainingDelegation |
| Books | Design PatternsEnterprise Integration Patterns |
| People | Christopher AlexanderErich GammaRalph JohnsonJohn VlissidesGrady BoochKent BeckWard CunninghamMartin FowlerRobert MartinJim CoplienDouglas SchmidtLinda Rising |
| Communities | The Hillside GroupPortland Pattern Repository |
| See also | Anti-patternArchitectural pattern |
---
source: sources/wiki-Interpreter_pattern.md
source_url: https://en.wikipedia.org/wiki/Interpreter_pattern
---

## Interpreter Pattern — Evaluating Sentences in a Domain-Specific Language

The Interpreter pattern is a **behavioral design pattern** from the Gang of Four catalog that defines how to evaluate sentences in a language by mapping grammar rules to a class hierarchy. Each symbol (terminal or nonterminal) in a specialized language gets its own class, and a sentence is represented as an abstract syntax tree (AST) — an instance of the Composite pattern — which is traversed to interpret (evaluate) the sentence.

## Key Concepts

- **Purpose**: Evaluate sentences in a simple, domain-specific language by representing grammar rules as an object hierarchy
- **Classification**: Behavioral pattern (one of 23 GoF patterns)
- **Core abstraction**: An `Expression` class hierarchy where each class represents a grammar rule, with a shared `interpret(context)` operation
- **Terminal expressions**: Leaf nodes that interpret directly without delegating to children (e.g., variable lookups, literal values)
- **Nonterminal expressions**: Composite nodes that hold child expressions and forward interpretation requests recursively (e.g., `AndExpression` combining two sub-expressions)
- **Context object**: Carries global state needed during interpretation (e.g., variable bindings)
- **AST construction is out of scope**: The pattern describes evaluation, not parsing — the AST can be built manually by a client or automatically by a parser
- **The AST is an instance of the Composite pattern**: Nonterminal expressions compose child expressions recursively into a tree structure
- **Best suited for**: Simple, stable grammars where the language doesn't change frequently and efficiency is not the primary concern

## Commands and Syntax

**Structural participants:**
- `AbstractExpression` — declares `interpret(context)` interface
- `TerminalExpression` — implements interpret for terminal symbols (leaf nodes)
- `NonTerminalExpression` — maintains a collection of child `Expression` objects, forwards interpret calls downward
- `Context` — contains global information for the interpreter (e.g., variable-to-value mappings)
- `Client` — builds (or receives) the AST and invokes `interpret()`

**Typical method signatures:**
```
class BooleanExpression {
    virtual bool evaluate(Context&) = 0;
    virtual UniquePtr<BooleanExpression> replace(String&, BooleanExpression&) = 0;
    virtual UniquePtr<BooleanExpression> copy() const = 0;
};
```

**Common operations beyond interpret:**
- `replace(name, expression)` — substitutes a variable with another expression (supports symbolic manipulation)
- `copy()` — deep-copies the expression tree (needed since expressions are composed into trees)

## Relationships

- **Composite pattern**: The AST that Interpreter evaluates is structured as a Composite. Nonterminal expressions are composites; terminal expressions are leaves. Understanding Composite is a prerequisite.
- **Visitor pattern**: For complex grammars with many operations, Visitor can externalize the interpret behavior instead of embedding it in each expression class
- **Flyweight pattern**: Terminal expressions that appear many times in the AST can be shared using Flyweight
- **Iterator pattern**: Used to traverse the composite AST structure
- **Domain-Specific Languages (DSLs)**: Interpreter is the pattern-level realization of building a DSL evaluator
- **Backus-Naur Form (BNF)**: The grammar that Interpreter implements is typically described in BNF; each BNF production becomes an expression class
- **Parser**: Complements Interpreter by handling AST construction, which Interpreter deliberately omits

## Exam-Relevant Points

- Interpreter is a **behavioral** GoF pattern — know the classification
- The pattern maps **one class per grammar rule**, not one class per token or one class per sentence
- The AST is an instance of **Composite** — this connection is frequently tested
- Interpreter does **not** describe how to parse or build the AST; it only describes evaluation
- Best applied to **simple, relatively stable grammars** (e.g., search expressions, boolean logic, simple query languages like SQL subsets)
- The `Context` object is essential — it carries state across the interpretation (variable bindings, environment)
- **Problem it solves**: Avoids hard-wiring expressions directly into classes, which makes adding or changing expressions impossible without modifying the class
- **Trade-off**: For complex grammars, the class hierarchy becomes unwieldy — at that point, parser generators or the Visitor pattern are more appropriate
- Common **real-world uses**: SQL query languages, communication protocol description languages, regular expressions, embedded DSLs
- Terminal expressions interpret **directly**; nonterminal expressions **delegate** to children — know the distinction

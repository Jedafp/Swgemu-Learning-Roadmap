Programming Roadmap: Beginner → Lua → C++ → SWGEmu Developer

This roadmap assumes zero programming experience. The end goal is to become capable of independently reading, modifying, debugging, extending, and maintaining the C++/Lua SWGEmu codebase.

You do not need to learn everything before touching SWGEmu. You'll gradually introduce the codebase as your skills improve.

Overview
Phase	Learn	Approx. Time
1	Programming fundamentals with Lua	1–2 months
2	Intermediate Lua	1–2 months
3	Lua projects	1 month
4	C++ fundamentals	3–4 months
5	Intermediate C++	3–4 months
6	Advanced/practical C++	3–6 months
7	Git + Linux + build tools	Alongside everything
8	SQL/databases	1–2 months
9	Networking	2–3 months
10	Concurrency	1–2 months
11	Debugging/profiling	Ongoing
12	Lua/C++ integration	1 month
13	SWGEmu/Core3 study	6–12+ months
14	Independent development	Ongoing

Don't take those times as requirements. With a large existing C++ project, code-reading and debugging ability matter more than finishing courses quickly.

Phase 1 — Learn Programming Through Lua

Goal: Learn how programming works without simultaneously fighting C++ complexity.

Start here rather than taking a separate programming language first.

Learn:

Programs and source code
Variables
Numbers
Strings
Booleans
nil

Arithmetic
Comparison operators
Logical operators

if
elseif
else

for loops
while loops
repeat/until

Functions
Parameters
Return values

Local/global scope

Tables
Arrays
Key/value tables

pairs()
ipairs()

String manipulation
Basic file I/O
Modules
Error handling
Free resources

Your main course:

Programming in Lua — Free Online Book

Use the official manual as a reference:

Lua Documentation

Practice here:

Exercism Lua Track

Another useful resource:

Learn Lua in Y Minutes

Don't just read tutorials

For approximately every hour you spend learning, try to spend another hour programming.

Build small programs such as:

Calculator
Number guessing game
Unit converter
Character creator
Inventory list
Random item generator
Experience calculator
Damage calculator
Simple combat simulator
Milestone

You should be able to open an unfamiliar 100–200 line Lua program and roughly explain what it does.

Then continue.

Phase 2 — Intermediate Lua

Goal: Become comfortable enough with Lua to work with larger scripted systems.

Learn:

Nested tables
Functions stored in tables
Higher-order functions
Anonymous functions
Closures

Modules
require()

Multiple return values
Variable arguments

Metatables
Metamethods

Object-like Lua patterns

Iterators

Error handling
pcall()
assert()
error()

File organization
Data-driven programming

Spend extra time on tables.

You should become extremely comfortable with structures like:

player = {
    name = "PlayerOne",
    level = 20,

    inventory = {
        {name = "Item A", quantity = 5},
        {name = "Item B", quantity = 2}
    }
}

And writing functions that search, modify, add and remove data from those structures.

Phase 3 — Build a Larger Lua Project

Goal: Stop thinking like a tutorial student.

Build a text-based game simulation.

Don't worry about graphics.

Implement:

Player
NPC
Creature
Inventory
Items
Weapons
Armor
Health
Combat
Skills
Experience
Loot
Currency
Vendors
Crafting
Resources
Saving/loading

Split it into multiple files.

For example:

project/
│
├── main.lua
├── player.lua
├── creature.lua
├── combat.lua
├── inventory.lua
├── items.lua
├── crafting.lua
└── save.lua

This teaches something extremely important for SWGEmu:

working across multiple source files.

Lua milestone

Before making C++ your main focus, you should be able to:

write functions without following tutorials;
design tables yourself;
split programs into modules;
debug your own mistakes;
read someone else's Lua;
search a project to determine where something happens;
modify an existing Lua program without rewriting it.

You don't need to master Lua before proceeding.

Phase 4 — Start C++

Now make C++ your primary language.

Your main free C++ course should be:

LearnCpp.com

For your goal, I recommend going through essentially the entire LearnCpp curriculum rather than just completing the beginner chapters.

Use this as your reference:

cppreference

Practice:

Exercism C++ Track

Phase 5 — C++ Fundamentals

Learn these thoroughly:

Compilation
Compiler
Linker

Variables
Fundamental data types
Operators

Functions
Parameters
Return values

Scope
Namespaces

if/else
switch

for
while

Arrays
std::array
std::vector

std::string

References
Pointers

const

struct
enum
enum class

Header files
Source files

Classes
Objects

Constructors
Destructors

Don't rush pointers and references.

They will matter enormously later.

You should understand differences like:

Player player;
Player* player;
Player& player;
const Player& player;

You don't need to memorize everything, but those declarations shouldn't look mysterious.

Phase 6 — Object-Oriented C++

Now learn:

Classes
Encapsulation
Constructors
Destructors

Inheritance

Base classes
Derived classes

Virtual functions
override

Abstract classes

Polymorphism

Composition

Static members

Operator overloading

Create structures such as:

GameObject
    │
    ├── Creature
    │      │
    │      ├── Player
    │      └── NPC
    │
    └── Item
           │
           ├── Weapon
           └── Armor

Don't try to reproduce SWGEmu architecture.

You're simply practicing C++ architecture.

Phase 7 — C++ Memory Management

This is one of the most important phases.

Learn:

Stack
Heap

Memory allocation
Object lifetime

Pointers
References

nullptr

new/delete

Dangling pointers

Memory leaks

RAII

std::unique_ptr
std::shared_ptr
std::weak_ptr

Copy constructors
Copy assignment

Move constructors
Move assignment

Move semantics

Modern C++ should generally avoid manually scattering new and delete throughout programs, but you still need to understand them because you're working with an established codebase.

Spend significant time understanding:

Who owns this object?

How long does this object exist?

Those questions become extremely important in server software.

Phase 8 — Standard Library + Data Structures

Become comfortable with:

std::vector
std::array
std::string

std::map
std::unordered_map

std::set
std::unordered_set

std::queue
std::deque

std::pair
std::tuple

Iterators

Algorithms

std::sort
std::find

Then learn basic computer-science data structures:

Arrays
Linked lists
Stacks
Queues
Hash tables
Trees
Graphs

And understand basic Big-O:

O(1)
O(log n)
O(n)
O(n log n)
O(n²)

You don't need months of LeetCode.

Your objective is understanding why one solution becomes expensive when thousands or millions of objects are involved.

Phase 9 — Git

Start this much earlier than Phase 9. Once you're writing programs, start using Git.

Free complete resource:

Pro Git Book

Learn:

git clone
git status
git add
git commit

git diff
git log

git branch
git switch

git merge

git pull
git push

git restore
git revert

git stash

.gitignore

Later learn:

merge conflicts
rebase
bisect
tags

For every meaningful project:

Make change
     ↓
Test
     ↓
Commit
     ↓
Next change

This becomes critical when modifying a huge existing project.

Phase 10 — Linux Development Skills

Learn enough Linux command-line usage that navigating a source tree becomes effortless.

Learn:

pwd
ls
cd

mkdir
touch

cp
mv
rm

cat
less

head
tail

grep
find

chmod

ps
top

kill

pipes
redirection
environment variables

Spend extra time on:

grep
find

Eventually you'll constantly ask questions like:

Where is SomeFunction() defined?

or:

Which files reference this class?

Fast code searching is one of the most useful skills you can develop.

Phase 11 — CMake and Compilation

Learn how C++ actually becomes an executable.

Understand:

Source files
Headers

Preprocessor
Compiler
Linker

Object files
Libraries

Static libraries
Shared libraries

Debug builds
Release builds

Compiler warnings
Dependencies

Then learn basic CMake.

Free official tutorial:

CMake Tutorial

Learn:

CMakeLists.txt

cmake
cmake --build

Targets
Libraries
Dependencies
Include directories
Build directories

You don't need to become a CMake specialist.

You need to understand enough that the build system isn't magic.

Phase 12 — Debugging

This deserves its own phase.

Learn GDB.

Free official documentation:

GDB Documentation

Learn:

break
run
continue

next
step

print

watch

backtrace

frame

info locals
info threads

Eventually you want to be able to:

Start server under debugger
        ↓
Set breakpoint
        ↓
Perform action
        ↓
Breakpoint triggers
        ↓
Inspect variables
        ↓
Step through code
        ↓
Understand execution path

That ability will be enormously useful for learning an unfamiliar codebase.

Also learn Valgrind:

Valgrind Quick Start Guide

And later learn compiler sanitizers:

AddressSanitizer
UndefinedBehaviorSanitizer
ThreadSanitizer
Phase 13 — SQL and Databases

Start with:

SQLBolt

Learn:

Database
Table
Row
Column

Primary key
Foreign key

SELECT
INSERT
UPDATE
DELETE

WHERE

ORDER BY

GROUP BY

JOIN

Indexes

Constraints

Transactions

Normalization

Then learn MariaDB:

MariaDB Documentation

Take your C++ project and add persistence:

Create character
       ↓
Store character
       ↓
Exit program

Restart
       ↓
Load character
       ↓
Character still exists

Then save:

Inventory
Items
Currency
Skills
Character state

Now you're getting much closer to server-development concepts.

Phase 14 — Networking

This is where you transition from general C++ programming toward server programming.

Use:

Beej's Guide to Network Programming

Learn:

Client/server architecture

IP addresses

Ports

Sockets

TCP

UDP

Packets

Connections

Latency

Serialization

Protocols

Build projects in this order:

Echo server
    ↓
TCP chat server
    ↓
Multi-client chat server
    ↓
Login server
    ↓
Simple multiplayer server

Don't add graphics.

Terminal clients are enough.

Phase 15 — Multithreading and Concurrency

Now learn:

Processes
Threads

std::thread

Race conditions

Mutexes
std::mutex

Locks

Deadlocks

Atomics

Condition variables

Thread-safe queues

Thread pools

Understand situations such as:

Thread 1
Player changes inventory

Thread 2
Player data saves

Thread 3
Another system accesses inventory

What happens when those operations occur simultaneously?

This becomes extremely important in server development.

Phase 16 — Advanced Practical C++

Return to LearnCpp and cppreference as necessary.

Learn more about:

Templates

Lambdas

STL algorithms

Move semantics

RAII

Smart pointers

Object lifetime

Exception safety

Concurrency

Memory layout

Undefined behavior

Performance

Cache locality

Profiling

Don't interpret "advanced C++" as:

Memorize every feature C++ has.

The target is:

Open complicated unfamiliar C++ and figure out what it's doing.

That's a much more useful skill.

Phase 17 — Learn How C++ and Lua Work Together

Now your original Lua work becomes especially useful.

Study the Lua C API:

Lua Documentation

Understand this relationship:

             C++ SERVER
                 │
                 │
          creates Lua state
                 │
                 ▼
             LUA SCRIPT
                 │
        executes functions
                 │
                 ▼
             C++ SERVER

Learn concepts such as:

Lua state

Lua stack

Loading scripts

Executing Lua functions

Passing C++ values → Lua

Passing Lua values → C++

Exposing C++ functions to Lua

Error handling

userdata

Bindings

Make a tiny C++ program that embeds Lua.

For example:

C++:

Create game character
Load Lua configuration
Ask Lua for character settings
Apply them in C++

This miniature project will make mixed Lua/C++ architecture much easier to understand.

Phase 18 — Begin Studying SWGEmu/Core3

Now transition heavily into the real codebase.

SWGEmu Core3 GitHub Repository

Also become familiar with:

SWGEmu Engine3 GitHub Repository

Do not attempt to read the repositories from beginning to end.

You'll drown in code.

Instead:

Choose ONE feature
        ↓
Find relevant files
        ↓
Find relevant Lua
        ↓
Find relevant C++
        ↓
Search references
        ↓
Set breakpoints
        ↓
Perform action
        ↓
Observe execution
        ↓
Change something tiny
        ↓
Compile
        ↓
Test
        ↓
Git commit

Repeat this hundreds of times.

Phase 19 — Your SWGEmu Modification Ladder

Don't immediately start rewriting major systems.

Level 1 — Data changes

Make simple changes:

Creature values
Item values
XP values
Loot values
NPC values
Skill values
Configuration values
Level 2 — Lua changes

Modify existing scripted behaviors.

Then add small scripted functionality yourself.

Level 3 — Simple C++ changes

Find a straightforward existing behavior and modify it.

Compile.

Test.

Debug.

Level 4 — Add small C++ features

Create a genuinely new but small behavior.

Learn how your feature interacts with existing classes.

Level 5 — Cross-system features

Build something requiring:

C++
+
Lua
+
database
+
existing gameplay systems
Level 6 — Major systems

Only after you've accumulated considerable Core3 experience should you start altering large foundational systems.

Phase 20 — Learn Software Architecture by Studying Core3

At this point, the source code itself becomes one of your primary textbooks.

Pick a concept:

Player
NPC
Creature
Item
Inventory
Combat
Skills
Movement
Persistence
Networking
World
Guild
City
Crafting
Resources

Then trace it.

Create personal notes:

PLAYER SYSTEM

Important classes:
------------------
...

Important Lua:
--------------
...

Important functions:
--------------------
...

Database interaction:
---------------------
...

Related systems:
----------------
...

Execution path:
---------------
...

Eventually you'll build your own private documentation of the codebase.

That documentation could become one of your most valuable development resources.

Phase 21 — Learn Testing

Once your modifications become significant, you need repeatable testing.

Learn:

Unit tests
Integration tests
Regression tests
Assertions
Test fixtures
Mocks
Automated testing

For every bug:

Discover bug
     ↓
Understand bug
     ↓
Create reproducible test
     ↓
Fix bug
     ↓
Verify test passes
     ↓
Commit

The bigger your fork becomes, the more important regression testing becomes.

Phase 22 — Performance and Profiling

Don't optimize everything prematurely.

But eventually learn:

CPU profiling

Memory profiling

Memory leaks

Database bottlenecks

Lock contention

Network bottlenecks

Algorithmic complexity

Allocations

Cache behavior

The basic process should always be:

Server is slow
      ↓
MEASURE
      ↓
Find bottleneck
      ↓
Understand bottleneck
      ↓
Change implementation
      ↓
Measure again

Never:

Server is slow
      ↓
Guess
      ↓
Rewrite everything
Your Main Learning Path

If you want one simple sequence to follow, this is it:

START
 │
 ▼
Lua fundamentals
 │
 ▼
Intermediate Lua
 │
 ▼
Build Lua RPG simulation
 │
 ▼
C++ fundamentals
 │
 ▼
Classes/OOP
 │
 ▼
Pointers + references
 │
 ▼
Memory + RAII
 │
 ▼
STL + data structures
 │
 ▼
Build C++ RPG simulation
 │
 ▼
Git
 │
 ▼
Linux development
 │
 ▼
CMake/build systems
 │
 ▼
GDB/debugging
 │
 ▼
SQL/MariaDB
 │
 ▼
Add persistence to C++ project
 │
 ▼
Networking
 │
 ▼
Build multiplayer C++ server
 │
 ▼
Concurrency
 │
 ▼
Advanced practical C++
 │
 ▼
Lua/C++ integration
 │
 ▼
Build C++ program embedding Lua
 │
 ▼
SWGEmu/Core3
 │
 ▼
Small Lua modifications
 │
 ▼
Small C++ modifications
 │
 ▼
New small features
 │
 ▼
Cross-system features
 │
 ▼
Major systems
 │
 ▼
Independent SWGEmu development
The free-resource stack I'd use

You don't need dozens of overlapping courses. These can carry most of the roadmap:

Lua: Programming in Lua
Lua practice: Exercism Lua
Lua reference: Official Lua Documentation
C++: LearnCpp
C++ practice: Exercism C++
C++ reference: cppreference
Git: Pro Git
CMake: Official CMake Tutorial
SQL: SQLBolt
Database: MariaDB Documentation
Networking: Beej's Guide to Network Programming
Debugging: GDB Documentation
Memory debugging: Valgrind Documentation
Real-world code study: SWGEmu Core3
Engine study: SWGEmu Engine3
The biggest rule

Don't spend two years doing tutorials before touching Core3.

A better progression is:

First few months: mostly tutorials → later: 70% learning / 30% projects → intermediate: 50% learning / 50% projects → advanced: 20% tutorials / 80% Core3.

Eventually, Core3 itself becomes the course.

And because you're working toward an existing C++/Lua codebase rather than creating an entire engine and emulator from zero, your most important long-term ability isn't knowing every C++ feature. It's being able to find unfamiliar code, understand it, trace it with a debugger, modify it safely, test it, and move on to the next subsystem.

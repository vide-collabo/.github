# The Vide Collaboration Space

Vide provides layers of abstraction for applications based on the principle of state-aware pure function composition, which target JavaScript or dotnet based runtimes using F#.

The principle fits well to all applications that are based on computations that require cyclic / multiple evaluations, where a computation is made up of pure functions that can retain their own local state from one evaluation to the next. It is thus well suited for various domains like digital signal processing, stream analysis and rule engines, reactive frontends, game engines, discrete simulation, and more.

Unlike the **state monad**, which allows for transforming a **_global state_** through a computation, Vide is based on the idea that a function in a computation retains it's own **_local state_** between evaluations cycles. While this first seems to require objects (and the associated delocalization of instanciation and usage), Vide lets you compose state-aware functions in a way that's almost as easy as composing pure functions.

## Repos

Currently, there are 2 repos, which might be split up in the future:

* Vide.docs: The single-doc repo 

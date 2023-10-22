# The Vide Collaboration Space

Vide provides layers of abstraction for applications based on the principle of state-aware pure function composition, which target JavaScript or dotnet based runtimes.

The principle fits well to all applications that are based on computations that require cyclic / multiple evaluations, where a computation is made up of pure functions that can retain their own local state from one evaluation to the next. It is thus well suited for various domains like digital signal processing, stream analysis and rule engines, reactive frontends, game engines, discrete simulation, and more.

Unlike the **state monad**, which allows for transforming a **_global state_** through a computation, Vide is based on the idea that a function in a computation retains it's own **_local state_** between evaluations cycles. While this first seems to require objects (and the associated delocalization of instanciation and usage), Vide lets you compose state-aware functions in a way that's almost as easy as composing pure functions.

## Collaboration

There's a lot to do! There are many low-hanging fruits in the current implementations, as well as opportunities for implementing completely new stuff based on Vide:

### Improve current Vide implementations

* Implement demo- and showcasing apps for Vide Fable and Vide Avalonia.
* Improve Vide DSP with signal processing low- and high level building blocks such as filters, phasers, reverbs or synthesis elements
* Restart the Vide MAUI implementation (which is basically the thing for Avalonia, but with another API generator)
* Improve the "docs" repo (I guess there's not so much to do; it's the famous last 20%)

### New Vide implementations

Are you interested in making something new? Here are some ideas:

* "Persistable and Rsumable Computations" (which would be some kind of "Vide Workflow" thing). A PoC implementation would be quite easy and straight-forward.
* Rethink the idea of [https://github.com/fsprojects/LocSta](https://github.com/fsprojects/LocSta) and take it back into Vide.
* Implement a react-like "Vide Unity" or "Vide Stride" API
* A react-like "Vide Terminal" for text mode UIs
* A "Vide UI" thing that targets a low-level rendering API like Skia and implement layout, styling, animations, etc. on top of that.

## Repos

Currently, there are 2 repos, which might be split up in the future:

### Vide.docs

  The repo that contains sources for the Vide docu site. The content is auto-built and deployed to: https://vide-dev.io

### Vide

The monorepo that currently contains all Vide implementations, independent of the layer of abstraction or the targeting domain or technology.

All artefacts are available as NuGet package for either dotnet or Fable.

**Vide.Common**

* Vide.Common

  Base functions for all libraries and applications
  
* Vide.Common.DSP

  Building blocks for using Vide in the domain of digital signal processing
  
* Vide.Common.UI

  CE builders that allow for building an API supporting several content models.
  This is used currently for the Vide.Fable and Vide.Avalonia implementations.
    
**Vide.Audio**

Vide.Audio builds upon Vide.Common.DSP, and provides playback functionalities and further functions for generating or modifying sample-exact streams or control-rate signals.

**Vide.UI**

* Vide.UI.Fable

  A Fable library, solely based on Vide.Common for building reactive web frontends.

* Vide.UI.Avalonia

  A dotnet library, solely based on Vide.Common for building reactive mobile or desktop apps, based on Avalonia.

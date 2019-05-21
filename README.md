# noise

This is forked from [`cmaher/noise`](https://github.com/cmaher/noise) for
packaging reasons. I had trouble using `cmaher/noise` in a `deps.edn` project
because it has both Java and Clojure sources, and I couldn't find a good
solution to using Java sources in a `deps.edn` project, at least not easily.

After considering runtime compilation, I decided to simply commit the compiled
class file to source control and distributed it with the source.

``` shell
javac src/org/kdotjpg/noise/OpenSimplexNoise.java
```

This package isn't published to any maven repositories, but you can use it by
cloning it and using local require:

``` edn
noise {:local/root "../path/to/noise"}
```

Or using a git coordinate:

``` edn
github-atamis/noise {:git/url "https://github.com/atamis/noise.git"
                     :sha "<latest sha1>"}
```

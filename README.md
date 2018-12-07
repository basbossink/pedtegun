# pedtegun

**The description below is as of yet a vision, the code for this
project still has to be written. 😊**

This command line application tries to answer
[NuGet](https://www.nuget.org/ "NuGet") related questions .NET
developers have that maintain packages within a single code-base.

## Indexing

pedtegun uses a self contained index to be able to quickly answer
questions about your dependencies. pedtegun can index based on all
project files it can find from a single root directory and by parsing
nuspec files in the NuGet package cache.

To create an index use:

```sh
$ pedtegun index sourceRootDir
```

## Showing dependencies

### Recursive dependencies

pedtegun can show you the recursive dependencies of a project by
moving into the project directory and typing the following command:

```sh
$ pedtegun tree
```

If you prefer output in the form of a [dot](https://www.graphviz.org/)
file that can be turned into a nice graphical representation use:

```sh
$ pedtegun tree --dot
```

### Inverse dependencies

pedtegun can also show you which projects/packages depend (directly or
indirectly) on a particular package or project.

```sh
$ pedtegun eert Example.Package.Id
```

This will show you all the projects that are not dependent on by any
other project that have a dependency on `Example.Package.Id`.

You can also show the _unique_ paths in all dependency trees that
contain `Example.Package.Id` using:

```sh
$ pedtegun eert --paths Example.Package.Id
```

Or in a graphical tree:

```sh
$ pedtegun eert --dot Example.Package.Id
```

----
### License

Copyright &copy; Bas Bossink 2018. This project is licensed under the
BSD-2-Clause license also known as the "Simplified BSD License" and the
"FreeBSD License". See the [LICENSE](LICENSE "License") for details.

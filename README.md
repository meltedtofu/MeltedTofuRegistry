# MeltedTofuRegistry

This registry allows you to use packages from MeltedTofu in Julia 1.x.

## Usage
If you are using at least Julia 1.1, then you can add this registry with

`]registry add https://github.com/meltedtofu/MeltedTofuRegistry.git`

(The `]` enters Pkg mode when you type it at the REPL prompt, see [https://docs.julialang.org/en/v1/stdlib/Pkg/](https://docs.julialang.org/en/v1/stdlib/Pkg/).)

Then we can use unregistered public packages (or private packages) as if they are registered ones.

## Registering your package with MeltedTofuRegistry

Add the [LocalRegistry.jl](https://github.com/GunnarFarneback/LocalRegistry.jl) package to your environment. Then:

* Navigate to MeltedTofuRegistry, which for me is at `~/.julia/registries/MeltedTofuRegistry`.
* Update to the latest `main` branch.
* check out a new branch, e.g., `git checkout -b SomeNewPkg`
* Switch to your package directory.
* start Julia and enter the following:
```
using LocalRegistry, SomeNewPkg
register(SomeNewPkg, "~/.julia/registries/MeltedTofuRegistry")
```
where you replace the specific package name and path with the appropriate value on your computer.

This will add a new commit to the branch of MeltedTofuRegistry you just created.

* Submit the branch as a PR to MeltedTofuRegistry

## See also
* Creating a registry : [https://discourse.julialang.org/t/creating-a-registry/12094](https://discourse.julialang.org/t/creating-a-registry/12094)

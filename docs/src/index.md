# Bukdu 🌌

Bukdu 🌌 is a web development framework for Julia (https://julialang.org).

It's influenced by Phoenix framework (http://phoenixframework.org).

```julia
using Bukdu

struct WelcomeController <: ApplicationController
    conn::Conn
end

function index(c::WelcomeController)
    render(JSON, "Hello World")
end

routes() do
    get("/", WelcomeController, index)
end

Bukdu.start(8080)
```


### RESTful API Demo

Visit [Bukdu on Heroku](https://sevenstars.herokuapp.com)
and check its [source code](https://github.com/wookay/heroku-sevenstars).
(A sleeping heroku page, it will become active again after a short delay.)


### Modifying actions at runtime

```sh
Bukdu/examples $ julia -i welcome.jl
               _
   _       _ _(_)_     |  A fresh approach to technical computing
  (_)     | (_) (_)    |  Documentation: https://docs.julialang.org
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 0.7.0-beta.3 (2018-06-24 10:12 UTC)
 _/ |\__'_|_|_|\__'_|  |  Commit c4d24e60f1* (0 days old master)
|__/                   |  x86_64-apple-darwin17.4.0

INFO: Bukdu Listening on: 127.0.0.1:8080
julia> function index(c::WelcomeController)
           render(JSON, "Love")
       end
index (generic function with 1 method)
```
That's it! Refresh your page of the web browser.


### Requirements

The project has reworked based on [HTTP.jl](https://github.com/JuliaWeb/HTTP.jl) in [Julia 0.7 beta](https://julialang.org/downloads/nightlies.html).

`julia>` type `]` key

```julia
(v0.7) pkg> add HTTP#master
(v0.7) pkg> add https://github.com/wookay/Bukdu.jl.git#master
```

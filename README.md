[![JuliaFEMLogo](https://github.com/JuliaFEM/JuliaFEM.jl/blob/master/docs/logo/JuliaFEMLogo_128x128.png)](http://www.juliafem.org)

# Miniball.jl is a part of JuliaFEM

.. image:: https://travis-ci.org/JuliaFEM/Miniball.jl.svg?branch=master
  :target: https://travis-ci.org/JuliaFEM/Miniball.jl

Julia package for a smallest enclosing sphere for points in arbitrary dimensions. Implementation is based on the Bernd Gärtner's C++ miniball (https://www.inf.ethz.ch/personal/gaertner/miniball.html). Presented implementation is pure Julia code, does not have any depencies and has the same speed as the C++ implementation. The original C++ implementation is licensed under [GNU General Public License (GPLv3)](http://www.gnu.org/copyleft/gpl.html), which is why this implementation also has the same license.

## Some examples of the usage

```julia
julia> using Miniball

julia> ball = miniball([1.0 0.0; 0.0 1.0])

julia> ball.center
[0.5,0.5]

julia> ball.squared_radius
0.5

julia> ball = miniball([-1.0 0.0; 1.0 0.0; 0.0 1.0; 0.0 -1.0])

julia> ball.center
([0.0,0.0],1.0)

julia> ball.squared_radius
1.0

julia> ball = miniball(rand(1000000,3))

julia> ball.center
 [0.502234, 0.495934, 0.504458]

julia> ball.squared_center
0.7283212748080066

```
Here is the original Miniball documentation http://www-oldurls.inf.ethz.ch/personal/gaertner/miniball.html

[![Miniball log](http://www-oldurls.inf.ethz.ch/personal/gaertner/miniball/mb.gif)](http://www-oldurls.inf.ethz.ch/personal/gaertner/miniball.html)

Miniball.jl also has a C++ implementation wrapped using [Cxx.jl](https://github.com/Keno/Cxx.jl), see source [cxx_miniball.jl](https://github.com/JuliaFEM/Miniball.jl/blob/master/src/cxx_miniball.jl).

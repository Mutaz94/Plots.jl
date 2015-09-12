### Lines

A simple line plot of the 3 columns.

```julia
plot(rand(100,3))
```

![](../img/unicodeplots_example_1.png)

### Functions

Plot multiple functions.

```julia
plot(0:0.01:4π,[sin,cos])
```

![](../img/unicodeplots_example_2.png)

### 

You can also call it with (xmin, xmax).

```julia
plot([sin,cos],0,4π)
```

![](../img/unicodeplots_example_3.png)

### Global

Change the guides/background without a separate call.

```julia
plot(rand(10); title="TITLE",xlabel="XLABEL",ylabel="YLABEL",background_color=RGB(0.5,0.5,0.5))
```

![](../img/unicodeplots_example_4.png)

### Two-axis

Use the `axis` or `axiss` arguments.

Note: This is only supported with Qwt right now

```julia
plot(Vector[randn(100),randn(100) * 100]; axiss=[:left,:right])
```

![](../img/unicodeplots_example_5.png)

### Vectors w/ pluralized args

Plot multiple series with different numbers of points.  Mix arguments that apply to all series (singular... see `marker`) with arguments unique to each series (pluralized... see `colors`).

```julia
plot(Vector[rand(10),rand(20)]; marker=:ellipse,markersize=8,colors=[:red,:blue])
```

![](../img/unicodeplots_example_6.png)

### Build plot in pieces

Start with a base plot...

```julia
plot(rand(100) / 3; reg=true,fillto=0)
```

![](../img/unicodeplots_example_7.png)

### 

and add to it later.

```julia
scatter!(rand(100); markersize=6,color=:blue)
```

![](../img/unicodeplots_example_8.png)

### Lots of line types

Options: (:line, :step, :stepinverted, :sticks, :dots, :none, :heatmap, :hexbin, :hist, :bar)  
Note: some may not work with all backends

```julia
plot(rand(20,4); linetypes=[:line,:step,:sticks,:dots])
```

![](../img/unicodeplots_example_10.png)

### Bar

x is the midpoint of the bar. (todo: allow passing of edges instead of midpoints)

```julia
bar(randn(1000))
```

![](../img/unicodeplots_example_11.png)

### Histogram

note: fillto isn't supported on all backends

```julia
histogram(randn(1000); nbins=50,fillto=20)
```

![](../img/unicodeplots_example_12.png)

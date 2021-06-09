---
layout: page
title: ABC
description: absorbing boundary conditions for the convected Helmholtz equation
img: /assets/img/fig_abc.png
importance: 2
category: "Numerical methods for harmonic wave problems with convection"
---

Many wave propagation problems are set in unbounded domain.
To perform numerical simulations, it is required to truncate this domain to obtain a finite computational region that can be handled by computers.

The two most popular domain truncation techniques are
- **Perfectly Matched Layers** (PML): a layer of absorbing material is added oustid the domain of interest, here *perfectly matched* means that no reflection should appear at the interface between the physical domain and absorbing layer,
- **Absorbing Boundary Conditions** (ABC): the physical domain is surrounded by an *artificial boundary* on which a non-reflecting boundary conditions is enforced, when the dimension of the domain is greater than one, exact ABCs are non-local and devising local approximation of those ABCs is a challenging problem.


For the *convected Helmholtz equation*, stable PMLs have been devised, but they are difficult to use with numerical methods belonging to the family of mixed finite-elements, such has *Hybridizable Discontinuous Galerkin* (HDG) methods.


In this work, we introduce a simple way to construct ABCs for the convected Helmholtz equation from the ABCs formerly derived for the standard Helmholtz equation.
This leads to local ABCs that are efficient and easy to implement.

As for the derivation of stable PMLs for the convected Helmholtz equation, the main tool of this work is the *Prandtl-Glauert-Lorentz transformation* which transforms the convected Helmholtz equation to the standard Helmholtz equation.

### Some numerical results
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p_abc_M6e-1.png' | relative_url }}" alt="" title="res 1" />
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/p_abc_interf.png' | relative_url }}" alt="" title="res 2" />
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/conv_helm_pot_abc.png' | relative_url }}" alt="" title="res 3" />
    </div>
</div>
<div class="caption">
Some numerical results obtained with the HDG method. Left, point source in a uniform flow. Middle, interferences between two point sources. Right, point source in a potential flow around a circular obstacle (in black).
</div>

<!--
Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
```
--> 

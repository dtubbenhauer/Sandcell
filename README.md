# Sandwich cellularity and a version of cell theory

This page collects all code that is relevant for the calculations in the paper with the name of this section, see [click](https://arxiv.org/abs/2206.06678) with its home here [click](https://www.dtubbenhauer.com/sandcell.html). We also give a few explanation of how to run the code.

There are three different computer-based calculations that were done in that paper:

* Kazhdan–Lusztig (KL for short) combinatorics of dihedral groups, relevant for Section 2.
* GAP computations of cells, relevant for Section 4.
* Mathematica computation for Gram matrices, relevant for Section 4.

We will discuss all three of these seperately.

# Dihedral combintorics

The main underlying tool for computations, even beyond dihedral type, is du Cloux's Coxeter program: [click](http://math.univ-lyon1.fr/~ducloux/coxeter/coxeter3/english/coxeter3_e.html). A guide how to run the program can be found on that page.

This amazing piece of work can do a lot of computations related to Coxeter groups, e.g. after starting the program type

```python
   help
```

and you get all relevant commands:

![Coxeter](https://github.com/dtubbenhauer/Sandcell/blob/main/coxeter.png)

Now, let us get started. Type

```python
   type
   I
   6
```

which starts type $I_2(6)$ - the dihedral group of the 6-gon.

Enter

```python
   cprod
   1212
   21212
```

which computes the product of the KL elements $b_{1212}$ and $b_{21212}$. The ouput is $(v)c(12)+(v^3+2v)c(121212)$ (the program uses c for the KL elements), which says $b_{1212}b_{21212}=(v+v^{-1})b_{12}+(v^3+2v+2v^{-1}+v^{-3})b_{121212}$.

Note hereby the symmetry $v\leftrightarrow v^{-1}$, and the program only gives the nonnegative powers.

All calculations in Section 3 of the paper can be verified using similar calculations.

# Cell combintorics

To do

# Gram matrix combintorics

This part is a bit messy, my apologies, and I never found the time to clean it. I attached the files in a .zip, so feel free to play with them.

# Contact

If there are any questions, then please feel free to contact me: dtubbenhauer@gmail.com

Have fun playing with the code!

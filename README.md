# Sandwich cellularity and a version of cell theory

This page collects all code that is relevant for the calculations in the paper with the name of this section, see [click](https://arxiv.org/abs/2206.06678) with its home here [click](https://www.dtubbenhauer.com/sandcell.html). We also give a few explanation of how to run the code.

There are three different computer-based calculations that were done in that paper:

* Kazhdan–Lusztig (KL for short) combinatorics of dihedral groups, relevant for Section 2.
* GAP computations of cells, relevant for Section 4.
* Mathematica computation for Gram matrices, relevant for Section 4.

We will discuss all three of these seperately.

# Dihedral combinatorics

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

# Cell combinatorics

This part is based on GAP [click](https://www.gap-system.org/) in particular the semigroup package [click](https://www.gap-system.org/Packages/semigroups.html). The manual can be found here [click](https://docs.gap-system.org/pkg/semigroups/doc/manual.pdf).

After installing GAP start it and run

```python
   LoadPackage("semigroups");
   S := FullTransformationMonoid(5);
   DotString(S);
   FileString("t5.dot", DotString(S)); 
```

This creates a dot string diagram of the cells for the full transformation monoid on 5 strands. To convert a dot string diagram to a svg use

```python
   dot -Tsvg t5.dot -Tsvg -o t5.svg
```

in the terminal if you are a unix user. Otherwise, use for example an online converter to get your favorit picture file.

You will get the following picture:

![T5cells](https://github.com/dtubbenhauer/Sandcell/blob/main/t5.png)

Compared to the conventions of the paper, these are flipped top-to-bottom, so that the 1-1 cell is the bottom cell in the paper.

All cell calculations in the picture can be verified similarly. We refer to the documentation of the semigroup package for all the relevant commands one can use.

# Gram matrix combinatorics

This part is a bit messy, my apologies, and I never found the time to clean it. I attached the files in a .zip, so feel free to play with them.

# Contact

If there are any questions, then please feel free to contact me: dtubbenhauer@gmail.com

Have fun playing with the code!

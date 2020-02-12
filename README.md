# STFR-MWF
This repository contains code
for reproducing the results in the paper:

Steven T. Whitaker, Gopal Nataraj, Jon-Fredrik Nielsen, and Jeffrey A. Fessler \
Myelin Water Fraction Estimation Using Small-Tip Fast Recovery MRI \
Magnetic Resonance in Medicine, 2020, Accepted

## Getting Started
The code in this repository is structured as a Julia module.
It was coded using Julia 1.1.1,
though other versions may work as well.

1. Download or clone this repository.
2. Download the BrainWeb dataset [here](https://brainweb.bic.mni.mcgill.ca/cgi/brainweb1?alias=phantom_1.0mm_normal_crisp&download=1).
   - Choose raw byte (unsigned) for the file format.
   - Choose none for compression.
   - Place the downloaded file in `<path_to_this_repo>/STFR-MWF/src/estimation/data/BrainWeb/`,
     where `<path_to_this_repo>` is where you downloaded this repo on your computer.
     (You will have to create the `data` and `BrainWeb` directories.)
3. Download Julia 1.1.1 [here](https://julialang.org/downloads/oldreleases/).
4. Run Julia.
5. Enter Julia's package prompt by typing `]` at the Julia prompt, i.e.,
   ```julia
   julia> ]
   ```
6. Add this repository with
   ```julia
   (v1.1) pkg> add <path_to_this_repo>/STFR-MWF
   ```
7. Add PyPlot.jl with
   ```julia
   (v1.1) pkg> add PyPlot
   ```
8. Return to the original Julia prompt by typing backspace, i.e.,
   ```julia
   (v1.1) pkg> <backspace>
   ```
9. Load the module with
   ```julia
   julia> using STFRMWF
   ```
10. Run any function with
   ```julia
   julia> STFRMWF.func() # Replace func with actual function name
   ```

Steps 1 through 8 only need to be done once,
and step 9 only needs to be done once each time you start Julia.

## Reproducing Results
To reproduce the results in the paper, call the corresponding function.
For example, to reproduce Figure 3 run
```julia
julia> STFRMWF.figure3()
```
Some results are used for both a figure and a table.
For example, Figure 4 and Table 3 use the same data,
so to reproduce both run
```julia
julia> STFRMWF.figure4table3()
```

The first time calling these functions may take a while
(especially the biased CRLB and NNLS results),
but after running once the results will be saved,
so future calls will simply load the results and display them.
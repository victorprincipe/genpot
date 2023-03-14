# General-Purpose Potentials for Organic Molecular Solids

Here you will find the bulk of my work on creating a general-purpose machine learning potential for organic molecular solids.

Note: the file `CSD_GAP_model.json` is Aditi's preliminary baselined potential.

General rule of thumb: Notebooks with capitalised letters at the start of each word are worthy of opening
- If there aren't any capitalised letters, the notebook will likely be a messy

There's quite a lot in this directory, but the notebook you should ___really___ open and read is `Best_Baselined_Potential.ipynb`
- This notebook applies all of what I learnt in terms of methods/best practice from the other notebooks, and creates the best performing baselined potential

If you want to recreate the best performing direct-fit potential, you can open the notebook `Best_Direct_Fit_Potential.ipynb`.
- This will be commented much less well than the `Best_Baselined_Potential.ipynb`, but it applies the exact same methodologies, and so if anything is unclear please look at that notebook and the comments.

The `general_purpose_potential_part_x.ipynb` notebooks contain the process of developing/testing the direct-fit general-purpose potential.
- The first three notebooks create an initial potential
- The notebooks thereafter have various tests/optimisations and create newer models from what I learnt, in order to improve performance
- Again, please note that the `Best_X_Potential.ipynb` contain the methodology that led to the most performant potential

The `Learning_Curves.ipynb` notebook creates learning curves using the first 20k structures from the PCovFPS-sorted _initial_ training set and varying numbers of sparse points per species. This notebook also shows how the computation time of properties increases with increasing numbers of sparse points per species, as well as when computing representations with and without gradients.
- The initial training set contains ~24.6k structures total, see the `Best_Baselined_Potential.ipynb` on how this was constructed

Other (maybe) useful notebooks are:
- `create_PCA.ipynb`, used to create a Kernel PCA map of training and test set structures, to show that there are many abnormal structures in the training set. Also shows that the binding energies of elements as determined from the training set structures and test set structures differ.
- `dftb_calcs.ipynb`, used to calculate DFTB energies and forces for the CSD-1k test set and the _initial_ training set of ~24/6k structures (11 x 2238 configurations, with the 11 most diverse from each crystal selected via FPS)
- `deepMD_potential.ipynb`, used to prepare files for use with DeepMD. Very scrappy notebook, so it might be better to ask Davide Tisi about how to create a deepMD potential as he has more experience.

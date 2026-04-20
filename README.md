# lack

Regression-focused MGraphDTA snapshot with the `full_model` fixes plus the
dataset assets needed to reproduce preprocessing and split-aware training.

Included:

- `regression/*.py` training, testing, model, and utility code
- `regression/data/davis/raw`
- `regression/data/davis/splits`
- `regression/data/kiba/raw`
- `regression/data/kiba/splits`

Not included:

- preprocessed `processed_data_train.pt` / `processed_data_test.pt` files

To make the regression code runnable after cloning, run preprocessing first:

- `python regression/preprocessing.py`

Key fixes in the code snapshot:

- `quantity_branch` is independent from `interaction_prior`
- `full_model` decorrelation acts on the actual mechanism branches
- quantity auxiliary loss is only enabled when `quantity_target` exists
- validation / best-checkpoint selection use the main affinity loss
- training returns to `train()` after validation and uses real epoch semantics

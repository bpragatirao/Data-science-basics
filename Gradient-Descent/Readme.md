# Gradient Descent — Notebook Collection

A series of Jupyter notebooks that build up gradient descent from first principles, covering manual step-by-step derivation, a from-scratch implementation, 3D cost surface visualization, and animated learning.

---

## Notebooks

### 1. `gradient_descent_step_by_step.ipynb`

A beginner-friendly walkthrough of how a single gradient descent step works. Uses a tiny dataset (`n_samples=4`) so every number is easy to follow by hand.

**What it covers:**
- Fitting a baseline OLS regression with scikit-learn
- Manually computing the loss slope with respect to the intercept `b`
- Applying a learning rate to get the step size
- Updating `b` and plotting the improved line after each step
- Building intuition for why the gradient points in the direction of steepest ascent

**Key concepts:** MSE loss, partial derivative w.r.t. `b`, learning rate, single-parameter update

---

### 2. `gradient-descent-code-from-scratch.ipynb`

Implements a full `GDRegressor` class from scratch that updates both slope `m` and intercept `b` simultaneously, then benchmarks it against scikit-learn's `LinearRegression`.

**What it covers:**
- Generating a 100-sample regression dataset with noise
- Training a scikit-learn `LinearRegression` as the reference (R² ≈ 0.635)
- Building `GDRegressor` with `fit()` and `predict()` methods
- Running gradient descent for 50 epochs at `lr=0.001`
- Confirming the custom model matches scikit-learn's coefficients and R² score

**Key concepts:** simultaneous update of `m` and `b`, epoch loop, convergence check via R²

---

### 3. `gradient-descent-3d.ipynb`

Visualizes the MSE cost surface over a grid of `(m, b)` values as an interactive 3D plot, then overlays the path that gradient descent takes across that surface.

**What it covers:**
- Building a 10×10 grid of `m` and `b` values using `np.meshgrid`
- Computing the total MSE cost at every grid point
- Rendering the cost surface with Plotly (`go.Surface`) and saving to `cost_function.html`
- Running gradient descent for 30 epochs and recording `(m, b, cost)` at each step
- Overlaying the descent trajectory as a 3D scatter on top of the cost surface

**Key concepts:** cost landscape, saddle points vs. global minimum, trajectory visualization

---

### 4. `gradient-descent-animation_both-m-and-b_.ipynb`

Animates gradient descent updating both `m` and `b` simultaneously, showing the regression line converging epoch by epoch. Also animates the cost function decreasing over epochs.

**What it covers:**
- Running 30 epochs of full gradient descent, storing `m`, `b`, and cost at each step
- Using `matplotlib.animation.FuncAnimation` to animate the fitted line
- Animating the cost-vs-epoch curve as a second panel
- Starting from intentionally bad initial values (`b=-520`, `m=600`) to make convergence visible

**Key concepts:** animation with Matplotlib, simultaneous `m`+`b` updates, cost curve

---

### 5. `gradient-descent-animation_onlyb_.ipynb`

Animates gradient descent updating only the intercept `b` while keeping the slope `m` fixed, making it easy to see a single-parameter optimization in motion.

**What it covers:**
- Fixing slope `m` at 27.82 (close to the true value) and only optimizing `b`
- Running 30 epochs and storing `all_b` and `all_cost` at each step
- Plotting all intermediate regression lines on a single scatter plot to show convergence
- Animating the line and cost curve using `FuncAnimation`

**Key concepts:** single-parameter gradient descent, cost reduction, animation basics

---

## Dependencies

```
numpy
matplotlib
scikit-learn
plotly          # required for gradient-descent-3d.ipynb
```

Install with:

```bash
pip install numpy matplotlib scikit-learn plotly
```

> The animation notebooks use `%matplotlib notebook` — run them in **Jupyter Notebook** (not JupyterLab) for inline animations.

---

## Suggested Learning Order

1. `gradient_descent_step_by_step` — understand one manual step
2. `gradient-descent-animation_onlyb_` — watch single-parameter descent animate
3. `gradient-descent-animation_both-m-and-b_` — watch both parameters converge
4. `gradient-descent-code-from-scratch` — build and validate the full algorithm
5. `gradient-descent-3d` — see the cost surface and the path through it
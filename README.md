[Webpage](https://haseebrj17.github.io/SeabornCheetSheet/)
---

Here's a comprehensive markdown documentation of the Seaborn plots with detailed parameter explanations for each type:

---

## Seaborn Plot Documentation

### 1. **Bar Plot**

```python
sns.barplot(data=iris, x='species', y='petal_length', hue=None, palette='pastel', 
            order=None, hue_order=None, estimator=np.mean, ci=95, n_boot=1000, 
            units=None, seed=None, orient=None, color=None, saturation=0.75, 
            errcolor='.26', errwidth=None, capsize=None, dodge=True, ax=None)
plt.title('Average Petal Length by Species')
plt.show()
```

#### Parameters:
- **data**: DataFrame containing the data.
- **x**, **y**: Variables that specify positions on the x and y axes.
- **hue**: Grouping variable that will produce points with different colors.
- **palette**: Colors to use for the different levels of the **hue** variable.
- **order**, **hue_order**: Order to plot the categorical levels.
- **estimator**: Statistical function to estimate within each categorical bin.
- **ci**: Size of confidence intervals.
- **n_boot**: Number of bootstrap iterations for confidence interval calculation.
- **units**: Identifier of sampling units.
- **seed**: Seed for random number generator.
- **orient**: Orientation of the plot.
- **color**: Color for all the elements.
- **saturation**: Proportion of the original saturation to use.
- **errcolor**, **errwidth**: Color and width of the error bars.
- **capsize**: Width of the caps on the error bars.
- **dodge**: Adjust bars when hue nesting is used.

### 2. **Box Plot**

```python
sns.boxplot(data=iris, x='species', y='sepal_length', hue=None, order=None, hue_order=None,
            orient=None, color=None, palette=None, saturation=0.75, width=0.8, dodge=True,
            fliersize=5, linewidth=None, whis=1.5, ax=None)
plt.title('Distribution of Sepal Length by Species')
plt.show()
```

#### Parameters:
- **width**: Width of the full element when not using hue nesting.
- **fliersize**: Size of the markers used to indicate outliers.
- **linewidth**: Width of the lines framing the plot elements.
- **whis**: Proportion past the low and high quartiles to extend the plot whiskers.

### 3. **Violin Plot**

```python
sns.violinplot(data=iris, x='species', y='sepal_width', scale='area', inner='box', split=False,
               order=None, hue_order=None, bw='scott', cut=2, linewidth=None, scale_hue=True, gridsize=100,
               width=0.8, dodge=True, orient=None, linewidth=2, color=None, palette=None, saturation=0.75)
plt.title('Distribution of Sepal Width by Species')
plt.show()
```

#### Parameters:
- **scale**: Method to scale the width of the violins.
- **inner**: Representation of the quartiles.
- **split**: Split the violins for easier comparison.
- **bw**: Bandwidth for kernel density estimation.
- **cut**: Extend the density past extreme datapoints.
- **gridsize**: Number of grid points for KDE.

### 4. **Pair Plot**

```python
sns.pairplot(data=iris, hue='species', palette='bright', vars=None, x_vars=None, y_vars=None,
             kind='scatter', diag_kind='auto', markers=None, height=2.5, aspect=1, dropna=True,
             plot_kws=None, diag_kws=None, grid_kws=None, corner=False)
plt.show()
```

#### Parameters:
- **vars**, **x_vars**, **y_vars**: Variables to use for plotting.
- **kind**: Type of plot for non-diagonal subplots.
- **diag_kind**: Type of plot for diagonal.
- **markers**: Style for each level of the hue variable.
- **height**, **aspect**: Size of the figure elements.
- **dropna**: Whether to drop missing values.
- **plot_kws**, **diag_kws**, **grid_kws**: Keyword arguments for underlying plots.
- **corner**: Only plots the lower triangle of the pair grid.

### 5. **Heatmap**

```python
sns.heatmap(data=corr, annot=True, fmt=".2f", linewidths=.5, cmap='coolwarm', center=0,
            robust=False, cbar=True, cbar_kws=None, cbar_ax=None, square=False, xticklabels='auto',
            yticklabels='auto', mask=None, ax=None)
plt.title('Correlation Matrix of Iris Dataset')
plt.show()
```

#### Parameters:
- **fmt**: String formatting

 for annotated values.
- **linewidths**: Width of the lines dividing cells.
- **cmap**: Colormap for heatmap.
- **center**: Value at which to center colormap.
- **robust**: Use robust quantiles for colormap range.
- **cbar**, **cbar_kws**, **cbar_ax**: Color bar configuration.
- **square**: Set axes aspect to “equal”.
- **xticklabels**, **yticklabels**: Axis tick labels.
- **mask**: Mask data points.

### 6. **Count Plot**

```python
sns.countplot(data=iris, x='species', hue=None, order=None, hue_order=None, orient=None, 
              color=None, palette=None, saturation=0.75, dodge=True, ax=None)
plt.title('Count of Instances by Species')
plt.show()
```

#### Parameters:
- Common parameters such as **data**, **x**, **hue**, **order**, **hue_order**, **orient**, **color**, **palette**, **saturation**, **dodge** match those used in `barplot`.

### 7. **Reg Plot**

```python
sns.regplot(data=iris, x='sepal_length', y='sepal_width', x_estimator=None, x_bins=None, 
            x_ci='ci', scatter=True, fit_reg=True, ci=95, n_boot=1000, units=None, 
            order=1, logistic=False, lowess=False, robust=False, logx=False, x_partial=None, 
            y_partial=None, truncate=False, dropna=True, x_jitter=None, y_jitter=None, 
            label=None, color='blue', marker='o', scatter_kws=None, line_kws=None, ax=None)
plt.title('Regression Plot of Sepal Length and Sepal Width')
plt.show()
```

#### Parameters:
- **x_estimator**: Function to estimate within x bins.
- **x_bins**: Bin x using pandas cut function.
- **x_ci**: Confidence interval size for x binning.
- **scatter**, **fit_reg**: Whether to plot scatter and regression line.
- **ci**: Confidence interval size for the regression estimate.
- **n_boot**: Number of bootstrap iterations.
- **order**: Order of the polynomial for fitting.
- **logistic**: Use logistic regression for binary y.
- **lowess**: Use locally weighted scatterplot smoothing.
- **robust**: Use robust regression to reduce influence of outliers.
- **logx**: Log-scale x-axis.
- **x_partial**, **y_partial**: Additional variables as covariates.
- **truncate**: Truncate regression line to data limits.
- **dropna**: Drop missing values.
- **x_jitter**, **y_jitter**: Jitter for scatter plot points.
- **label**: Label for regression line.
- **color**, **marker**: Color and style of scatter plot points.
- **scatter_kws**, **line_kws**: Additional keywords for scatter and line elements.

### 8. **Swarm Plot**

```python
sns.swarmplot(data=iris, x='species', y='petal_length', hue=None, order=None, hue_order=None, 
              dodge=False, orient=None, color=None, palette=None, size=5, edgecolor='gray', 
              linewidth=1, ax=None)
plt.title('Petal Length by Species')
plt.show()
```

#### Parameters:
- **dodge**: Adjust points when hue nesting is used.
- **size**: Size of the points in the swarm.
- **edgecolor**: Color of the edge of each point.
- **linewidth**: Width of the line around each point.

### 9. **Strip Plot**

```python
sns.stripplot(data=iris, x='species', y='petal_width', hue=None, jitter=True, order=None, hue_order=None, 
              dodge=False, orient=None, color=None, palette=None, size=5, edgecolor='gray', linewidth=1, 
              marker='o', ax=None)
plt.title('Petal Width by Species')
plt.show()
```

#### Parameters:
- **jitter**: Amount of jitter (random noise) to apply to scatter plot points to avoid overlap. Can be True, False, or a float specifying the amount of jitter.
- **marker**: Style of the marker used for the scatter plot points (e.g., 'o' for circles).

### 10. **Facet Grid**

```python
g = sns.FacetGrid(data=iris, col='species', hue='species', height=4, aspect=1, palette=None, 
                  row_order=None, col_order=None, row_titles=None, col_titles=None, 
                  despine=True, margin_titles=False, xlim=None, ylim=None, subplot_kws=None, 
                  gridspec_kws=None, dropna=True)
g.map(sns.histplot, 'sepal_length')
g.add_legend()
plt.show()
```

#### Parameters:
- **col**, **hue**: Variables that define subsets along the columns and colors.
- **height**, **aspect**: Height and aspect ratio of each facet.
- **palette**: Colors to use for the different levels of the hue variable.
- **row_order**, **col_order**: Order to organize the rows and/or columns.
- **despine**: Remove the top and right spines from the plots.
- **margin_titles**: Draw labels outside the grid area.
- **xlim**, **ylim**: Limits for the x and y axes.
- **subplot_kws**, **gridspec_kws**: Additional keyword arguments for subplots.
- **dropna**: Drop missing values from the data before plotting.

### 11. **Joint Plot**

```python
sns.jointplot(data=iris, x='sepal_length', y='sepal_width', kind='scatter', hue=None, 
              palette=None, color=None, height=6, ratio=5, space=0.2, dropna=True, xlim=None, 
              ylim=None, marginal_ticks=False, joint_kws=None, marginal_kws=None, hue_order=None, 
              kind_kws=None, common_norm=True, common_grid=False)
plt.show()
```

#### Parameters:
- **kind**: Type of plot to draw in the joint and marginal axes (e.g., "scatter", "kde").
- **ratio**: Ratio of joint axes height to marginal axes height.
- **space**: Space between the joint and marginal axes.
- **marginal_ticks**: Whether to draw ticks on the marginal axes.
- **joint_kws**, **marginal_kws**, **kind_kws**: Additional keyword arguments for the joint, marginal, and kind-specific plots, respectively.
- **common_norm**: Normalize kde plots to the full dataset or each subset if `hue` is used.
- **common_grid**: Use a common grid of reference lines for histograms.

### 12. **KDE Plot**

```python
sns.kdeplot(data=iris, x='sepal_length', y='sepal_width', hue='species', multiple='layer', 
            bw_adjust=0.5, gridsize=100, cut=3, clip=None, legend=True, cumulative=False, 
            shade=False, shade_lowest=True, cbar=False, cbar_ax=None, cbar_kws=None, ax=None, 
            weights=None, hue_order=None, palette=None, common_norm=True, common_grid=False)
plt.title('Kernel Density Estimate Plot of Sepal Length and Width')
plt.show()
```

#### Parameters:
- **multiple**: Handling of multiple elements; "layer", "stack", "fill", or "dodge".
- **bw_adjust**: Factor that multiplies the bandwidth used to calculate the KDE.
- **gridsize**: Number of grid points along each axis.
- **cut**: Factor that determines how far the KDE extends

 beyond extreme datapoints.
- **clip**: Bounds to limit the extent of the plot.
- **legend**: Whether to add a legend for hue labels.
- **cumulative**: If true, plot the cumulative distribution.
- **shade**: If true, add an underlying shade.
- **cbar**: Whether to add a color bar.
- **cbar_ax**, **cbar_kws**: Additional keyword arguments for the color bar.

### 13. **ECDF Plot**

```python
sns.ecdfplot(data=iris, x='sepal_width', hue='species', stat='proportion', complementary=False, 
             palette=None, linewidth=None, linestyle=None, drawstyle=None, 
             alpha=None, legend=True, ax=None)
plt.title('Empirical Cumulative Distribution Function for Sepal Width')
plt.show()
```

#### Parameters:
- **stat**: Statistical transformation ("count" or "proportion").
- **complementary**: If true, plot the complementary CDF.
- **linewidth**, **linestyle**, **drawstyle**: Style of the ECDF lines.
- **alpha**: Transparency level of the lines.
- **legend**: Whether to display a legend.

### 14. **Cluster Map**

```python
sns.clustermap(data=iris.drop(columns=['species']), method='average', metric='euclidean', 
               z_score=None, standard_scale=None, figsize=(10, 8), cbar_kws=None, 
               row_cluster=True, col_cluster=True, row_linkage=None, col_linkage=None, 
               row_colors=None, col_colors=None, mask=None, dendrogram_ratio=(.2, .2), 
               colors_ratio=0.03, cbar_pos=(0, .2, .03, .4))
plt.show()
```

#### Parameters:
- **method**, **metric**: Linkage and distance metrics for clustering.
- **z_score**, **standard_scale**: Normalization options.
- **figsize**: Size of the figure.
- **cbar_kws**: Keyword arguments for the color bar.
- **row_cluster**, **col_cluster**: Whether to cluster rows or columns.
- **row_linkage**, **col_linkage**: Precomputed linkage matrix for rows or columns.
- **row_colors**, **col_colors**: Colors for the annotation of rows or columns.
- **mask**: Mask for data points.
- **dendrogram_ratio**: Relative sizes of (row dendrogram, column dendrogram).
- **colors_ratio**: Height of the color bar relative to the plot.
- **cbar_pos**: Position of the color bar.




### **Additional Plot Types and Extensions**

#### **1. Line Plot**

Seaborn can be used to create line plots, which are particularly useful for time series data or data showing trends over a continuous variable.

```python
sns.lineplot(data=iris, x='sepal_length', y='petal_length', hue='species', style='species', markers=True)
plt.title('Line Plot of Sepal Length and Petal Length by Species')
plt.show()
```

#### **Parameters:**
- **markers**: Boolean or list of marker styles, one per level of the hue variable, to be used when plotting the lines.

#### **2. Cat Plot (Categorical Plot)**

This is a function that provides access to several axes-level functions that show the relationship between a numerical and one or more categorical variables using one of several visual representations.

```python
sns.catplot(data=iris, x='species', y='petal_length', kind='violin', inner='stick', split=True)
plt.title('Categorical Plot - Violin Plot of Petal Length by Species')
plt.show()
```

#### **Parameters:**
- **kind**: The kind of plot to draw (e.g., 'box', 'violin', 'bar', etc.).
- **inner**: Representation of the quartiles in violin plots.
- **split**: Whether to split the violin plots for comparing levels of the hue variable within each category.

#### **3. PairGrid**

This is a subplot grid for plotting pairwise relationships in a dataset. This allows for more customized pair plots.

```python
g = sns.PairGrid(iris, hue='species')
g.map_upper(sns.scatterplot)
g.map_lower(sns.kdeplot)
g.map_diag(sns.histplot)
g.add_legend()
plt.show()
```

#### **Parameters:**
- **map_upper**, **map_lower**, **map_diag**: Methods to draw the upper triangle, lower triangle, and diagonal subplots, respectively.

#### **4. FacetGrid with Custom Functions**

This allows you to use custom plotting functions to map data onto multiple axes.

```python
g = sns.FacetGrid(iris, col='species', hue='species')
g.map(plt.scatter, 'sepal_length', 'petal_length')
g.add_legend()
plt.show()
```

#### **Parameters:**
- No new parameters; the example uses `plt.scatter` directly, showing flexibility.

#### **5. Themes and Aesthetics**

Seaborn allows for detailed control over plot aesthetics, which can be set globally using `sns.set()` or locally using plot-specific parameters.

```python
sns.set(style='whitegrid', palette='muted')
sns.violinplot(data=iris, x='species', y='sepal_width')
plt.title('Violin Plot with Custom Aesthetics')
plt.show()
```

#### **Parameters:**
- **style**: Predefined themes provided by Seaborn (e.g., 'darkgrid', 'whitegrid', etc.).
- **palette**: Color palette choice.

### **Using Matplotlib with Seaborn**

For all Seaborn plots, since they are built on Matplotlib, you can use Matplotlib's functions to modify the plots (e.g., adding annotations, text, adjusting limits, etc.), offering unlimited customization capabilities. This integration is pivotal for tailoring your visualizations to exact specifications required by advanced data analysis or presentation needs.

---

This markdown guide comprehensively covers the key plots in Seaborn with detailed parameter explanations, aiding in the effective visualization and analysis of data.

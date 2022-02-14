# Python DataFrame Diff and Overlap Functions

**Ever found yourself wondering _what rows are in Pandas DataFrame A only, but not in B (or vice versa), and what rows are in A, as well as in B (or vice versa)?_**

While there exists `pandas.DataFrame.diff()` (more like an element-by-element subtraction), `pandas.Index.intersection` (only on the index) and `pandas.DataFrame.merge()` (more like SQL join to merge two DataFrames), none of them does exactly what we need here.

Therefore I wrote these two functions **`df_diff()`** and **`df_overlap()`** to do exactly that -- see the visual demo below.

Great things about them:

- Can compare on any column (not only on the index - but default to index if omit arguments `on_A` and/or `on_B`)
- Can compare on different column combination (like `column_this` in DataFrame A and `column_that` in DataFrame B. You can also insert concatenated id columns of your own and then compare on them)
- Can handle duplicated/missing ids correctly
- They are mainly based on set operations -- super fast!
- Has error check/handling (will safely return empty DataFrame if found no result or got invalid input)

To use the function(s), simply copy them from file `df_diff_overlap.py`. Or try notebook `df_diff_overlap.ipynb` if you prefer the step-by-step Jupyter way!

![image](https://user-images.githubusercontent.com/42301547/153688445-ecdf72b9-e334-4368-ae9f-d3e7f7ddfc2c.png)

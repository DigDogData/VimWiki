= Code snippets =

    * Check package version:
        >>> `import sklearn`
        >>> `print(sklearn.__version__)`

    * Handle console warnings:
        >>> `import warnings`
        >>> `warnings.filterwarnings("ignore")` # disable all warnings (use with cauthion)
        >>> `warnings.filterwarnings("ignore", category=FutureWarning)`
        >>> `warnings.filterwarnings("ignore", category=DeprecationWarning)`
        >>> `warnings.filterwarnings("ignore", message="divide by zero encountered")`

    * Enter two integer inputs
        >>> `print("Enter two (comma-separated) numbers:")`
        >>> `x, y = map(int, input().split(','))`

    * Generate a series of random numbers:
        >>> `import numpy as np`
        >>> `np.random.uniform(0,1,10)`

    * Create a simple Dataframe:
        >>> `import pandas as pd`
        >>> `data = {'a':range(1,11), 'b':np.random.uniform(0,1,10)}`
        >>> `df = pd.DataFrame(data)`                   # with default index
        >>> `df = pd.DataFrame(data, index=range(10,20))` # with specified index

    * Extract subset from DataFrame:
        >>> `df2 = df.get(['C1','C2'])`             # get columns _C1_ and _C2_
        >>> `df2 = df._get_numeric_data()`          # get only numerical data
        >>> `df2 = df.select_dtypes(np.number)`     # get only numerical data
        >>> `df2 = df.select_dtypes('object')`      # get only categorical data
        >>> `df2 = df.drop(['C1','C2'], axis=1)`    # drop columns _C1_ and _C2_
        >>> `df2 = df.loc[df['C1'].str.contains('V1|V2|V3', na=False)]`
                    # filter data with column 'C1' containing values _V1_, _V2_, _V3_

    * Re-encode categorical values (`custcat={1,2,3}` -> `custcat2={'a','b','c'}`):
        >>> `map_dict = {1:'a', 2:'b', 3:'c'}`
        >>> `df['custcat2'] = df.custcat.map(map_dict)`

    * Insert variable value to filename:
        >>> `a = 5`
        >>> `filename = 'decisiontree_' + str(a) + '.png'`

    == Handling lists ==
        * Delete values in list:
            >>> `spam = ['cat', 'bat', 'rat', 'elephant']`
            >>> `del spam[2]`
            >>> `spam`
            >>> ['cat', 'bat', 'elephant']

        * Looping with lists:
            >>> `for i in range(len(spam)):`
                    `print('Index ' + str(i) + ' in spam is: ' + spam[i])`
            >>> `for index, item in enumerate(spam):`
                    `print('Index ' + str(index) + ' in spam is: ' + item)`
        * Randomizing list:
            >>> `import random`
                `random.choice[spam]`
            >>> 'rat'
            >>> `random.shuffle(spam)`
            >>> ['rat', 'cat', 'elephant', 'bat']

    == Handling NA ==
        * Basic syntax:
            >>> `df.info(null_counts=True)`         # detailed info with _NA_
            >>> `df.isnull().sum()`                 # _NA_ counts of all columns
            >>> `df.isnull().sum()[data.isnull().sum()>0]`  # _NA_ counts of only _NA_ columns
            >>> `df.columns[df.isna().any()]`       # find names of _NA_ columns
            >>> `df2 = df.loc[:, df.isna().any()]`  # subset data with only _NA_ columns
            >>> `df2.select_dtypes(np.number).columns`  # find names of only numeric _NA_ columns
            >>> `df2.select_dtypes("object").columns`   # find names of only categorical _NA_ columns

        * Drop all rows with at least one NA:
            >>> `df.dropna(inplace=True)`                   # default params: `axis=0`, `how='any'`
            >>> `df.reset_index(drop=True, inplace=True)`   # reset index if needed

        * Only drop all-_NA_ rows:
            >>> `df.dropna(how='all', inplace=True)`
            >>> `df.reset_index(drop=True, inplace=True)`

        * Drop all columns with at least one _NA_:
            >>> `df.dropna(axis=1, inplace=True)`

        * Drop rows from columns _C1_ and _C2_ with at least one _NA_:
            >>> `df.dropna(subset=['C1','C2'], inplace=True)`
            >>> `df.reset_index(drop=True, inplace=True)`

    == Handling plots ==
        * Height+aspect(=W/H)(in) define size of FacetGrid/PairGrid/pairplot subplots:
            >>> `sns.PairGrid(df, hue='C1', palette="husl", height=1.5, aspect=1.2)`
            >>> `sns.pairplot(df, hue='C1', diag_kind="kde", kind="scatter", palette="husl", height=1.5, aspect=1.2)`

        * Add legend inside last subplot:
            >>> `bins = np.linspace(df.C1.min(), df.C1.max(), 10)`
            >>> `g = sns.FacetGrid(df, col='C2', hue='C3', palette="Set1", col_wrap=2)`
            >>> `g.map(plt.hist, 'C1', bins=bins, ec="k")`
            >>> `g.axes[-1].legend()`   # default way to add legend is `g.add_legend()`


.. code:: ipython3

    import pandas as pd
    data={
        'Name':['Alice','Bob','Charlie','David','Eva'],
        'Age':[25,35,67,22,45],
        'City':['New York','America','New York','India','New York']
    } 
    


.. parsed-literal::

    {'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'], 'Age': [25, 35, 67, 22, 45], 'City': ['New York', 'America', 'New York', 'India', 'New York']}
    

.. code:: ipython3

    df=pd.DataFrame(data)
    print(df)


.. parsed-literal::

          Name  Age      City
    0    Alice   25  New York
    1      Bob   35   America
    2  Charlie   67  New York
    3    David   22     India
    4      Eva   45  New York
    

.. code:: ipython3

    def categorize_age(age):
        if age <= 25:
            return 'Youth'
        elif 26 <= age <= 60:
            return 'Adult'
        else:
            return 'Senior'
    df['Age group'] = df['Age'].apply(categorize_age)
    print(df['Age group'])


.. parsed-literal::

    0     Youth
    1     Adult
    2    Senior
    3     Youth
    4     Adult
    Name: Age group, dtype: object
    

.. code:: ipython3

    cities=df[df['City'].isin(['New York'])]
    print(cities)


.. parsed-literal::

          Name  Age      City Age group
    0    Alice   25  New York     Youth
    2  Charlie   67  New York    Senior
    4      Eva   45  New York     Adult
    


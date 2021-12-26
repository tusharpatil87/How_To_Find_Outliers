# Project Goal:

# Our Primary goal is to find out the Outlier values from the Data series. We will see how to set the Minimum value to find out the Lower Outliers and we will also see how to set the Maximum value for the Higher Outliers. Even though we can use these Minimum and Maximum values to clean the impurities from the Data series.

import numpy as np
import scipy.stats as stats
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
%matplotlib inline

x = np.array([2,32,43,44,49,51,63])
y = np.array([21,27,34,38,42,48,81])

sns.boxplot(x)
plt.show()


plt.boxplot(x)
plt.show()

sns.boxplot(x)
sns.swarmplot(x)

plt.boxplot(y)
plt.show()

sns.boxplot(y)
sns.swarmplot(y)

# Formula

# Lower Outlier = Q1 - (1.5 * IQR)     #Higher Outlier = Q3 + (1.5 * IQR)

x_d = pd.Series(x)
x_d

y_d = pd.Series(y)
y_d

x_d.describe()

y_d.describe()

def Outliers(data):
    val_low = data.describe().values
    min_value = val_low[3]
    print("Minimum_Value for the data is >>> {}\n".format(min_value ))
    
    max_value = val_low[7]
    print("Maximum_Value for the data is >>> {}\n".format(max_value ))
   
    
    Q1 = val_low[4]
    print("Q1 Value for the data is >>> {}\n".format( Q1 ))
    
    val_high = data.describe().values
    Q3 = val_high[6]
    print("Q3 Value for the data is >>> {}\n".format( Q3 ))
        
    IQR = Q3-Q1
    Lower_Outlier = Q1 - (1.5 * IQR)
    Higher_Outlier = Q3 + (1.5 * IQR)
    print("Lower_Outlier Value for the data is >>> {}\n".format(Lower_Outlier ))
    print("Higher_Outlier Value for the data is >>> {}\n".format( Higher_Outlier ))
    
    if  min_value < Lower_Outlier:
        print("Conclude that there is Lower_Outlier values than {}\n".format(Lower_Outlier))
    else:
        print("Conclude that there is no Lower_Outlier values than {}\n".format(Lower_Outlier))
    
    if Higher_Outlier < max_value:
        print("Conclude that there is Higher_Outlier values than {}\n".format(Higher_Outlier))
    else:
        print("Conclude that there is no Higher_Outlier values than {}\n".format(Higher_Outlier)) 
        
Outliers(x_d)


Outliers(x_d)

Outliers(y_d)

# Project Conclusion:

# We have successfully implemented the logic for the customized function and with the help of that we achieved our Primary goal which is to find out the Outlier values from the Data series. We have seen how to set the Minimum value to find out the Lower Outliers and we have also seen that how to set the Maximum value for the Higher Outliers. Now we can use this function values  like Minimum and Maximum values to clean the impurities from the Data series.


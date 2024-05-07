```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```


```python
df = pd.read_csv(r"C:\Users\alexm\OneDrive\文档\Data Analyst\Python\world_population_pd.csv")

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.0</td>
      <td>38972230.0</td>
      <td>33753499.0</td>
      <td>28189672.0</td>
      <td>19542982.0</td>
      <td>10694796.0</td>
      <td>12486631.0</td>
      <td>10752971.0</td>
      <td>652230.0</td>
      <td>63.0587</td>
      <td>1.0257</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.0</td>
      <td>2866849.0</td>
      <td>2882481.0</td>
      <td>2913399.0</td>
      <td>3182021.0</td>
      <td>3295066.0</td>
      <td>2941651.0</td>
      <td>2324731.0</td>
      <td>28748.0</td>
      <td>98.8702</td>
      <td>0.9957</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.0</td>
      <td>43451666.0</td>
      <td>39543154.0</td>
      <td>35856344.0</td>
      <td>30774621.0</td>
      <td>25518074.0</td>
      <td>18739378.0</td>
      <td>13795915.0</td>
      <td>2381741.0</td>
      <td>18.8531</td>
      <td>1.0164</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.0</td>
      <td>46189.0</td>
      <td>51368.0</td>
      <td>54849.0</td>
      <td>58230.0</td>
      <td>47818.0</td>
      <td>32886.0</td>
      <td>27075.0</td>
      <td>199.0</td>
      <td>222.4774</td>
      <td>0.9831</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.0</td>
      <td>77700.0</td>
      <td>71746.0</td>
      <td>71519.0</td>
      <td>66097.0</td>
      <td>53569.0</td>
      <td>35611.0</td>
      <td>19860.0</td>
      <td>468.0</td>
      <td>170.5641</td>
      <td>1.0100</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>235</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.0</td>
      <td>11655.0</td>
      <td>12182.0</td>
      <td>13142.0</td>
      <td>14723.0</td>
      <td>13454.0</td>
      <td>11315.0</td>
      <td>9377.0</td>
      <td>142.0</td>
      <td>81.4930</td>
      <td>0.9953</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>236</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.0</td>
      <td>556048.0</td>
      <td>491824.0</td>
      <td>413296.0</td>
      <td>270375.0</td>
      <td>178529.0</td>
      <td>116775.0</td>
      <td>76371.0</td>
      <td>266000.0</td>
      <td>2.1654</td>
      <td>1.0184</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>237</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.0</td>
      <td>32284046.0</td>
      <td>28516545.0</td>
      <td>24743946.0</td>
      <td>18628700.0</td>
      <td>13375121.0</td>
      <td>9204938.0</td>
      <td>6843607.0</td>
      <td>527968.0</td>
      <td>63.8232</td>
      <td>1.0217</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>238</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.0</td>
      <td>18927715.0</td>
      <td>NaN</td>
      <td>13792086.0</td>
      <td>9891136.0</td>
      <td>7686401.0</td>
      <td>5720438.0</td>
      <td>4281671.0</td>
      <td>752612.0</td>
      <td>26.5976</td>
      <td>1.0280</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>239</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.0</td>
      <td>15669666.0</td>
      <td>14154937.0</td>
      <td>12839771.0</td>
      <td>11834676.0</td>
      <td>10113893.0</td>
      <td>7049926.0</td>
      <td>5202918.0</td>
      <td>390757.0</td>
      <td>41.7665</td>
      <td>1.0204</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>240 rows × 17 columns</p>
</div>




```python
# Remove Duplicates

df = df.drop_duplicates()

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.0</td>
      <td>38972230.0</td>
      <td>33753499.0</td>
      <td>28189672.0</td>
      <td>19542982.0</td>
      <td>10694796.0</td>
      <td>12486631.0</td>
      <td>10752971.0</td>
      <td>652230.0</td>
      <td>63.0587</td>
      <td>1.0257</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.0</td>
      <td>2866849.0</td>
      <td>2882481.0</td>
      <td>2913399.0</td>
      <td>3182021.0</td>
      <td>3295066.0</td>
      <td>2941651.0</td>
      <td>2324731.0</td>
      <td>28748.0</td>
      <td>98.8702</td>
      <td>0.9957</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.0</td>
      <td>43451666.0</td>
      <td>39543154.0</td>
      <td>35856344.0</td>
      <td>30774621.0</td>
      <td>25518074.0</td>
      <td>18739378.0</td>
      <td>13795915.0</td>
      <td>2381741.0</td>
      <td>18.8531</td>
      <td>1.0164</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.0</td>
      <td>46189.0</td>
      <td>51368.0</td>
      <td>54849.0</td>
      <td>58230.0</td>
      <td>47818.0</td>
      <td>32886.0</td>
      <td>27075.0</td>
      <td>199.0</td>
      <td>222.4774</td>
      <td>0.9831</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.0</td>
      <td>77700.0</td>
      <td>71746.0</td>
      <td>71519.0</td>
      <td>66097.0</td>
      <td>53569.0</td>
      <td>35611.0</td>
      <td>19860.0</td>
      <td>468.0</td>
      <td>170.5641</td>
      <td>1.0100</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>235</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.0</td>
      <td>11655.0</td>
      <td>12182.0</td>
      <td>13142.0</td>
      <td>14723.0</td>
      <td>13454.0</td>
      <td>11315.0</td>
      <td>9377.0</td>
      <td>142.0</td>
      <td>81.4930</td>
      <td>0.9953</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>236</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.0</td>
      <td>556048.0</td>
      <td>491824.0</td>
      <td>413296.0</td>
      <td>270375.0</td>
      <td>178529.0</td>
      <td>116775.0</td>
      <td>76371.0</td>
      <td>266000.0</td>
      <td>2.1654</td>
      <td>1.0184</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>237</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.0</td>
      <td>32284046.0</td>
      <td>28516545.0</td>
      <td>24743946.0</td>
      <td>18628700.0</td>
      <td>13375121.0</td>
      <td>9204938.0</td>
      <td>6843607.0</td>
      <td>527968.0</td>
      <td>63.8232</td>
      <td>1.0217</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>238</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.0</td>
      <td>18927715.0</td>
      <td>NaN</td>
      <td>13792086.0</td>
      <td>9891136.0</td>
      <td>7686401.0</td>
      <td>5720438.0</td>
      <td>4281671.0</td>
      <td>752612.0</td>
      <td>26.5976</td>
      <td>1.0280</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>239</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.0</td>
      <td>15669666.0</td>
      <td>14154937.0</td>
      <td>12839771.0</td>
      <td>11834676.0</td>
      <td>10113893.0</td>
      <td>7049926.0</td>
      <td>5202918.0</td>
      <td>390757.0</td>
      <td>41.7665</td>
      <td>1.0204</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
df = df.reset_index(drop=True)

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.0</td>
      <td>38972230.0</td>
      <td>33753499.0</td>
      <td>28189672.0</td>
      <td>19542982.0</td>
      <td>10694796.0</td>
      <td>12486631.0</td>
      <td>10752971.0</td>
      <td>652230.0</td>
      <td>63.0587</td>
      <td>1.0257</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.0</td>
      <td>2866849.0</td>
      <td>2882481.0</td>
      <td>2913399.0</td>
      <td>3182021.0</td>
      <td>3295066.0</td>
      <td>2941651.0</td>
      <td>2324731.0</td>
      <td>28748.0</td>
      <td>98.8702</td>
      <td>0.9957</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.0</td>
      <td>43451666.0</td>
      <td>39543154.0</td>
      <td>35856344.0</td>
      <td>30774621.0</td>
      <td>25518074.0</td>
      <td>18739378.0</td>
      <td>13795915.0</td>
      <td>2381741.0</td>
      <td>18.8531</td>
      <td>1.0164</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.0</td>
      <td>46189.0</td>
      <td>51368.0</td>
      <td>54849.0</td>
      <td>58230.0</td>
      <td>47818.0</td>
      <td>32886.0</td>
      <td>27075.0</td>
      <td>199.0</td>
      <td>222.4774</td>
      <td>0.9831</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.0</td>
      <td>77700.0</td>
      <td>71746.0</td>
      <td>71519.0</td>
      <td>66097.0</td>
      <td>53569.0</td>
      <td>35611.0</td>
      <td>19860.0</td>
      <td>468.0</td>
      <td>170.5641</td>
      <td>1.0100</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.0</td>
      <td>11655.0</td>
      <td>12182.0</td>
      <td>13142.0</td>
      <td>14723.0</td>
      <td>13454.0</td>
      <td>11315.0</td>
      <td>9377.0</td>
      <td>142.0</td>
      <td>81.4930</td>
      <td>0.9953</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.0</td>
      <td>556048.0</td>
      <td>491824.0</td>
      <td>413296.0</td>
      <td>270375.0</td>
      <td>178529.0</td>
      <td>116775.0</td>
      <td>76371.0</td>
      <td>266000.0</td>
      <td>2.1654</td>
      <td>1.0184</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.0</td>
      <td>32284046.0</td>
      <td>28516545.0</td>
      <td>24743946.0</td>
      <td>18628700.0</td>
      <td>13375121.0</td>
      <td>9204938.0</td>
      <td>6843607.0</td>
      <td>527968.0</td>
      <td>63.8232</td>
      <td>1.0217</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>232</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.0</td>
      <td>18927715.0</td>
      <td>NaN</td>
      <td>13792086.0</td>
      <td>9891136.0</td>
      <td>7686401.0</td>
      <td>5720438.0</td>
      <td>4281671.0</td>
      <td>752612.0</td>
      <td>26.5976</td>
      <td>1.0280</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.0</td>
      <td>15669666.0</td>
      <td>14154937.0</td>
      <td>12839771.0</td>
      <td>11834676.0</td>
      <td>10113893.0</td>
      <td>7049926.0</td>
      <td>5202918.0</td>
      <td>390757.0</td>
      <td>41.7665</td>
      <td>1.0204</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
# Standardize Format

df["Country"] = df["Country"].str.strip()

df["Capital"] = df["Capital"].str.strip()

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.0</td>
      <td>38972230.0</td>
      <td>33753499.0</td>
      <td>28189672.0</td>
      <td>19542982.0</td>
      <td>10694796.0</td>
      <td>12486631.0</td>
      <td>10752971.0</td>
      <td>652230.0</td>
      <td>63.0587</td>
      <td>1.0257</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.0</td>
      <td>2866849.0</td>
      <td>2882481.0</td>
      <td>2913399.0</td>
      <td>3182021.0</td>
      <td>3295066.0</td>
      <td>2941651.0</td>
      <td>2324731.0</td>
      <td>28748.0</td>
      <td>98.8702</td>
      <td>0.9957</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.0</td>
      <td>43451666.0</td>
      <td>39543154.0</td>
      <td>35856344.0</td>
      <td>30774621.0</td>
      <td>25518074.0</td>
      <td>18739378.0</td>
      <td>13795915.0</td>
      <td>2381741.0</td>
      <td>18.8531</td>
      <td>1.0164</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.0</td>
      <td>46189.0</td>
      <td>51368.0</td>
      <td>54849.0</td>
      <td>58230.0</td>
      <td>47818.0</td>
      <td>32886.0</td>
      <td>27075.0</td>
      <td>199.0</td>
      <td>222.4774</td>
      <td>0.9831</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.0</td>
      <td>77700.0</td>
      <td>71746.0</td>
      <td>71519.0</td>
      <td>66097.0</td>
      <td>53569.0</td>
      <td>35611.0</td>
      <td>19860.0</td>
      <td>468.0</td>
      <td>170.5641</td>
      <td>1.0100</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.0</td>
      <td>11655.0</td>
      <td>12182.0</td>
      <td>13142.0</td>
      <td>14723.0</td>
      <td>13454.0</td>
      <td>11315.0</td>
      <td>9377.0</td>
      <td>142.0</td>
      <td>81.4930</td>
      <td>0.9953</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.0</td>
      <td>556048.0</td>
      <td>491824.0</td>
      <td>413296.0</td>
      <td>270375.0</td>
      <td>178529.0</td>
      <td>116775.0</td>
      <td>76371.0</td>
      <td>266000.0</td>
      <td>2.1654</td>
      <td>1.0184</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.0</td>
      <td>32284046.0</td>
      <td>28516545.0</td>
      <td>24743946.0</td>
      <td>18628700.0</td>
      <td>13375121.0</td>
      <td>9204938.0</td>
      <td>6843607.0</td>
      <td>527968.0</td>
      <td>63.8232</td>
      <td>1.0217</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>232</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.0</td>
      <td>18927715.0</td>
      <td>NaN</td>
      <td>13792086.0</td>
      <td>9891136.0</td>
      <td>7686401.0</td>
      <td>5720438.0</td>
      <td>4281671.0</td>
      <td>752612.0</td>
      <td>26.5976</td>
      <td>1.0280</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.0</td>
      <td>15669666.0</td>
      <td>14154937.0</td>
      <td>12839771.0</td>
      <td>11834676.0</td>
      <td>10113893.0</td>
      <td>7049926.0</td>
      <td>5202918.0</td>
      <td>390757.0</td>
      <td>41.7665</td>
      <td>1.0204</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
df["Country"] = df["Country"].str.replace('%','')

df["Capital"] = df["Capital"].str.replace('%','')

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.0</td>
      <td>38972230.0</td>
      <td>33753499.0</td>
      <td>28189672.0</td>
      <td>19542982.0</td>
      <td>10694796.0</td>
      <td>12486631.0</td>
      <td>10752971.0</td>
      <td>652230.0</td>
      <td>63.0587</td>
      <td>1.0257</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.0</td>
      <td>2866849.0</td>
      <td>2882481.0</td>
      <td>2913399.0</td>
      <td>3182021.0</td>
      <td>3295066.0</td>
      <td>2941651.0</td>
      <td>2324731.0</td>
      <td>28748.0</td>
      <td>98.8702</td>
      <td>0.9957</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.0</td>
      <td>43451666.0</td>
      <td>39543154.0</td>
      <td>35856344.0</td>
      <td>30774621.0</td>
      <td>25518074.0</td>
      <td>18739378.0</td>
      <td>13795915.0</td>
      <td>2381741.0</td>
      <td>18.8531</td>
      <td>1.0164</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.0</td>
      <td>46189.0</td>
      <td>51368.0</td>
      <td>54849.0</td>
      <td>58230.0</td>
      <td>47818.0</td>
      <td>32886.0</td>
      <td>27075.0</td>
      <td>199.0</td>
      <td>222.4774</td>
      <td>0.9831</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.0</td>
      <td>77700.0</td>
      <td>71746.0</td>
      <td>71519.0</td>
      <td>66097.0</td>
      <td>53569.0</td>
      <td>35611.0</td>
      <td>19860.0</td>
      <td>468.0</td>
      <td>170.5641</td>
      <td>1.0100</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.0</td>
      <td>11655.0</td>
      <td>12182.0</td>
      <td>13142.0</td>
      <td>14723.0</td>
      <td>13454.0</td>
      <td>11315.0</td>
      <td>9377.0</td>
      <td>142.0</td>
      <td>81.4930</td>
      <td>0.9953</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.0</td>
      <td>556048.0</td>
      <td>491824.0</td>
      <td>413296.0</td>
      <td>270375.0</td>
      <td>178529.0</td>
      <td>116775.0</td>
      <td>76371.0</td>
      <td>266000.0</td>
      <td>2.1654</td>
      <td>1.0184</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.0</td>
      <td>32284046.0</td>
      <td>28516545.0</td>
      <td>24743946.0</td>
      <td>18628700.0</td>
      <td>13375121.0</td>
      <td>9204938.0</td>
      <td>6843607.0</td>
      <td>527968.0</td>
      <td>63.8232</td>
      <td>1.0217</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>232</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.0</td>
      <td>18927715.0</td>
      <td>NaN</td>
      <td>13792086.0</td>
      <td>9891136.0</td>
      <td>7686401.0</td>
      <td>5720438.0</td>
      <td>4281671.0</td>
      <td>752612.0</td>
      <td>26.5976</td>
      <td>1.0280</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.0</td>
      <td>15669666.0</td>
      <td>14154937.0</td>
      <td>12839771.0</td>
      <td>11834676.0</td>
      <td>10113893.0</td>
      <td>7049926.0</td>
      <td>5202918.0</td>
      <td>390757.0</td>
      <td>41.7665</td>
      <td>1.0204</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
pd.set_option('display.float_format', lambda x: '%.2f' %x)

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.00</td>
      <td>38972230.00</td>
      <td>33753499.00</td>
      <td>28189672.00</td>
      <td>19542982.00</td>
      <td>10694796.00</td>
      <td>12486631.00</td>
      <td>10752971.00</td>
      <td>652230.00</td>
      <td>63.06</td>
      <td>1.03</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.00</td>
      <td>2866849.00</td>
      <td>2882481.00</td>
      <td>2913399.00</td>
      <td>3182021.00</td>
      <td>3295066.00</td>
      <td>2941651.00</td>
      <td>2324731.00</td>
      <td>28748.00</td>
      <td>98.87</td>
      <td>1.00</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.00</td>
      <td>43451666.00</td>
      <td>39543154.00</td>
      <td>35856344.00</td>
      <td>30774621.00</td>
      <td>25518074.00</td>
      <td>18739378.00</td>
      <td>13795915.00</td>
      <td>2381741.00</td>
      <td>18.85</td>
      <td>1.02</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.00</td>
      <td>46189.00</td>
      <td>51368.00</td>
      <td>54849.00</td>
      <td>58230.00</td>
      <td>47818.00</td>
      <td>32886.00</td>
      <td>27075.00</td>
      <td>199.00</td>
      <td>222.48</td>
      <td>0.98</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.00</td>
      <td>77700.00</td>
      <td>71746.00</td>
      <td>71519.00</td>
      <td>66097.00</td>
      <td>53569.00</td>
      <td>35611.00</td>
      <td>19860.00</td>
      <td>468.00</td>
      <td>170.56</td>
      <td>1.01</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.00</td>
      <td>11655.00</td>
      <td>12182.00</td>
      <td>13142.00</td>
      <td>14723.00</td>
      <td>13454.00</td>
      <td>11315.00</td>
      <td>9377.00</td>
      <td>142.00</td>
      <td>81.49</td>
      <td>1.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.00</td>
      <td>556048.00</td>
      <td>491824.00</td>
      <td>413296.00</td>
      <td>270375.00</td>
      <td>178529.00</td>
      <td>116775.00</td>
      <td>76371.00</td>
      <td>266000.00</td>
      <td>2.17</td>
      <td>1.02</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.00</td>
      <td>32284046.00</td>
      <td>28516545.00</td>
      <td>24743946.00</td>
      <td>18628700.00</td>
      <td>13375121.00</td>
      <td>9204938.00</td>
      <td>6843607.00</td>
      <td>527968.00</td>
      <td>63.82</td>
      <td>1.02</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>232</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.00</td>
      <td>18927715.00</td>
      <td>NaN</td>
      <td>13792086.00</td>
      <td>9891136.00</td>
      <td>7686401.00</td>
      <td>5720438.00</td>
      <td>4281671.00</td>
      <td>752612.00</td>
      <td>26.60</td>
      <td>1.03</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.00</td>
      <td>15669666.00</td>
      <td>14154937.00</td>
      <td>12839771.00</td>
      <td>11834676.00</td>
      <td>10113893.00</td>
      <td>7049926.00</td>
      <td>5202918.00</td>
      <td>390757.00</td>
      <td>41.77</td>
      <td>1.02</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 234 entries, 0 to 233
    Data columns (total 17 columns):
     #   Column                       Non-Null Count  Dtype  
    ---  ------                       --------------  -----  
     0   Rank                         234 non-null    int64  
     1   CCA3                         234 non-null    object 
     2   Country                      234 non-null    object 
     3   Capital                      234 non-null    object 
     4   Continent                    234 non-null    object 
     5   2022 Population              230 non-null    float64
     6   2020 Population              233 non-null    float64
     7   2015 Population              230 non-null    float64
     8   2010 Population              227 non-null    float64
     9   2000 Population              227 non-null    float64
     10  1990 Population              229 non-null    float64
     11  1980 Population              229 non-null    float64
     12  1970 Population              230 non-null    float64
     13  Area (km²)                   232 non-null    float64
     14  Density (per km²)            230 non-null    float64
     15  Growth Rate                  232 non-null    float64
     16  World Population Percentage  234 non-null    float64
    dtypes: float64(12), int64(1), object(4)
    memory usage: 31.2+ KB
    


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>234.00</td>
      <td>230.00</td>
      <td>233.00</td>
      <td>230.00</td>
      <td>227.00</td>
      <td>227.00</td>
      <td>229.00</td>
      <td>229.00</td>
      <td>230.00</td>
      <td>232.00</td>
      <td>230.00</td>
      <td>232.00</td>
      <td>234.00</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>117.50</td>
      <td>34632250.88</td>
      <td>33600710.95</td>
      <td>32066004.16</td>
      <td>30270164.48</td>
      <td>26840495.26</td>
      <td>19330463.93</td>
      <td>16282884.78</td>
      <td>15866499.13</td>
      <td>581663.75</td>
      <td>456.81</td>
      <td>1.01</td>
      <td>0.43</td>
    </tr>
    <tr>
      <th>std</th>
      <td>67.69</td>
      <td>137889172.44</td>
      <td>135873196.61</td>
      <td>131507146.34</td>
      <td>126074183.54</td>
      <td>113352454.57</td>
      <td>81309624.96</td>
      <td>69345465.54</td>
      <td>68355859.75</td>
      <td>1769133.06</td>
      <td>2083.74</td>
      <td>0.01</td>
      <td>1.71</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.00</td>
      <td>510.00</td>
      <td>520.00</td>
      <td>564.00</td>
      <td>596.00</td>
      <td>651.00</td>
      <td>700.00</td>
      <td>733.00</td>
      <td>752.00</td>
      <td>1.00</td>
      <td>0.03</td>
      <td>0.91</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>59.25</td>
      <td>419738.50</td>
      <td>406471.00</td>
      <td>394295.00</td>
      <td>382726.50</td>
      <td>329470.00</td>
      <td>261928.00</td>
      <td>223752.00</td>
      <td>145880.50</td>
      <td>2567.25</td>
      <td>36.60</td>
      <td>1.00</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>117.50</td>
      <td>5762857.00</td>
      <td>5456681.00</td>
      <td>5244415.00</td>
      <td>4889741.00</td>
      <td>4491202.00</td>
      <td>3785847.00</td>
      <td>3135123.00</td>
      <td>2511718.00</td>
      <td>77141.00</td>
      <td>95.35</td>
      <td>1.01</td>
      <td>0.07</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>175.75</td>
      <td>22653719.00</td>
      <td>21522626.00</td>
      <td>19730853.75</td>
      <td>16825852.50</td>
      <td>15625467.00</td>
      <td>11882762.00</td>
      <td>9817257.00</td>
      <td>8817329.00</td>
      <td>414643.25</td>
      <td>236.88</td>
      <td>1.02</td>
      <td>0.28</td>
    </tr>
    <tr>
      <th>max</th>
      <td>234.00</td>
      <td>1425887337.00</td>
      <td>1424929781.00</td>
      <td>1393715448.00</td>
      <td>1348191368.00</td>
      <td>1264099069.00</td>
      <td>1153704252.00</td>
      <td>982372466.00</td>
      <td>822534450.00</td>
      <td>17098242.00</td>
      <td>23172.27</td>
      <td>1.07</td>
      <td>17.88</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.isnull().sum()
```




    Rank                           0
    CCA3                           0
    Country                        0
    Capital                        0
    Continent                      0
    2022 Population                4
    2020 Population                1
    2015 Population                4
    2010 Population                7
    2000 Population                7
    1990 Population                5
    1980 Population                5
    1970 Population                4
    Area (km²)                     2
    Density (per km²)              4
    Growth Rate                    2
    World Population Percentage    0
    dtype: int64




```python
df=df.fillna('')

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.00</td>
      <td>38972230.00</td>
      <td>33753499.00</td>
      <td>28189672.00</td>
      <td>19542982.00</td>
      <td>10694796.00</td>
      <td>12486631.00</td>
      <td>10752971.00</td>
      <td>652230.00</td>
      <td>63.06</td>
      <td>1.03</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.00</td>
      <td>2866849.00</td>
      <td>2882481.00</td>
      <td>2913399.00</td>
      <td>3182021.00</td>
      <td>3295066.00</td>
      <td>2941651.00</td>
      <td>2324731.00</td>
      <td>28748.00</td>
      <td>98.87</td>
      <td>1.00</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.00</td>
      <td>43451666.00</td>
      <td>39543154.00</td>
      <td>35856344.00</td>
      <td>30774621.00</td>
      <td>25518074.00</td>
      <td>18739378.00</td>
      <td>13795915.00</td>
      <td>2381741.00</td>
      <td>18.85</td>
      <td>1.02</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.00</td>
      <td>46189.00</td>
      <td>51368.00</td>
      <td>54849.00</td>
      <td>58230.00</td>
      <td>47818.00</td>
      <td>32886.00</td>
      <td>27075.00</td>
      <td>199.00</td>
      <td>222.48</td>
      <td>0.98</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.00</td>
      <td>77700.00</td>
      <td>71746.00</td>
      <td>71519.00</td>
      <td>66097.00</td>
      <td>53569.00</td>
      <td>35611.00</td>
      <td>19860.00</td>
      <td>468.00</td>
      <td>170.56</td>
      <td>1.01</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.00</td>
      <td>11655.00</td>
      <td>12182.00</td>
      <td>13142.00</td>
      <td>14723.00</td>
      <td>13454.00</td>
      <td>11315.00</td>
      <td>9377.00</td>
      <td>142.00</td>
      <td>81.49</td>
      <td>1.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.00</td>
      <td>556048.00</td>
      <td>491824.00</td>
      <td>413296.00</td>
      <td>270375.00</td>
      <td>178529.00</td>
      <td>116775.00</td>
      <td>76371.00</td>
      <td>266000.00</td>
      <td>2.17</td>
      <td>1.02</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.00</td>
      <td>32284046.00</td>
      <td>28516545.00</td>
      <td>24743946.00</td>
      <td>18628700.00</td>
      <td>13375121.00</td>
      <td>9204938.00</td>
      <td>6843607.00</td>
      <td>527968.00</td>
      <td>63.82</td>
      <td>1.02</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>232</th>
      <td>63</td>
      <td>ZMB</td>
      <td>Zambia</td>
      <td>Lusaka</td>
      <td>Africa</td>
      <td>20017675.00</td>
      <td>18927715.00</td>
      <td></td>
      <td>13792086.00</td>
      <td>9891136.00</td>
      <td>7686401.00</td>
      <td>5720438.00</td>
      <td>4281671.00</td>
      <td>752612.00</td>
      <td>26.60</td>
      <td>1.03</td>
      <td>0.25</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.00</td>
      <td>15669666.00</td>
      <td>14154937.00</td>
      <td>12839771.00</td>
      <td>11834676.00</td>
      <td>10113893.00</td>
      <td>7049926.00</td>
      <td>5202918.00</td>
      <td>390757.00</td>
      <td>41.77</td>
      <td>1.02</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>234 rows × 17 columns</p>
</div>




```python
for x in df.index:
    if df.loc[x, "2022 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "2020 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "2015 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "2010 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "2000 Population"] == '':
        df.drop(x, inplace=True)

for x in df.index:
    if df.loc[x, "1990 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "1980 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "1970 Population"] == '':
        df.drop(x, inplace=True)
        
for x in df.index:
    if df.loc[x, "Density (per km²)"] == '':
        df.drop(x, inplace=True)
        
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.00</td>
      <td>38972230.00</td>
      <td>33753499.00</td>
      <td>28189672.00</td>
      <td>19542982.00</td>
      <td>10694796.00</td>
      <td>12486631.00</td>
      <td>10752971.00</td>
      <td>652230.00</td>
      <td>63.06</td>
      <td>1.03</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.00</td>
      <td>2866849.00</td>
      <td>2882481.00</td>
      <td>2913399.00</td>
      <td>3182021.00</td>
      <td>3295066.00</td>
      <td>2941651.00</td>
      <td>2324731.00</td>
      <td>28748.00</td>
      <td>98.87</td>
      <td>1.00</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.00</td>
      <td>43451666.00</td>
      <td>39543154.00</td>
      <td>35856344.00</td>
      <td>30774621.00</td>
      <td>25518074.00</td>
      <td>18739378.00</td>
      <td>13795915.00</td>
      <td>2381741.00</td>
      <td>18.85</td>
      <td>1.02</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.00</td>
      <td>46189.00</td>
      <td>51368.00</td>
      <td>54849.00</td>
      <td>58230.00</td>
      <td>47818.00</td>
      <td>32886.00</td>
      <td>27075.00</td>
      <td>199.00</td>
      <td>222.48</td>
      <td>0.98</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.00</td>
      <td>77700.00</td>
      <td>71746.00</td>
      <td>71519.00</td>
      <td>66097.00</td>
      <td>53569.00</td>
      <td>35611.00</td>
      <td>19860.00</td>
      <td>468.00</td>
      <td>170.56</td>
      <td>1.01</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>228</th>
      <td>16</td>
      <td>VNM</td>
      <td>Vietnam</td>
      <td>Hanoi</td>
      <td>Asia</td>
      <td>98186856.00</td>
      <td>96648685.00</td>
      <td>92191398.00</td>
      <td>87411012.00</td>
      <td>79001142.00</td>
      <td>66912613.00</td>
      <td>52968270.00</td>
      <td>41928849.00</td>
      <td>331212.00</td>
      <td>296.45</td>
      <td>1.01</td>
      <td>1.23</td>
    </tr>
    <tr>
      <th>229</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.00</td>
      <td>11655.00</td>
      <td>12182.00</td>
      <td>13142.00</td>
      <td>14723.00</td>
      <td>13454.00</td>
      <td>11315.00</td>
      <td>9377.00</td>
      <td>142.00</td>
      <td>81.49</td>
      <td>1.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>230</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.00</td>
      <td>556048.00</td>
      <td>491824.00</td>
      <td>413296.00</td>
      <td>270375.00</td>
      <td>178529.00</td>
      <td>116775.00</td>
      <td>76371.00</td>
      <td>266000.00</td>
      <td>2.17</td>
      <td>1.02</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>231</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.00</td>
      <td>32284046.00</td>
      <td>28516545.00</td>
      <td>24743946.00</td>
      <td>18628700.00</td>
      <td>13375121.00</td>
      <td>9204938.00</td>
      <td>6843607.00</td>
      <td>527968.00</td>
      <td>63.82</td>
      <td>1.02</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>233</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.00</td>
      <td>15669666.00</td>
      <td>14154937.00</td>
      <td>12839771.00</td>
      <td>11834676.00</td>
      <td>10113893.00</td>
      <td>7049926.00</td>
      <td>5202918.00</td>
      <td>390757.00</td>
      <td>41.77</td>
      <td>1.02</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>209 rows × 17 columns</p>
</div>




```python
df.isnull().sum()
```




    Rank                           0
    CCA3                           0
    Country                        0
    Capital                        0
    Continent                      0
    2022 Population                0
    2020 Population                0
    2015 Population                0
    2010 Population                0
    2000 Population                0
    1990 Population                0
    1980 Population                0
    1970 Population                0
    Area (km²)                     0
    Density (per km²)              0
    Growth Rate                    0
    World Population Percentage    0
    dtype: int64




```python
df = df.reset_index(drop=True)

df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>36</td>
      <td>AFG</td>
      <td>Afghanistan</td>
      <td>Kabul</td>
      <td>Asia</td>
      <td>41128771.00</td>
      <td>38972230.00</td>
      <td>33753499.00</td>
      <td>28189672.00</td>
      <td>19542982.00</td>
      <td>10694796.00</td>
      <td>12486631.00</td>
      <td>10752971.00</td>
      <td>652230.00</td>
      <td>63.06</td>
      <td>1.03</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>1</th>
      <td>138</td>
      <td>ALB</td>
      <td>Albania</td>
      <td>Tirana</td>
      <td>Europe</td>
      <td>2842321.00</td>
      <td>2866849.00</td>
      <td>2882481.00</td>
      <td>2913399.00</td>
      <td>3182021.00</td>
      <td>3295066.00</td>
      <td>2941651.00</td>
      <td>2324731.00</td>
      <td>28748.00</td>
      <td>98.87</td>
      <td>1.00</td>
      <td>0.04</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>DZA</td>
      <td>Algeria</td>
      <td>Algiers</td>
      <td>Africa</td>
      <td>44903225.00</td>
      <td>43451666.00</td>
      <td>39543154.00</td>
      <td>35856344.00</td>
      <td>30774621.00</td>
      <td>25518074.00</td>
      <td>18739378.00</td>
      <td>13795915.00</td>
      <td>2381741.00</td>
      <td>18.85</td>
      <td>1.02</td>
      <td>0.56</td>
    </tr>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.00</td>
      <td>46189.00</td>
      <td>51368.00</td>
      <td>54849.00</td>
      <td>58230.00</td>
      <td>47818.00</td>
      <td>32886.00</td>
      <td>27075.00</td>
      <td>199.00</td>
      <td>222.48</td>
      <td>0.98</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>203</td>
      <td>AND</td>
      <td>Andorra</td>
      <td>Andorra la Vella</td>
      <td>Europe</td>
      <td>79824.00</td>
      <td>77700.00</td>
      <td>71746.00</td>
      <td>71519.00</td>
      <td>66097.00</td>
      <td>53569.00</td>
      <td>35611.00</td>
      <td>19860.00</td>
      <td>468.00</td>
      <td>170.56</td>
      <td>1.01</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>204</th>
      <td>16</td>
      <td>VNM</td>
      <td>Vietnam</td>
      <td>Hanoi</td>
      <td>Asia</td>
      <td>98186856.00</td>
      <td>96648685.00</td>
      <td>92191398.00</td>
      <td>87411012.00</td>
      <td>79001142.00</td>
      <td>66912613.00</td>
      <td>52968270.00</td>
      <td>41928849.00</td>
      <td>331212.00</td>
      <td>296.45</td>
      <td>1.01</td>
      <td>1.23</td>
    </tr>
    <tr>
      <th>205</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.00</td>
      <td>11655.00</td>
      <td>12182.00</td>
      <td>13142.00</td>
      <td>14723.00</td>
      <td>13454.00</td>
      <td>11315.00</td>
      <td>9377.00</td>
      <td>142.00</td>
      <td>81.49</td>
      <td>1.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>206</th>
      <td>172</td>
      <td>ESH</td>
      <td>Western Sahara</td>
      <td>El Aaiún</td>
      <td>Africa</td>
      <td>575986.00</td>
      <td>556048.00</td>
      <td>491824.00</td>
      <td>413296.00</td>
      <td>270375.00</td>
      <td>178529.00</td>
      <td>116775.00</td>
      <td>76371.00</td>
      <td>266000.00</td>
      <td>2.17</td>
      <td>1.02</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>207</th>
      <td>46</td>
      <td>YEM</td>
      <td>Yemen</td>
      <td>Sanaa</td>
      <td>Asia</td>
      <td>33696614.00</td>
      <td>32284046.00</td>
      <td>28516545.00</td>
      <td>24743946.00</td>
      <td>18628700.00</td>
      <td>13375121.00</td>
      <td>9204938.00</td>
      <td>6843607.00</td>
      <td>527968.00</td>
      <td>63.82</td>
      <td>1.02</td>
      <td>0.42</td>
    </tr>
    <tr>
      <th>208</th>
      <td>74</td>
      <td>ZWE</td>
      <td>Zimbabwe</td>
      <td>Harare</td>
      <td>Africa</td>
      <td>16320537.00</td>
      <td>15669666.00</td>
      <td>14154937.00</td>
      <td>12839771.00</td>
      <td>11834676.00</td>
      <td>10113893.00</td>
      <td>7049926.00</td>
      <td>5202918.00</td>
      <td>390757.00</td>
      <td>41.77</td>
      <td>1.02</td>
      <td>0.20</td>
    </tr>
  </tbody>
</table>
<p>209 rows × 17 columns</p>
</div>




```python
df.nunique()
```




    Rank                           209
    CCA3                           209
    Country                        209
    Capital                        209
    Continent                        6
    2022 Population                209
    2020 Population                209
    2015 Population                209
    2010 Population                209
    2000 Population                209
    1990 Population                209
    1980 Population                209
    1970 Population                209
    Area (km²)                     208
    Density (per km²)              209
    Growth Rate                    163
    World Population Percentage     67
    dtype: int64




```python
df.sort_values(by="World Population Percentage", ascending=False).head(20)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>40</th>
      <td>1</td>
      <td>CHN</td>
      <td>China</td>
      <td>Beijing</td>
      <td>Asia</td>
      <td>1425887337.00</td>
      <td>1424929781.00</td>
      <td>1393715448.00</td>
      <td>1348191368.00</td>
      <td>1264099069.00</td>
      <td>1153704252.00</td>
      <td>982372466.00</td>
      <td>822534450.00</td>
      <td>9706961.00</td>
      <td>146.89</td>
      <td>1.00</td>
      <td>17.88</td>
    </tr>
    <tr>
      <th>198</th>
      <td>3</td>
      <td>USA</td>
      <td>United States</td>
      <td>Washington, D.C.</td>
      <td>North America</td>
      <td>338289857.00</td>
      <td>335942003.00</td>
      <td>324607776.00</td>
      <td>311182845.00</td>
      <td>282398554.00</td>
      <td>248083732.00</td>
      <td>223140018.00</td>
      <td>200328340.00</td>
      <td>9372610.00</td>
      <td>36.09</td>
      <td>1.00</td>
      <td>4.24</td>
    </tr>
    <tr>
      <th>84</th>
      <td>4</td>
      <td>IDN</td>
      <td>Indonesia</td>
      <td>Jakarta</td>
      <td>Asia</td>
      <td>275501339.00</td>
      <td>271857970.00</td>
      <td>259091970.00</td>
      <td>244016173.00</td>
      <td>214072421.00</td>
      <td>182159874.00</td>
      <td>148177096.00</td>
      <td>115228394.00</td>
      <td>1904569.00</td>
      <td>144.65</td>
      <td>1.01</td>
      <td>3.45</td>
    </tr>
    <tr>
      <th>141</th>
      <td>5</td>
      <td>PAK</td>
      <td>Pakistan</td>
      <td>Islamabad</td>
      <td>Asia</td>
      <td>235824862.00</td>
      <td>227196741.00</td>
      <td>210969298.00</td>
      <td>194454498.00</td>
      <td>154369924.00</td>
      <td>115414069.00</td>
      <td>80624057.00</td>
      <td>59290872.00</td>
      <td>881912.00</td>
      <td>267.40</td>
      <td>1.02</td>
      <td>2.96</td>
    </tr>
    <tr>
      <th>135</th>
      <td>6</td>
      <td>NGA</td>
      <td>Nigeria</td>
      <td>Abuja</td>
      <td>Africa</td>
      <td>218541212.00</td>
      <td>208327405.00</td>
      <td>183995785.00</td>
      <td>160952853.00</td>
      <td>122851984.00</td>
      <td>95214257.00</td>
      <td>72951439.00</td>
      <td>55569264.00</td>
      <td>923768.00</td>
      <td>236.58</td>
      <td>1.02</td>
      <td>2.74</td>
    </tr>
    <tr>
      <th>26</th>
      <td>7</td>
      <td>BRA</td>
      <td>Brazil</td>
      <td>Brasilia</td>
      <td>South America</td>
      <td>215313498.00</td>
      <td>213196304.00</td>
      <td>205188205.00</td>
      <td>196353492.00</td>
      <td>175873720.00</td>
      <td>150706446.00</td>
      <td>122288383.00</td>
      <td>96369875.00</td>
      <td>8515767.00</td>
      <td>25.28</td>
      <td>1.00</td>
      <td>2.70</td>
    </tr>
    <tr>
      <th>15</th>
      <td>8</td>
      <td>BGD</td>
      <td>Bangladesh</td>
      <td>Dhaka</td>
      <td>Asia</td>
      <td>171186372.00</td>
      <td>167420951.00</td>
      <td>157830000.00</td>
      <td>148391139.00</td>
      <td>129193327.00</td>
      <td>107147651.00</td>
      <td>83929765.00</td>
      <td>67541860.00</td>
      <td>147570.00</td>
      <td>1160.04</td>
      <td>1.01</td>
      <td>2.15</td>
    </tr>
    <tr>
      <th>155</th>
      <td>9</td>
      <td>RUS</td>
      <td>Russia</td>
      <td>Moscow</td>
      <td>Europe</td>
      <td>144713314.00</td>
      <td>145617329.00</td>
      <td>144668389.00</td>
      <td>143242599.00</td>
      <td>146844839.00</td>
      <td>148005704.00</td>
      <td>138257420.00</td>
      <td>130093010.00</td>
      <td>17098242.00</td>
      <td>8.46</td>
      <td>1.00</td>
      <td>1.81</td>
    </tr>
    <tr>
      <th>118</th>
      <td>10</td>
      <td>MEX</td>
      <td>Mexico</td>
      <td>Mexico City</td>
      <td>North America</td>
      <td>127504125.00</td>
      <td>125998302.00</td>
      <td>120149897.00</td>
      <td>112532401.00</td>
      <td>97873442.00</td>
      <td>81720428.00</td>
      <td>67705186.00</td>
      <td>50289306.00</td>
      <td>1964375.00</td>
      <td>64.91</td>
      <td>1.01</td>
      <td>1.60</td>
    </tr>
    <tr>
      <th>91</th>
      <td>11</td>
      <td>JPN</td>
      <td>Japan</td>
      <td>Tokyo</td>
      <td>Asia</td>
      <td>123951692.00</td>
      <td>125244761.00</td>
      <td>127250933.00</td>
      <td>128105431.00</td>
      <td>126803861.00</td>
      <td>123686321.00</td>
      <td>117624196.00</td>
      <td>105416839.00</td>
      <td>377930.00</td>
      <td>327.98</td>
      <td>0.99</td>
      <td>1.55</td>
    </tr>
    <tr>
      <th>59</th>
      <td>12</td>
      <td>ETH</td>
      <td>Ethiopia</td>
      <td>Addis Ababa</td>
      <td>Africa</td>
      <td>123379924.00</td>
      <td>117190911.00</td>
      <td>102471895.00</td>
      <td>89237791.00</td>
      <td>67031867.00</td>
      <td>47878073.00</td>
      <td>34945469.00</td>
      <td>28308246.00</td>
      <td>1104300.00</td>
      <td>111.73</td>
      <td>1.03</td>
      <td>1.55</td>
    </tr>
    <tr>
      <th>147</th>
      <td>13</td>
      <td>PHL</td>
      <td>Philippines</td>
      <td>Manila</td>
      <td>Asia</td>
      <td>115559009.00</td>
      <td>112190977.00</td>
      <td>103031365.00</td>
      <td>94636700.00</td>
      <td>77958223.00</td>
      <td>61558898.00</td>
      <td>48419546.00</td>
      <td>37435586.00</td>
      <td>342353.00</td>
      <td>337.54</td>
      <td>1.01</td>
      <td>1.45</td>
    </tr>
    <tr>
      <th>55</th>
      <td>14</td>
      <td>EGY</td>
      <td>Egypt</td>
      <td>Cairo</td>
      <td>Africa</td>
      <td>110990103.00</td>
      <td>107465134.00</td>
      <td>97723799.00</td>
      <td>87252413.00</td>
      <td>71371371.00</td>
      <td>57214630.00</td>
      <td>43748556.00</td>
      <td>34781986.00</td>
      <td>1002450.00</td>
      <td>110.72</td>
      <td>1.02</td>
      <td>1.39</td>
    </tr>
    <tr>
      <th>53</th>
      <td>15</td>
      <td>COD</td>
      <td>DR Congo</td>
      <td>Kinshasa</td>
      <td>Africa</td>
      <td>99010212.00</td>
      <td>92853164.00</td>
      <td>78656904.00</td>
      <td>66391257.00</td>
      <td>48616317.00</td>
      <td>35987541.00</td>
      <td>26708686.00</td>
      <td>20151733.00</td>
      <td>2344858.00</td>
      <td>42.22</td>
      <td>1.03</td>
      <td>1.24</td>
    </tr>
    <tr>
      <th>204</th>
      <td>16</td>
      <td>VNM</td>
      <td>Vietnam</td>
      <td>Hanoi</td>
      <td>Asia</td>
      <td>98186856.00</td>
      <td>96648685.00</td>
      <td>92191398.00</td>
      <td>87411012.00</td>
      <td>79001142.00</td>
      <td>66912613.00</td>
      <td>52968270.00</td>
      <td>41928849.00</td>
      <td>331212.00</td>
      <td>296.45</td>
      <td>1.01</td>
      <td>1.23</td>
    </tr>
    <tr>
      <th>85</th>
      <td>17</td>
      <td>IRN</td>
      <td>Iran</td>
      <td>Tehran</td>
      <td>Asia</td>
      <td>88550570.00</td>
      <td>87290193.00</td>
      <td>81790841.00</td>
      <td>75373855.00</td>
      <td>65544383.00</td>
      <td>55793629.00</td>
      <td>38520664.00</td>
      <td>28449705.00</td>
      <td>1648195.00</td>
      <td>53.73</td>
      <td>1.01</td>
      <td>1.11</td>
    </tr>
    <tr>
      <th>190</th>
      <td>18</td>
      <td>TUR</td>
      <td>Turkey</td>
      <td>Ankara</td>
      <td>Asia</td>
      <td>85341241.00</td>
      <td>84135428.00</td>
      <td>79646178.00</td>
      <td>73195345.00</td>
      <td>64113547.00</td>
      <td>54324142.00</td>
      <td>44089069.00</td>
      <td>35540990.00</td>
      <td>783562.00</td>
      <td>108.91</td>
      <td>1.01</td>
      <td>1.07</td>
    </tr>
    <tr>
      <th>68</th>
      <td>19</td>
      <td>DEU</td>
      <td>Germany</td>
      <td>Berlin</td>
      <td>Europe</td>
      <td>83369843.00</td>
      <td>83328988.00</td>
      <td>82073226.00</td>
      <td>81325090.00</td>
      <td>81551677.00</td>
      <td>79370196.00</td>
      <td>77786703.00</td>
      <td>78294583.00</td>
      <td>357114.00</td>
      <td>233.45</td>
      <td>1.00</td>
      <td>1.05</td>
    </tr>
    <tr>
      <th>197</th>
      <td>21</td>
      <td>GBR</td>
      <td>United Kingdom</td>
      <td>London</td>
      <td>Europe</td>
      <td>67508936.00</td>
      <td>67059474.00</td>
      <td>65224364.00</td>
      <td>62760039.00</td>
      <td>58850043.00</td>
      <td>57210442.00</td>
      <td>56326328.00</td>
      <td>55650166.00</td>
      <td>242900.00</td>
      <td>277.93</td>
      <td>1.00</td>
      <td>0.85</td>
    </tr>
    <tr>
      <th>185</th>
      <td>22</td>
      <td>TZA</td>
      <td>Tanzania</td>
      <td>Dodoma</td>
      <td>Africa</td>
      <td>65497748.00</td>
      <td>61704518.00</td>
      <td>52542823.00</td>
      <td>45110527.00</td>
      <td>34463704.00</td>
      <td>26206012.00</td>
      <td>19297659.00</td>
      <td>13618192.00</td>
      <td>945087.00</td>
      <td>69.30</td>
      <td>1.03</td>
      <td>0.82</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.sort_values(by="2022 Population", ascending=False).head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>40</th>
      <td>1</td>
      <td>CHN</td>
      <td>China</td>
      <td>Beijing</td>
      <td>Asia</td>
      <td>1425887337.00</td>
      <td>1424929781.00</td>
      <td>1393715448.00</td>
      <td>1348191368.00</td>
      <td>1264099069.00</td>
      <td>1153704252.00</td>
      <td>982372466.00</td>
      <td>822534450.00</td>
      <td>9706961.00</td>
      <td>146.89</td>
      <td>1.00</td>
      <td>17.88</td>
    </tr>
    <tr>
      <th>198</th>
      <td>3</td>
      <td>USA</td>
      <td>United States</td>
      <td>Washington, D.C.</td>
      <td>North America</td>
      <td>338289857.00</td>
      <td>335942003.00</td>
      <td>324607776.00</td>
      <td>311182845.00</td>
      <td>282398554.00</td>
      <td>248083732.00</td>
      <td>223140018.00</td>
      <td>200328340.00</td>
      <td>9372610.00</td>
      <td>36.09</td>
      <td>1.00</td>
      <td>4.24</td>
    </tr>
    <tr>
      <th>84</th>
      <td>4</td>
      <td>IDN</td>
      <td>Indonesia</td>
      <td>Jakarta</td>
      <td>Asia</td>
      <td>275501339.00</td>
      <td>271857970.00</td>
      <td>259091970.00</td>
      <td>244016173.00</td>
      <td>214072421.00</td>
      <td>182159874.00</td>
      <td>148177096.00</td>
      <td>115228394.00</td>
      <td>1904569.00</td>
      <td>144.65</td>
      <td>1.01</td>
      <td>3.45</td>
    </tr>
    <tr>
      <th>141</th>
      <td>5</td>
      <td>PAK</td>
      <td>Pakistan</td>
      <td>Islamabad</td>
      <td>Asia</td>
      <td>235824862.00</td>
      <td>227196741.00</td>
      <td>210969298.00</td>
      <td>194454498.00</td>
      <td>154369924.00</td>
      <td>115414069.00</td>
      <td>80624057.00</td>
      <td>59290872.00</td>
      <td>881912.00</td>
      <td>267.40</td>
      <td>1.02</td>
      <td>2.96</td>
    </tr>
    <tr>
      <th>135</th>
      <td>6</td>
      <td>NGA</td>
      <td>Nigeria</td>
      <td>Abuja</td>
      <td>Africa</td>
      <td>218541212.00</td>
      <td>208327405.00</td>
      <td>183995785.00</td>
      <td>160952853.00</td>
      <td>122851984.00</td>
      <td>95214257.00</td>
      <td>72951439.00</td>
      <td>55569264.00</td>
      <td>923768.00</td>
      <td>236.58</td>
      <td>1.02</td>
      <td>2.74</td>
    </tr>
    <tr>
      <th>26</th>
      <td>7</td>
      <td>BRA</td>
      <td>Brazil</td>
      <td>Brasilia</td>
      <td>South America</td>
      <td>215313498.00</td>
      <td>213196304.00</td>
      <td>205188205.00</td>
      <td>196353492.00</td>
      <td>175873720.00</td>
      <td>150706446.00</td>
      <td>122288383.00</td>
      <td>96369875.00</td>
      <td>8515767.00</td>
      <td>25.28</td>
      <td>1.00</td>
      <td>2.70</td>
    </tr>
    <tr>
      <th>15</th>
      <td>8</td>
      <td>BGD</td>
      <td>Bangladesh</td>
      <td>Dhaka</td>
      <td>Asia</td>
      <td>171186372.00</td>
      <td>167420951.00</td>
      <td>157830000.00</td>
      <td>148391139.00</td>
      <td>129193327.00</td>
      <td>107147651.00</td>
      <td>83929765.00</td>
      <td>67541860.00</td>
      <td>147570.00</td>
      <td>1160.04</td>
      <td>1.01</td>
      <td>2.15</td>
    </tr>
    <tr>
      <th>155</th>
      <td>9</td>
      <td>RUS</td>
      <td>Russia</td>
      <td>Moscow</td>
      <td>Europe</td>
      <td>144713314.00</td>
      <td>145617329.00</td>
      <td>144668389.00</td>
      <td>143242599.00</td>
      <td>146844839.00</td>
      <td>148005704.00</td>
      <td>138257420.00</td>
      <td>130093010.00</td>
      <td>17098242.00</td>
      <td>8.46</td>
      <td>1.00</td>
      <td>1.81</td>
    </tr>
    <tr>
      <th>118</th>
      <td>10</td>
      <td>MEX</td>
      <td>Mexico</td>
      <td>Mexico City</td>
      <td>North America</td>
      <td>127504125.00</td>
      <td>125998302.00</td>
      <td>120149897.00</td>
      <td>112532401.00</td>
      <td>97873442.00</td>
      <td>81720428.00</td>
      <td>67705186.00</td>
      <td>50289306.00</td>
      <td>1964375.00</td>
      <td>64.91</td>
      <td>1.01</td>
      <td>1.60</td>
    </tr>
    <tr>
      <th>91</th>
      <td>11</td>
      <td>JPN</td>
      <td>Japan</td>
      <td>Tokyo</td>
      <td>Asia</td>
      <td>123951692.00</td>
      <td>125244761.00</td>
      <td>127250933.00</td>
      <td>128105431.00</td>
      <td>126803861.00</td>
      <td>123686321.00</td>
      <td>117624196.00</td>
      <td>105416839.00</td>
      <td>377930.00</td>
      <td>327.98</td>
      <td>0.99</td>
      <td>1.55</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 209 entries, 0 to 208
    Data columns (total 17 columns):
     #   Column                       Non-Null Count  Dtype  
    ---  ------                       --------------  -----  
     0   Rank                         209 non-null    int64  
     1   CCA3                         209 non-null    object 
     2   Country                      209 non-null    object 
     3   Capital                      209 non-null    object 
     4   Continent                    209 non-null    object 
     5   2022 Population              209 non-null    object 
     6   2020 Population              209 non-null    object 
     7   2015 Population              209 non-null    object 
     8   2010 Population              209 non-null    object 
     9   2000 Population              209 non-null    object 
     10  1990 Population              209 non-null    object 
     11  1980 Population              209 non-null    object 
     12  1970 Population              209 non-null    object 
     13  Area (km²)                   209 non-null    object 
     14  Density (per km²)            209 non-null    object 
     15  Growth Rate                  209 non-null    object 
     16  World Population Percentage  209 non-null    float64
    dtypes: float64(1), int64(1), object(15)
    memory usage: 27.9+ KB
    


```python
df["2022 Population"] = df["2022 Population"].apply(lambda x: float(x))

df["2020 Population"] = df["2020 Population"].apply(lambda x: float(x))

df["2015 Population"] = df["2015 Population"].apply(lambda x: float(x))

df["2010 Population"] = df["2010 Population"].apply(lambda x: float(x))

df["2000 Population"] = df["2000 Population"].apply(lambda x: float(x))

df["1990 Population"] = df["1990 Population"].apply(lambda x: float(x))

df["1980 Population"] = df["1980 Population"].apply(lambda x: float(x))

df["1970 Population"] = df["1970 Population"].apply(lambda x: float(x))

df["Area (km²)"] = df["Area (km²)"].apply(lambda x: int(x))

df["Density (per km²)"] = df["Density (per km²)"].apply(lambda x: int(x))

df["Growth Rate"] = df["Growth Rate"].apply(lambda x: int(x))
```


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 209 entries, 0 to 208
    Data columns (total 17 columns):
     #   Column                       Non-Null Count  Dtype  
    ---  ------                       --------------  -----  
     0   Rank                         209 non-null    int64  
     1   CCA3                         209 non-null    object 
     2   Country                      209 non-null    object 
     3   Capital                      209 non-null    object 
     4   Continent                    209 non-null    object 
     5   2022 Population              209 non-null    float64
     6   2020 Population              209 non-null    float64
     7   2015 Population              209 non-null    float64
     8   2010 Population              209 non-null    float64
     9   2000 Population              209 non-null    float64
     10  1990 Population              209 non-null    float64
     11  1980 Population              209 non-null    float64
     12  1970 Population              209 non-null    float64
     13  Area (km²)                   209 non-null    int64  
     14  Density (per km²)            209 non-null    int64  
     15  Growth Rate                  209 non-null    int64  
     16  World Population Percentage  209 non-null    float64
    dtypes: float64(9), int64(4), object(4)
    memory usage: 27.9+ KB
    


```python
df.corr(numeric_only = True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Rank</th>
      <td>1.00</td>
      <td>-0.39</td>
      <td>-0.38</td>
      <td>-0.37</td>
      <td>-0.37</td>
      <td>-0.35</td>
      <td>-0.34</td>
      <td>-0.33</td>
      <td>-0.33</td>
      <td>-0.38</td>
      <td>0.13</td>
      <td>-0.16</td>
      <td>-0.39</td>
    </tr>
    <tr>
      <th>2022 Population</th>
      <td>-0.39</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.98</td>
      <td>0.52</td>
      <td>-0.04</td>
      <td>0.07</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>2020 Population</th>
      <td>-0.38</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.98</td>
      <td>0.52</td>
      <td>-0.04</td>
      <td>0.06</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>2015 Population</th>
      <td>-0.37</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.52</td>
      <td>-0.04</td>
      <td>0.06</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>2010 Population</th>
      <td>-0.37</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.52</td>
      <td>-0.04</td>
      <td>0.05</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>2000 Population</th>
      <td>-0.35</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.52</td>
      <td>-0.03</td>
      <td>0.04</td>
      <td>1.00</td>
    </tr>
    <tr>
      <th>1990 Population</th>
      <td>-0.34</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.52</td>
      <td>-0.03</td>
      <td>0.03</td>
      <td>0.99</td>
    </tr>
    <tr>
      <th>1980 Population</th>
      <td>-0.33</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.53</td>
      <td>-0.03</td>
      <td>0.02</td>
      <td>0.99</td>
    </tr>
    <tr>
      <th>1970 Population</th>
      <td>-0.33</td>
      <td>0.98</td>
      <td>0.98</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.54</td>
      <td>-0.03</td>
      <td>0.01</td>
      <td>0.98</td>
    </tr>
    <tr>
      <th>Area (km²)</th>
      <td>-0.38</td>
      <td>0.52</td>
      <td>0.52</td>
      <td>0.52</td>
      <td>0.52</td>
      <td>0.52</td>
      <td>0.52</td>
      <td>0.53</td>
      <td>0.54</td>
      <td>1.00</td>
      <td>-0.07</td>
      <td>0.03</td>
      <td>0.52</td>
    </tr>
    <tr>
      <th>Density (per km²)</th>
      <td>0.13</td>
      <td>-0.04</td>
      <td>-0.04</td>
      <td>-0.04</td>
      <td>-0.04</td>
      <td>-0.03</td>
      <td>-0.03</td>
      <td>-0.03</td>
      <td>-0.03</td>
      <td>-0.07</td>
      <td>1.00</td>
      <td>-0.10</td>
      <td>-0.04</td>
    </tr>
    <tr>
      <th>Growth Rate</th>
      <td>-0.16</td>
      <td>0.07</td>
      <td>0.06</td>
      <td>0.06</td>
      <td>0.05</td>
      <td>0.04</td>
      <td>0.03</td>
      <td>0.02</td>
      <td>0.01</td>
      <td>0.03</td>
      <td>-0.10</td>
      <td>1.00</td>
      <td>0.07</td>
    </tr>
    <tr>
      <th>World Population Percentage</th>
      <td>-0.39</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>1.00</td>
      <td>0.99</td>
      <td>0.99</td>
      <td>0.98</td>
      <td>0.52</td>
      <td>-0.04</td>
      <td>0.07</td>
      <td>1.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
sns.heatmap(df.corr(numeric_only = True), annot = False, cmap='coolwarm')

plt.rcParams['figure.figsize'] = (20,10)

plt.show()
```


    
![png](output_21_0.png)
    



```python
df2=df.drop(columns=['CCA3','Country','Capital']) 

df3=df2.groupby('Continent').mean(numeric_only=True).sort_values(by="2022 Population", ascending=False)

df3 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
    <tr>
      <th>Continent</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Asia</th>
      <td>75.81</td>
      <td>74014123.44</td>
      <td>73166475.70</td>
      <td>70203359.07</td>
      <td>66695706.81</td>
      <td>59902972.09</td>
      <td>52408451.47</td>
      <td>43423636.49</td>
      <td>35590784.79</td>
      <td>647329.16</td>
      <td>1129.02</td>
      <td>0.88</td>
      <td>0.93</td>
    </tr>
    <tr>
      <th>South America</th>
      <td>107.25</td>
      <td>29720074.00</td>
      <td>29342410.67</td>
      <td>27957079.33</td>
      <td>26628926.67</td>
      <td>23832618.17</td>
      <td>20399536.92</td>
      <td>16700197.33</td>
      <td>13390535.58</td>
      <td>1314599.08</td>
      <td>17.58</td>
      <td>0.92</td>
      <td>0.37</td>
    </tr>
    <tr>
      <th>Africa</th>
      <td>91.85</td>
      <td>26961948.00</td>
      <td>25725500.10</td>
      <td>22715954.10</td>
      <td>19975819.02</td>
      <td>15558198.27</td>
      <td>12158419.56</td>
      <td>9139807.92</td>
      <td>6969879.85</td>
      <td>561063.96</td>
      <td>133.98</td>
      <td>1.00</td>
      <td>0.34</td>
    </tr>
    <tr>
      <th>Europe</th>
      <td>122.04</td>
      <td>15811725.04</td>
      <td>15875241.48</td>
      <td>15785573.39</td>
      <td>15660596.24</td>
      <td>15458519.15</td>
      <td>15335326.54</td>
      <td>14728110.76</td>
      <td>13945879.17</td>
      <td>488924.35</td>
      <td>705.72</td>
      <td>0.54</td>
      <td>0.20</td>
    </tr>
    <tr>
      <th>North America</th>
      <td>161.71</td>
      <td>15682571.45</td>
      <td>15523631.84</td>
      <td>14898137.58</td>
      <td>14173064.71</td>
      <td>12687504.63</td>
      <td>10989680.97</td>
      <td>9606051.66</td>
      <td>8225963.82</td>
      <td>637580.45</td>
      <td>272.03</td>
      <td>0.74</td>
      <td>0.20</td>
    </tr>
    <tr>
      <th>Oceania</th>
      <td>187.00</td>
      <td>2046386.32</td>
      <td>1996157.00</td>
      <td>1835704.05</td>
      <td>1685646.55</td>
      <td>1418320.55</td>
      <td>1214933.14</td>
      <td>1041272.18</td>
      <td>884950.18</td>
      <td>387028.27</td>
      <td>136.27</td>
      <td>0.82</td>
      <td>0.03</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3.plot()
```




    <Axes: xlabel='Continent'>




    
![png](output_23_1.png)
    



```python
df4=df3.drop(columns=['Area (km²)','Density (per km²)','Growth Rate','World Population Percentage']) 

df4 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
    </tr>
    <tr>
      <th>Continent</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Asia</th>
      <td>75.81</td>
      <td>74014123.44</td>
      <td>73166475.70</td>
      <td>70203359.07</td>
      <td>66695706.81</td>
      <td>59902972.09</td>
      <td>52408451.47</td>
      <td>43423636.49</td>
      <td>35590784.79</td>
    </tr>
    <tr>
      <th>South America</th>
      <td>107.25</td>
      <td>29720074.00</td>
      <td>29342410.67</td>
      <td>27957079.33</td>
      <td>26628926.67</td>
      <td>23832618.17</td>
      <td>20399536.92</td>
      <td>16700197.33</td>
      <td>13390535.58</td>
    </tr>
    <tr>
      <th>Africa</th>
      <td>91.85</td>
      <td>26961948.00</td>
      <td>25725500.10</td>
      <td>22715954.10</td>
      <td>19975819.02</td>
      <td>15558198.27</td>
      <td>12158419.56</td>
      <td>9139807.92</td>
      <td>6969879.85</td>
    </tr>
    <tr>
      <th>Europe</th>
      <td>122.04</td>
      <td>15811725.04</td>
      <td>15875241.48</td>
      <td>15785573.39</td>
      <td>15660596.24</td>
      <td>15458519.15</td>
      <td>15335326.54</td>
      <td>14728110.76</td>
      <td>13945879.17</td>
    </tr>
    <tr>
      <th>North America</th>
      <td>161.71</td>
      <td>15682571.45</td>
      <td>15523631.84</td>
      <td>14898137.58</td>
      <td>14173064.71</td>
      <td>12687504.63</td>
      <td>10989680.97</td>
      <td>9606051.66</td>
      <td>8225963.82</td>
    </tr>
    <tr>
      <th>Oceania</th>
      <td>187.00</td>
      <td>2046386.32</td>
      <td>1996157.00</td>
      <td>1835704.05</td>
      <td>1685646.55</td>
      <td>1418320.55</td>
      <td>1214933.14</td>
      <td>1041272.18</td>
      <td>884950.18</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4.boxplot()
```




    <Axes: >




    
![png](output_25_1.png)
    



```python
df[df['Continent'].str.contains('Oceania')]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>213</td>
      <td>ASM</td>
      <td>American Samoa</td>
      <td>Pago Pago</td>
      <td>Oceania</td>
      <td>44273.00</td>
      <td>46189.00</td>
      <td>51368.00</td>
      <td>54849.00</td>
      <td>58230.00</td>
      <td>47818.00</td>
      <td>32886.00</td>
      <td>27075.00</td>
      <td>199</td>
      <td>222</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>11</th>
      <td>55</td>
      <td>AUS</td>
      <td>Australia</td>
      <td>Canberra</td>
      <td>Oceania</td>
      <td>26177413.00</td>
      <td>25670051.00</td>
      <td>23820236.00</td>
      <td>22019168.00</td>
      <td>19017963.00</td>
      <td>17048003.00</td>
      <td>14706322.00</td>
      <td>12595034.00</td>
      <td>7692024</td>
      <td>3</td>
      <td>1</td>
      <td>0.33</td>
    </tr>
    <tr>
      <th>42</th>
      <td>223</td>
      <td>COK</td>
      <td>Cook Islands</td>
      <td>Avarua</td>
      <td>Oceania</td>
      <td>17011.00</td>
      <td>17029.00</td>
      <td>17695.00</td>
      <td>17212.00</td>
      <td>15897.00</td>
      <td>17123.00</td>
      <td>17651.00</td>
      <td>20470.00</td>
      <td>236</td>
      <td>72</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>62</th>
      <td>162</td>
      <td>FJI</td>
      <td>Fiji</td>
      <td>Suva</td>
      <td>Oceania</td>
      <td>929766.00</td>
      <td>920422.00</td>
      <td>917200.00</td>
      <td>905169.00</td>
      <td>832509.00</td>
      <td>780430.00</td>
      <td>644582.00</td>
      <td>527634.00</td>
      <td>18272</td>
      <td>50</td>
      <td>1</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>66</th>
      <td>183</td>
      <td>PYF</td>
      <td>French Polynesia</td>
      <td>Papeete</td>
      <td>Oceania</td>
      <td>306279.00</td>
      <td>301920.00</td>
      <td>291787.00</td>
      <td>283788.00</td>
      <td>250927.00</td>
      <td>211089.00</td>
      <td>163591.00</td>
      <td>117891.00</td>
      <td>4167</td>
      <td>73</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>75</th>
      <td>191</td>
      <td>GUM</td>
      <td>Guam</td>
      <td>Hagåtña</td>
      <td>Oceania</td>
      <td>171774.00</td>
      <td>169231.00</td>
      <td>167978.00</td>
      <td>164905.00</td>
      <td>160188.00</td>
      <td>138263.00</td>
      <td>110286.00</td>
      <td>88300.00</td>
      <td>549</td>
      <td>312</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>96</th>
      <td>192</td>
      <td>KIR</td>
      <td>Kiribati</td>
      <td>Tarawa</td>
      <td>Oceania</td>
      <td>131232.00</td>
      <td>126463.00</td>
      <td>116707.00</td>
      <td>107995.00</td>
      <td>88826.00</td>
      <td>75124.00</td>
      <td>60813.00</td>
      <td>57437.00</td>
      <td>811</td>
      <td>161</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>113</th>
      <td>215</td>
      <td>MHL</td>
      <td>Marshall Islands</td>
      <td>Majuro</td>
      <td>Oceania</td>
      <td>41569.00</td>
      <td>43413.00</td>
      <td>49410.00</td>
      <td>53416.00</td>
      <td>54224.00</td>
      <td>46047.00</td>
      <td>31988.00</td>
      <td>23969.00</td>
      <td>181</td>
      <td>229</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>119</th>
      <td>194</td>
      <td>FSM</td>
      <td>Micronesia</td>
      <td>Palikir</td>
      <td>Oceania</td>
      <td>114164.00</td>
      <td>112106.00</td>
      <td>109462.00</td>
      <td>107588.00</td>
      <td>111709.00</td>
      <td>98603.00</td>
      <td>76299.00</td>
      <td>58989.00</td>
      <td>702</td>
      <td>162</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>128</th>
      <td>225</td>
      <td>NRU</td>
      <td>Nauru</td>
      <td>Yaren</td>
      <td>Oceania</td>
      <td>12668.00</td>
      <td>12315.00</td>
      <td>11185.00</td>
      <td>10241.00</td>
      <td>10377.00</td>
      <td>9598.00</td>
      <td>7635.00</td>
      <td>6663.00</td>
      <td>21</td>
      <td>603</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>131</th>
      <td>185</td>
      <td>NCL</td>
      <td>New Caledonia</td>
      <td>Nouméa</td>
      <td>Oceania</td>
      <td>289950.00</td>
      <td>286403.00</td>
      <td>283032.00</td>
      <td>261426.00</td>
      <td>221537.00</td>
      <td>177264.00</td>
      <td>148599.00</td>
      <td>110982.00</td>
      <td>18575</td>
      <td>15</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>132</th>
      <td>123</td>
      <td>NZL</td>
      <td>New Zealand</td>
      <td>Wellington</td>
      <td>Oceania</td>
      <td>5185288.00</td>
      <td>5061133.00</td>
      <td>4590590.00</td>
      <td>4346338.00</td>
      <td>3855266.00</td>
      <td>3397389.00</td>
      <td>3147168.00</td>
      <td>2824061.00</td>
      <td>270467</td>
      <td>19</td>
      <td>1</td>
      <td>0.07</td>
    </tr>
    <tr>
      <th>136</th>
      <td>232</td>
      <td>NIU</td>
      <td>Niue</td>
      <td>Alofi</td>
      <td>Oceania</td>
      <td>1934.00</td>
      <td>1942.00</td>
      <td>1847.00</td>
      <td>1812.00</td>
      <td>2074.00</td>
      <td>2533.00</td>
      <td>3637.00</td>
      <td>5185.00</td>
      <td>260</td>
      <td>7</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>139</th>
      <td>210</td>
      <td>NFK</td>
      <td>Northern Mariana Islands</td>
      <td>Saipan</td>
      <td>Oceania</td>
      <td>49551.00</td>
      <td>49587.00</td>
      <td>51514.00</td>
      <td>54087.00</td>
      <td>80338.00</td>
      <td>48002.00</td>
      <td>17613.00</td>
      <td>10143.00</td>
      <td>464</td>
      <td>106</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>144</th>
      <td>93</td>
      <td>PNG</td>
      <td>Papua New Guinea</td>
      <td>Port Moresby</td>
      <td>Oceania</td>
      <td>10142619.00</td>
      <td>9749640.00</td>
      <td>8682174.00</td>
      <td>7583269.00</td>
      <td>5508297.00</td>
      <td>3864972.00</td>
      <td>3104788.00</td>
      <td>2489059.00</td>
      <td>462840</td>
      <td>21</td>
      <td>1</td>
      <td>0.13</td>
    </tr>
    <tr>
      <th>163</th>
      <td>188</td>
      <td>WSM</td>
      <td>Samoa</td>
      <td>Apia</td>
      <td>Oceania</td>
      <td>222382.00</td>
      <td>214929.00</td>
      <td>203571.00</td>
      <td>194672.00</td>
      <td>184008.00</td>
      <td>168186.00</td>
      <td>164905.00</td>
      <td>142771.00</td>
      <td>2842</td>
      <td>78</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>173</th>
      <td>166</td>
      <td>SLB</td>
      <td>Solomon Islands</td>
      <td>Honiara</td>
      <td>Oceania</td>
      <td>724273.00</td>
      <td>691191.00</td>
      <td>612660.00</td>
      <td>540394.00</td>
      <td>429978.00</td>
      <td>324171.00</td>
      <td>233668.00</td>
      <td>172833.00</td>
      <td>28896</td>
      <td>25</td>
      <td>1</td>
      <td>0.01</td>
    </tr>
    <tr>
      <th>187</th>
      <td>233</td>
      <td>TKL</td>
      <td>Tokelau</td>
      <td>Nukunonu</td>
      <td>Oceania</td>
      <td>1871.00</td>
      <td>1827.00</td>
      <td>1454.00</td>
      <td>1367.00</td>
      <td>1666.00</td>
      <td>1669.00</td>
      <td>1647.00</td>
      <td>1714.00</td>
      <td>12</td>
      <td>155</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>188</th>
      <td>197</td>
      <td>TON</td>
      <td>Tonga</td>
      <td>Nuku‘alofa</td>
      <td>Oceania</td>
      <td>106858.00</td>
      <td>105254.00</td>
      <td>106122.00</td>
      <td>107383.00</td>
      <td>102603.00</td>
      <td>98727.00</td>
      <td>96708.00</td>
      <td>86484.00</td>
      <td>747</td>
      <td>143</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>193</th>
      <td>227</td>
      <td>TUV</td>
      <td>Tuvalu</td>
      <td>Funafuti</td>
      <td>Oceania</td>
      <td>11312.00</td>
      <td>11069.00</td>
      <td>10877.00</td>
      <td>10550.00</td>
      <td>9638.00</td>
      <td>9182.00</td>
      <td>7731.00</td>
      <td>5814.00</td>
      <td>26</td>
      <td>435</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>202</th>
      <td>181</td>
      <td>VUT</td>
      <td>Vanuatu</td>
      <td>Port-Vila</td>
      <td>Oceania</td>
      <td>326740.00</td>
      <td>311685.00</td>
      <td>276438.00</td>
      <td>245453.00</td>
      <td>192074.00</td>
      <td>150882.00</td>
      <td>118156.00</td>
      <td>87019.00</td>
      <td>12189</td>
      <td>26</td>
      <td>1</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>205</th>
      <td>226</td>
      <td>WLF</td>
      <td>Wallis and Futuna</td>
      <td>Mata-Utu</td>
      <td>Oceania</td>
      <td>11572.00</td>
      <td>11655.00</td>
      <td>12182.00</td>
      <td>13142.00</td>
      <td>14723.00</td>
      <td>13454.00</td>
      <td>11315.00</td>
      <td>9377.00</td>
      <td>142</td>
      <td>81</td>
      <td>0</td>
      <td>0.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
df5 = df[df['Country'].str.contains('Australia')]

df5
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Rank</th>
      <th>CCA3</th>
      <th>Country</th>
      <th>Capital</th>
      <th>Continent</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
      <th>Area (km²)</th>
      <th>Density (per km²)</th>
      <th>Growth Rate</th>
      <th>World Population Percentage</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>55</td>
      <td>AUS</td>
      <td>Australia</td>
      <td>Canberra</td>
      <td>Oceania</td>
      <td>26177413.00</td>
      <td>25670051.00</td>
      <td>23820236.00</td>
      <td>22019168.00</td>
      <td>19017963.00</td>
      <td>17048003.00</td>
      <td>14706322.00</td>
      <td>12595034.00</td>
      <td>7692024</td>
      <td>3</td>
      <td>1</td>
      <td>0.33</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6 = df5.drop(columns=['CCA3','Capital','Continent','Rank','Area (km²)','Density (per km²)','Growth Rate','World Population Percentage']) 

df6
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>2022 Population</th>
      <th>2020 Population</th>
      <th>2015 Population</th>
      <th>2010 Population</th>
      <th>2000 Population</th>
      <th>1990 Population</th>
      <th>1980 Population</th>
      <th>1970 Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Australia</td>
      <td>26177413.00</td>
      <td>25670051.00</td>
      <td>23820236.00</td>
      <td>22019168.00</td>
      <td>19017963.00</td>
      <td>17048003.00</td>
      <td>14706322.00</td>
      <td>12595034.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
df6['Population Increase'] = df6['2022 Population'] - df6['1970 Population']

df6 = df6.iloc[:, ::-1]

plt.plot(df6.columns[1:9], df6.iloc[0, 1:9], marker='o', linestyle='-')
plt.title('Population Increase in Australia (1970-2022)')
plt.xlabel('Year')
plt.ylabel('Population Increase')
plt.xticks(rotation=45)
plt.grid(True)

plt.show()
```


    
![png](output_29_0.png)
    



```python
df6
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Population Increase</th>
      <th>1970 Population</th>
      <th>1980 Population</th>
      <th>1990 Population</th>
      <th>2000 Population</th>
      <th>2010 Population</th>
      <th>2015 Population</th>
      <th>2020 Population</th>
      <th>2022 Population</th>
      <th>Country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>13582379.00</td>
      <td>12595034.00</td>
      <td>14706322.00</td>
      <td>17048003.00</td>
      <td>19017963.00</td>
      <td>22019168.00</td>
      <td>23820236.00</td>
      <td>25670051.00</td>
      <td>26177413.00</td>
      <td>Australia</td>
    </tr>
  </tbody>
</table>
</div>




```python
df7=df6.drop(columns='Population Increase') 

df7 
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1970 Population</th>
      <th>1980 Population</th>
      <th>1990 Population</th>
      <th>2000 Population</th>
      <th>2010 Population</th>
      <th>2015 Population</th>
      <th>2020 Population</th>
      <th>2022 Population</th>
      <th>Country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>12595034.00</td>
      <td>14706322.00</td>
      <td>17048003.00</td>
      <td>19017963.00</td>
      <td>22019168.00</td>
      <td>23820236.00</td>
      <td>25670051.00</td>
      <td>26177413.00</td>
      <td>Australia</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.title('Australian Population Distribution (1970-2022)')

df7.boxplot(figsize=(20,10))
```




    <Axes: title={'center': 'Australian Population Distribution (1970-2022)'}>




    
![png](output_32_1.png)
    



```python

```


```python

```


```python

```


```python

```

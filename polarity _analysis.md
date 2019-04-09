

```python
import urllib
```

# imorting urllib to use any url in code


```python
import json
```

# importing json to load data from the site


```python
from pandas.io.json import json_normalize
```

# importing json_normalize to normalize semi-structured json data into a flat      table


```python
url = "https://www.googleapis.com/youtube/v3/commentThreads?key=AIzaSyBwdx2rVaePw3a5ls0tMnF3Z_dea_c-NLM&textFormat=plainText&part=snippet&videoId=5GDTIUVlHB8&maxResults=100"
```

# Using the video id ,google developer console api key and the url to fetch the required content,here content is comment


```python
response = urllib.request.urlopen(url)
```

# allow access to response data


```python
data = response.read()
```


```python
contents = json.loads(data)
```


```python
dataf = json_normalize(contents['items'])
```

# Normalizing the semi-structured json data to a flat table


```python
df = dataf[['snippet.topLevelComment.snippet.textOriginal']]
```


```python
df.rename(columns={'snippet.topLevelComment.snippet.textOriginal': 'comments'}, inplace=True)
```

    /home/prachi/PROJECTS/PYCHARM/venv/lib/python3.6/site-packages/pandas/core/frame.py:3781: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame
    
    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy
      return super(DataFrame, self).rename(**kwargs)


# Renaming the contents as per the need


```python
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
      <th>comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>sir plz provide videoes on c#.net</td>
    </tr>
    <tr>
      <th>1</th>
      <td>nice video sir. Thanks for this video 👍👍👍🔥🔥🔥</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Generalization ka topic ka v video dalo plz</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sir I need interview qns about DBMS sir ... \n...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>amazing teaching sir !</td>
    </tr>
    <tr>
      <th>5</th>
      <td>sir, SID should be 4 instead of 2 at 9:15</td>
    </tr>
    <tr>
      <th>6</th>
      <td>i m understand normlization after watchinh 4 v...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>At row level ..there are repeated rows ...how ...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Bhai you are so helpful.</td>
    </tr>
    <tr>
      <th>9</th>
      <td>🖤</td>
    </tr>
    <tr>
      <th>10</th>
      <td>sir hmme poly Mai SQL pr lesson Hai Sir pls.. ...</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Paji thanks</td>
    </tr>
    <tr>
      <th>12</th>
      <td>very nice explanation sir.. keep it up</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Sir 4th and 5th normal form bhi karwado</td>
    </tr>
    <tr>
      <th>14</th>
      <td>gurujee shandhar jabardast zindabad</td>
    </tr>
    <tr>
      <th>15</th>
      <td>You are doing great job bro!</td>
    </tr>
    <tr>
      <th>16</th>
      <td>your videos are great. pls make videos on alga...</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Best video ever😍</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Super class sir</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Sir...u have great teaching skills...even a si...</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Execlent technique of explanation</td>
    </tr>
    <tr>
      <th>21</th>
      <td>sir please Dijkstra algorithms make da video</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Sir apki krpa se m pas ho jauga</td>
    </tr>
    <tr>
      <th>23</th>
      <td>thank you so much sir m rdy for the final exam...</td>
    </tr>
    <tr>
      <th>24</th>
      <td>sir, thank you so much for nice explanation</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Hi sir, u have to Update SID=4 not 2 right, fo...</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Sir can you make a videos lecture of COA for g...</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Sir aap bahut accha padhate ho .ur are my favo...</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Ty sr</td>
    </tr>
    <tr>
      <th>29</th>
      <td>sir is video  mai udas udas kyu lag rahe ho...</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Excellent Lectures but only constraint is Hind...</td>
    </tr>
    <tr>
      <th>31</th>
      <td>sir aap algorithm par v video bnaiye ........p...</td>
    </tr>
    <tr>
      <th>32</th>
      <td>thanku so much sir ....</td>
    </tr>
    <tr>
      <th>33</th>
      <td>once again you've proved   that you are good e...</td>
    </tr>
    <tr>
      <th>34</th>
      <td>sir sid of amrit pal is 4 not 2</td>
    </tr>
    <tr>
      <th>35</th>
      <td>sir u teaching is amazing but y teaching only ...</td>
    </tr>
    <tr>
      <th>36</th>
      <td>it officer</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Subscribed....👍</td>
    </tr>
    <tr>
      <th>38</th>
      <td>I don't have words to thanking u for all ur vi...</td>
    </tr>
    <tr>
      <th>39</th>
      <td>finally a decent teacher who teach in both hin...</td>
    </tr>
    <tr>
      <th>40</th>
      <td>Sir plzz Normalization k all type k tutorials ...</td>
    </tr>
    <tr>
      <th>41</th>
      <td>very nice explanation..........will u plz uplo...</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.to_csv("video4.csv", index=False)
```


```python
import csv
```


```python
from textblob import TextBlob
```


```python
infile = '/home/prachi/PycharmProjects/Mini_project/video4.csv'
```


```python
print("polarity")
with open(infile, 'r') as csvfile:
    rows = csv.reader(csvfile)
    for row in rows:
        sentence = row[0]
        blob = TextBlob(sentence)
        print (blob.sentiment.polarity,",")
```

    polarity
    0.0 ,
    0.0 ,
    0.4 ,
    0.0 ,
    0.8 ,
    0.7500000000000001 ,
    0.0 ,
    0.0 ,
    0.2 ,
    0.0 ,
    0.0 ,
    0.0 ,
    0.2 ,
    0.78 ,
    0.15 ,
    0.0 ,
    1.0 ,
    0.8 ,
    1.0 ,
    0.3333333333333333 ,
    0.2904761904761905 ,
    0.0 ,
    0.0 ,
    0.0 ,
    0.1 ,
    0.4 ,
    -0.3214285714285714 ,
    0.0 ,
    0.20555555555555557 ,
    0.0 ,
    0.0 ,
    0.3333333333333333 ,
    0.0 ,
    0.2 ,
    0.7 ,
    0.0 ,
    0.30000000000000004 ,
    0.0 ,
    0.0 ,
    0.3816666666666667 ,
    0.18333333333333335 ,
    0.16666666666666666 ,
    0.78 ,


# Using textblob to find the polarity of the document at sentence level and the    finding its average in the further code


```python
import pandas
df_pol = pandas.read_csv('video4_pol.csv')
print(df_pol)
```

               polarity
     0.000000       NaN
     0.000000       NaN
     0.400000       NaN
     0.000000       NaN
     0.800000       NaN
     0.750000       NaN
     0.000000       NaN
     0.000000       NaN
     0.200000       NaN
     0.000000       NaN
     0.000000       NaN
     0.000000       NaN
     0.200000       NaN
     0.780000       NaN
     0.150000       NaN
     0.000000       NaN
     1.000000       NaN
     0.800000       NaN
     1.000000       NaN
     0.333333       NaN
     0.290476       NaN
     0.000000       NaN
     0.000000       NaN
     0.000000       NaN
     0.100000       NaN
     0.400000       NaN
    -0.321429       NaN
     0.000000       NaN
     0.205556       NaN
     0.000000       NaN
     0.000000       NaN
     0.333333       NaN
     0.000000       NaN
     0.200000       NaN
     0.700000       NaN
     0.000000       NaN
     0.300000       NaN
     0.000000       NaN
     0.000000       NaN
     0.381667       NaN
     0.183333       NaN
     0.166667       NaN
     0.780000       NaN



```python
df_pol.sum(axis = 1, skipna = True)
```




     0.000000    0.0
     0.000000    0.0
     0.400000    0.0
     0.000000    0.0
     0.800000    0.0
     0.750000    0.0
     0.000000    0.0
     0.000000    0.0
     0.200000    0.0
     0.000000    0.0
     0.000000    0.0
     0.000000    0.0
     0.200000    0.0
     0.780000    0.0
     0.150000    0.0
     0.000000    0.0
     1.000000    0.0
     0.800000    0.0
     1.000000    0.0
     0.333333    0.0
     0.290476    0.0
     0.000000    0.0
     0.000000    0.0
     0.000000    0.0
     0.100000    0.0
     0.400000    0.0
    -0.321429    0.0
     0.000000    0.0
     0.205556    0.0
     0.000000    0.0
     0.000000    0.0
     0.333333    0.0
     0.000000    0.0
     0.200000    0.0
     0.700000    0.0
     0.000000    0.0
     0.300000    0.0
     0.000000    0.0
     0.000000    0.0
     0.381667    0.0
     0.183333    0.0
     0.166667    0.0
     0.780000    0.0
    dtype: float64




```python
a=[0.0 ,
0.0 ,
0.4 ,
0.0 ,
0.8 ,
0.7500000000000001 ,
0.0 ,
0.0 ,
0.2 ,
0.0 ,
0.0 ,
0.0 ,
0.2 ,
0.78 ,
0.15 ,
0.0 ,
1.0 ,
0.8 ,
1.0 ,
0.3333333333333333 ,
0.2904761904761905 ,
0.0 ,
0.0 ,
0.0 ,
0.1 ,
0.4 ,
-0.3214285714285714 ,
0.0 ,
0.20555555555555557 ,
0.0 ,
0.0 ,
0.3333333333333333 ,
0.0 ,
0.2 ,
0.7 ,
0.0 ,
0.30000000000000004 ,
0.0 ,
0.0 ,
0.3816666666666667 ,
0.18333333333333335 ,
0.16666666666666666 ,
0.78 ]
```


```python
avg = sum(a)/43
```


```python
print(avg)
```

    0.23564968623108157



```python

```

---
layout: post
title:  Code snippets in a blog post
categories: [HTML,Code]
---

```python
!pip install -U numpy
!pip install finance-datareader
import FinanceDataReader as fdr

def get_stock_list():
    try:
        df_krx = fdr.StockListing("KRX")
        return df_krx
    except Exception as e:    
        print("raise error ", e)
```

    Looking in indexes: https://pypi.org/simple, https://us-python.pkg.dev/colab-wheels/public/simple/
    Requirement already satisfied: numpy in /usr/local/lib/python3.10/dist-packages (1.24.3)
    Looking in indexes: https://pypi.org/simple, https://us-python.pkg.dev/colab-wheels/public/simple/
    Requirement already satisfied: finance-datareader in /usr/local/lib/python3.10/dist-packages (0.9.50)
    Requirement already satisfied: pandas>=0.19.2 in /usr/local/lib/python3.10/dist-packages (from finance-datareader) (1.5.3)
    Requirement already satisfied: requests>=2.3.0 in /usr/local/lib/python3.10/dist-packages (from finance-datareader) (2.27.1)
    Requirement already satisfied: requests-file in /usr/local/lib/python3.10/dist-packages (from finance-datareader) (1.5.1)
    Requirement already satisfied: lxml in /usr/local/lib/python3.10/dist-packages (from finance-datareader) (4.9.2)
    Requirement already satisfied: tqdm in /usr/local/lib/python3.10/dist-packages (from finance-datareader) (4.65.0)
    Requirement already satisfied: python-dateutil>=2.8.1 in /usr/local/lib/python3.10/dist-packages (from pandas>=0.19.2->finance-datareader) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in /usr/local/lib/python3.10/dist-packages (from pandas>=0.19.2->finance-datareader) (2022.7.1)
    Requirement already satisfied: numpy>=1.21.0 in /usr/local/lib/python3.10/dist-packages (from pandas>=0.19.2->finance-datareader) (1.24.3)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in /usr/local/lib/python3.10/dist-packages (from requests>=2.3.0->finance-datareader) (1.26.15)
    Requirement already satisfied: certifi>=2017.4.17 in /usr/local/lib/python3.10/dist-packages (from requests>=2.3.0->finance-datareader) (2022.12.7)
    Requirement already satisfied: charset-normalizer~=2.0.0 in /usr/local/lib/python3.10/dist-packages (from requests>=2.3.0->finance-datareader) (2.0.12)
    Requirement already satisfied: idna<4,>=2.5 in /usr/local/lib/python3.10/dist-packages (from requests>=2.3.0->finance-datareader) (3.4)
    Requirement already satisfied: six in /usr/local/lib/python3.10/dist-packages (from requests-file->finance-datareader) (1.16.0)



```python
import pandas as pd

df_krx = get_stock_list()
sam_df = fdr.DataReader(df_krx['Code'][0], '2020')
sam_df.head()
```





  <div id="df-36fc166d-e4f9-4a1a-8f92-1a3f7ccbcfa3">
    <div class="colab-df-container">
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Change</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>2020-01-02</th>
      <td>55500</td>
      <td>56000</td>
      <td>55000</td>
      <td>55200</td>
      <td>12993228</td>
      <td>-0.010753</td>
    </tr>
    <tr>
      <th>2020-01-03</th>
      <td>56000</td>
      <td>56600</td>
      <td>54900</td>
      <td>55500</td>
      <td>15422255</td>
      <td>0.005435</td>
    </tr>
    <tr>
      <th>2020-01-06</th>
      <td>54900</td>
      <td>55600</td>
      <td>54600</td>
      <td>55500</td>
      <td>10278951</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2020-01-07</th>
      <td>55700</td>
      <td>56400</td>
      <td>55600</td>
      <td>55800</td>
      <td>10009778</td>
      <td>0.005405</td>
    </tr>
    <tr>
      <th>2020-01-08</th>
      <td>56200</td>
      <td>57400</td>
      <td>55900</td>
      <td>56800</td>
      <td>23501171</td>
      <td>0.017921</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-36fc166d-e4f9-4a1a-8f92-1a3f7ccbcfa3')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-36fc166d-e4f9-4a1a-8f92-1a3f7ccbcfa3 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-36fc166d-e4f9-4a1a-8f92-1a3f7ccbcfa3');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
weekly_open = sam_df['Open'].resample('W-FRI').first().ffill()
weekly_high = sam_df['High'].resample('W-FRI').max().ffill()
weekly_low = sam_df['Low'].resample('W-FRI').min().ffill()
weekly_volume = sam_df['Volume'].resample('W-FRI').sum().ffill()
weekly_close = sam_df['Close'].resample('W-FRI').last().ffill()

# 주봉 데이터 프레임 생성
weekly_data = pd.DataFrame({'Open': weekly_open,
                            'High': weekly_high,
                            'Low': weekly_low,
                            'Volume': weekly_volume,
                            'Close': weekly_close})

weekly_data['Close'].plot()
weekly_data.head()


```





  <div id="df-c86f0487-f90a-43a6-a2c3-ff06aa8a3cb9">
    <div class="colab-df-container">
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Volume</th>
      <th>Close</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-03</th>
      <td>55500</td>
      <td>56600</td>
      <td>54900</td>
      <td>28415483</td>
      <td>55500</td>
    </tr>
    <tr>
      <th>2020-01-10</th>
      <td>54900</td>
      <td>59700</td>
      <td>54600</td>
      <td>83892649</td>
      <td>59500</td>
    </tr>
    <tr>
      <th>2020-01-17</th>
      <td>59600</td>
      <td>62000</td>
      <td>58900</td>
      <td>72973797</td>
      <td>61300</td>
    </tr>
    <tr>
      <th>2020-01-24</th>
      <td>62000</td>
      <td>62800</td>
      <td>60400</td>
      <td>53927668</td>
      <td>60800</td>
    </tr>
    <tr>
      <th>2020-01-31</th>
      <td>59400</td>
      <td>59700</td>
      <td>56400</td>
      <td>80682039</td>
      <td>56400</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c86f0487-f90a-43a6-a2c3-ff06aa8a3cb9')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c86f0487-f90a-43a6-a2c3-ff06aa8a3cb9 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c86f0487-f90a-43a6-a2c3-ff06aa8a3cb9');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





    
![png](random-forest-v1_files/random-forest-v1_2_1.png)
    



```python

weekly_data['Close_1w_change'] = weekly_data['Close'].pct_change()
weekly_data['Close_1w_future_close'] = weekly_data['Close'].shift(-1)

weekly_data.dropna(inplace=True)
weekly_data['is_futrue_rise'] = weekly_data['Close_1w_future_close'] > weekly_data['Close'] 
weekly_data_org = weekly_data.copy()
weekly_data.head()

```





  <div id="df-c29d27eb-3fa4-4043-ad68-bbd3059f2c4e">
    <div class="colab-df-container">
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Volume</th>
      <th>Close</th>
      <th>Close_1w_change</th>
      <th>Close_1w_future_close</th>
      <th>is_futrue_rise</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>2020-01-10</th>
      <td>54900</td>
      <td>59700</td>
      <td>54600</td>
      <td>83892649</td>
      <td>59500</td>
      <td>0.072072</td>
      <td>61300.0</td>
      <td>True</td>
    </tr>
    <tr>
      <th>2020-01-17</th>
      <td>59600</td>
      <td>62000</td>
      <td>58900</td>
      <td>72973797</td>
      <td>61300</td>
      <td>0.030252</td>
      <td>60800.0</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2020-01-24</th>
      <td>62000</td>
      <td>62800</td>
      <td>60400</td>
      <td>53927668</td>
      <td>60800</td>
      <td>-0.008157</td>
      <td>56400.0</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2020-01-31</th>
      <td>59400</td>
      <td>59700</td>
      <td>56400</td>
      <td>80682039</td>
      <td>56400</td>
      <td>-0.072368</td>
      <td>60400.0</td>
      <td>True</td>
    </tr>
    <tr>
      <th>2020-02-07</th>
      <td>55500</td>
      <td>61200</td>
      <td>55200</td>
      <td>96203269</td>
      <td>60400</td>
      <td>0.070922</td>
      <td>61800.0</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-c29d27eb-3fa4-4043-ad68-bbd3059f2c4e')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-c29d27eb-3fa4-4043-ad68-bbd3059f2c4e button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-c29d27eb-3fa4-4043-ad68-bbd3059f2c4e');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```python
url = 'https://anaconda.org/conda-forge/libta-lib/0.4.0/download/linux-64/libta-lib-0.4.0-h166bdaf_1.tar.bz2'
!curl -L $url | tar xj -C /usr/lib/x86_64-linux-gnu/ lib --strip-components=1
url = 'https://anaconda.org/conda-forge/ta-lib/0.4.19/download/linux-64/ta-lib-0.4.19-py310hde88566_4.tar.bz2'
!curl -L $url | tar xj -C /usr/local/lib/python3.10/dist-packages/ lib/python3.10/site-packages/talib --strip-components=3
import talib
```

      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100  4267    0  4267    0     0   8779      0 --:--:-- --:--:-- --:--:--  8761
    100  517k  100  517k    0     0   303k      0  0:00:01  0:00:01 --:--:--  652k
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100  4271    0  4271    0     0  10677      0 --:--:-- --:--:-- --:--:-- 10704
    100  392k  100  392k    0     0   365k      0  0:00:01  0:00:01 --:--:--  663k



```python
import talib
import numpy as np

weekly_data = weekly_data_org.copy()
feature_names = []

float_data = [float(x) for x in weekly_data['Close']]
np_float_data = np.array(float_data)
for n in [3, 5, 14, 20]:
    weekly_data['ma' + str(n)] = talib.SMA(np_float_data, timeperiod=n)
    weekly_data['rsi' + str(n)] = talib.RSI(np_float_data, timeperiod=n)

    feature_names = feature_names + ['ma' + str(n), 'rsi' + str(n)]

# weekly_data['MACD'] = talib.MACD(weekly_data['Close'], fastperiod=12, slowperiod=26, signalperiod=9)[0] / \
#                      talib.MACD(weekly_data['Close'], fastperiod=12, slowperiod=26, signalperiod=9)[0].mean()

weekly_data['MACD'], weekly_data['MACD_SIGNAL'], weekly_data['MACD_HISTOGRAM'] = talib.MACD(weekly_data['Close'], fastperiod=12, slowperiod=26, signalperiod=9)
weekly_data['CCI'] = talib.CCI(weekly_data['High'], weekly_data['Low'], weekly_data['Close'], 14)
    
weekly_data['Volume_1d_change'] = weekly_data['Volume'].pct_change()
volume_features = ['Volume_1d_change']
feature_names.extend(volume_features)
weekly_data.dropna(inplace=True)
weekly_data.head()

print(weekly_data['MACD_HISTOGRAM'])

```

    Date
    2020-08-28    1013.131601
    2020-09-04     845.077895
    2020-09-11     916.966270
    2020-09-18     935.552475
    2020-09-25     809.133251
                     ...     
    2023-05-05     441.710870
    2023-05-12     302.430593
    2023-05-19     465.712343
    2023-05-26     655.850765
    2023-06-02     851.360241
    Freq: W-FRI, Name: MACD_HISTOGRAM, Length: 145, dtype: float64



```python
import matplotlib.pyplot as plt

plt.plot(weekly_data['Close'])
plt.plot(weekly_data['ma14'])
plt.plot(weekly_data['ma20'])
plt.show()
```


    
![png](random-forest-v1_files/random-forest-v1_6_0.png)
    



```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

#sam_df.dropna(inplace=True)
#sam_df = sam_df[np.isfinite(sam_df).all(1)]

data = weekly_data[['Open','High','Low','Close', 'ma3']].to_numpy()
print(data.shape)

target = weekly_data['is_futrue_rise'].to_numpy()
train_input, test_input, train_target, test_target = train_test_split(data, target, test_size=0.2, shuffle=False)

```

    (145, 5)



```python
from sklearn.model_selection import cross_validate
from sklearn.ensemble import RandomForestClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.preprocessing import StandardScaler

# ss = StandardScaler()
# ss.fit(train_input)
# train_scaled = ss.transform(train_input)
# test_scaled = ss.transform(test_input)
# print(train_scaled.shape)

rf = RandomForestClassifier(n_jobs=-1)
scores = cross_validate(rf, train_input, train_target, return_train_score=True, n_jobs=-1)
print(np.mean(scores['train_score']), np.mean(scores['test_score']))
```

    0.9978494623655914 0.45688405797101445



```python
%%shell
jupyter nbconvert --to html /content/colab2html.ipynb
```

    [NbConvertApp] WARNING | pattern '/content/colab2html.ipynb' matched no files
    This application is used to convert notebook files (*.ipynb)
            to various other formats.
    
            WARNING: THE COMMANDLINE INTERFACE MAY CHANGE IN FUTURE RELEASES.
    
    Options
    =======
    The options below are convenience aliases to configurable class-options,
    as listed in the "Equivalent to" description-line of the aliases.
    To see all configurable class-options for some <cmd>, use:
        <cmd> --help-all
    
    --debug
        set log level to logging.DEBUG (maximize logging output)
        Equivalent to: [--Application.log_level=10]
    --show-config
        Show the application's configuration (human-readable format)
        Equivalent to: [--Application.show_config=True]
    --show-config-json
        Show the application's configuration (json format)
        Equivalent to: [--Application.show_config_json=True]
    --generate-config
        generate default config file
        Equivalent to: [--JupyterApp.generate_config=True]
    -y
        Answer yes to any questions instead of prompting.
        Equivalent to: [--JupyterApp.answer_yes=True]
    --execute
        Execute the notebook prior to export.
        Equivalent to: [--ExecutePreprocessor.enabled=True]
    --allow-errors
        Continue notebook execution even if one of the cells throws an error and include the error message in the cell output (the default behaviour is to abort conversion). This flag is only relevant if '--execute' was specified, too.
        Equivalent to: [--ExecutePreprocessor.allow_errors=True]
    --stdin
        read a single notebook file from stdin. Write the resulting notebook with default basename 'notebook.*'
        Equivalent to: [--NbConvertApp.from_stdin=True]
    --stdout
        Write notebook output to stdout instead of files.
        Equivalent to: [--NbConvertApp.writer_class=StdoutWriter]
    --inplace
        Run nbconvert in place, overwriting the existing notebook (only
                relevant when converting to notebook format)
        Equivalent to: [--NbConvertApp.use_output_suffix=False --NbConvertApp.export_format=notebook --FilesWriter.build_directory=]
    --clear-output
        Clear output of current file and save in place,
                overwriting the existing notebook.
        Equivalent to: [--NbConvertApp.use_output_suffix=False --NbConvertApp.export_format=notebook --FilesWriter.build_directory= --ClearOutputPreprocessor.enabled=True]
    --no-prompt
        Exclude input and output prompts from converted document.
        Equivalent to: [--TemplateExporter.exclude_input_prompt=True --TemplateExporter.exclude_output_prompt=True]
    --no-input
        Exclude input cells and output prompts from converted document.
                This mode is ideal for generating code-free reports.
        Equivalent to: [--TemplateExporter.exclude_output_prompt=True --TemplateExporter.exclude_input=True --TemplateExporter.exclude_input_prompt=True]
    --allow-chromium-download
        Whether to allow downloading chromium if no suitable version is found on the system.
        Equivalent to: [--WebPDFExporter.allow_chromium_download=True]
    --disable-chromium-sandbox
        Disable chromium security sandbox when converting to PDF..
        Equivalent to: [--WebPDFExporter.disable_sandbox=True]
    --show-input
        Shows code input. This flag is only useful for dejavu users.
        Equivalent to: [--TemplateExporter.exclude_input=False]
    --embed-images
        Embed the images as base64 dataurls in the output. This flag is only useful for the HTML/WebPDF/Slides exports.
        Equivalent to: [--HTMLExporter.embed_images=True]
    --sanitize-html
        Whether the HTML in Markdown cells and cell outputs should be sanitized..
        Equivalent to: [--HTMLExporter.sanitize_html=True]
    --log-level=<Enum>
        Set the log level by value or name.
        Choices: any of [0, 10, 20, 30, 40, 50, 'DEBUG', 'INFO', 'WARN', 'ERROR', 'CRITICAL']
        Default: 30
        Equivalent to: [--Application.log_level]
    --config=<Unicode>
        Full path of a config file.
        Default: ''
        Equivalent to: [--JupyterApp.config_file]
    --to=<Unicode>
        The export format to be used, either one of the built-in formats
                ['asciidoc', 'custom', 'html', 'latex', 'markdown', 'notebook', 'pdf', 'python', 'rst', 'script', 'slides', 'webpdf']
                or a dotted object name that represents the import path for an
                ``Exporter`` class
        Default: ''
        Equivalent to: [--NbConvertApp.export_format]
    --template=<Unicode>
        Name of the template to use
        Default: ''
        Equivalent to: [--TemplateExporter.template_name]
    --template-file=<Unicode>
        Name of the template file to use
        Default: None
        Equivalent to: [--TemplateExporter.template_file]
    --theme=<Unicode>
        Template specific theme(e.g. the name of a JupyterLab CSS theme distributed
        as prebuilt extension for the lab template)
        Default: 'light'
        Equivalent to: [--HTMLExporter.theme]
    --sanitize_html=<Bool>
        Whether the HTML in Markdown cells and cell outputs should be sanitized.This
        should be set to True by nbviewer or similar tools.
        Default: False
        Equivalent to: [--HTMLExporter.sanitize_html]
    --writer=<DottedObjectName>
        Writer class used to write the
                                            results of the conversion
        Default: 'FilesWriter'
        Equivalent to: [--NbConvertApp.writer_class]
    --post=<DottedOrNone>
        PostProcessor class used to write the
                                            results of the conversion
        Default: ''
        Equivalent to: [--NbConvertApp.postprocessor_class]
    --output=<Unicode>
        overwrite base name use for output files.
                    can only be used when converting one notebook at a time.
        Default: ''
        Equivalent to: [--NbConvertApp.output_base]
    --output-dir=<Unicode>
        Directory to write output(s) to. Defaults
                                      to output to the directory of each notebook. To recover
                                      previous default behaviour (outputting to the current
                                      working directory) use . as the flag value.
        Default: ''
        Equivalent to: [--FilesWriter.build_directory]
    --reveal-prefix=<Unicode>
        The URL prefix for reveal.js (version 3.x).
                This defaults to the reveal CDN, but can be any url pointing to a copy
                of reveal.js.
                For speaker notes to work, this must be a relative path to a local
                copy of reveal.js: e.g., "reveal.js".
                If a relative path is given, it must be a subdirectory of the
                current directory (from which the server is run).
                See the usage documentation
                (https://nbconvert.readthedocs.io/en/latest/usage.html#reveal-js-html-slideshow)
                for more details.
        Default: ''
        Equivalent to: [--SlidesExporter.reveal_url_prefix]
    --nbformat=<Enum>
        The nbformat version to write.
                Use this to downgrade notebooks.
        Choices: any of [1, 2, 3, 4]
        Default: 4
        Equivalent to: [--NotebookExporter.nbformat_version]
    
    Examples
    --------
    
        The simplest way to use nbconvert is
    
                > jupyter nbconvert mynotebook.ipynb --to html
    
                Options include ['asciidoc', 'custom', 'html', 'latex', 'markdown', 'notebook', 'pdf', 'python', 'rst', 'script', 'slides', 'webpdf'].
    
                > jupyter nbconvert --to latex mynotebook.ipynb
    
                Both HTML and LaTeX support multiple output templates. LaTeX includes
                'base', 'article' and 'report'.  HTML includes 'basic', 'lab' and
                'classic'. You can specify the flavor of the format used.
    
                > jupyter nbconvert --to html --template lab mynotebook.ipynb
    
                You can also pipe the output to stdout, rather than a file
    
                > jupyter nbconvert mynotebook.ipynb --stdout
    
                PDF is generated via latex
    
                > jupyter nbconvert mynotebook.ipynb --to pdf
    
                You can get (and serve) a Reveal.js-powered slideshow
    
                > jupyter nbconvert myslides.ipynb --to slides --post serve
    
                Multiple notebooks can be given at the command line in a couple of
                different ways:
    
                > jupyter nbconvert notebook*.ipynb
                > jupyter nbconvert notebook1.ipynb notebook2.ipynb
    
                or you can specify the notebooks list in a config file, containing::
    
                    c.NbConvertApp.notebooks = ["my_notebook.ipynb"]
    
                > jupyter nbconvert --config mycfg.py
    
    To see all available configurables, use `--help-all`.
    



    ---------------------------------------------------------------------------

    CalledProcessError                        Traceback (most recent call last)

    <ipython-input-37-9ad7604c2f9f> in <cell line: 1>()
    ----> 1 get_ipython().run_cell_magic('shell', '', 'jupyter nbconvert --to html /content/colab2html.ipynb\n')
    

    /usr/local/lib/python3.10/dist-packages/google/colab/_shell.py in run_cell_magic(self, magic_name, line, cell)
        332     if line and not cell:
        333       cell = ' '
    --> 334     return super().run_cell_magic(magic_name, line, cell)
        335 
        336 


    /usr/local/lib/python3.10/dist-packages/IPython/core/interactiveshell.py in run_cell_magic(self, magic_name, line, cell)
       2471             with self.builtin_trap:
       2472                 args = (magic_arg_s, cell)
    -> 2473                 result = fn(*args, **kwargs)
       2474             return result
       2475 


    /usr/local/lib/python3.10/dist-packages/google/colab/_system_commands.py in _shell_cell_magic(args, cmd)
        110   result = _run_command(cmd, clear_streamed_output=False)
        111   if not parsed_args.ignore_errors:
    --> 112     result.check_returncode()
        113   return result
        114 


    /usr/local/lib/python3.10/dist-packages/google/colab/_system_commands.py in check_returncode(self)
        135   def check_returncode(self):
        136     if self.returncode:
    --> 137       raise subprocess.CalledProcessError(
        138           returncode=self.returncode, cmd=self.args, output=self.output
        139       )


    CalledProcessError: Command 'jupyter nbconvert --to html /content/colab2html.ipynb
    ' returned non-zero exit status 255.


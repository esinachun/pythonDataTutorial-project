

```python
from bs4 import BeautifulSoup
```


```python
page = open("../data/03. test_first.html",'r').read()
soup = BeautifulSoup(page, 'html.parser')
print(soup.prettify())
```

    <!DOCTYPE html>
    <html>
     <head>
      <title>
       Very Simple HTML Code by PinkWink
      </title>
     </head>
     <body>
      <div>
       <p class="inner-text first-item" id="first">
        Happy PinkWink.
        <a href="http://www.pinkwink.kr" id="pw-link">
         PinkWink
        </a>
       </p>
       <p class="inner-text second-item">
        Happy Data Science.
        <a href="https://www.python.org" id="py-link">
         Python
        </a>
       </p>
      </div>
      <p class="outer-text first-item" id="second">
       <b>
        Data Science is funny.
       </b>
      </p>
      <p class="outer-text">
       <b>
        All I need is Love.
       </b>
      </p>
     </body>
    </html>
    



```python
list(soup.children)
```




    ['html', '\n', <html>
     <head>
     <title>Very Simple HTML Code by PinkWink</title>
     </head>
     <body>
     <div>
     <p class="inner-text first-item" id="first">
                     Happy PinkWink.
                     <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
     </p>
     <p class="inner-text second-item">
                     Happy Data Science.
                     <a href="https://www.python.org" id="py-link">Python</a>
     </p>
     </div>
     <p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>
     <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>
     </body>
     </html>, '\n']




```python
html = list(soup.children)[2]
html
```




    <html>
    <head>
    <title>Very Simple HTML Code by PinkWink</title>
    </head>
    <body>
    <div>
    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>
    <p class="inner-text second-item">
                    Happy Data Science.
                    <a href="https://www.python.org" id="py-link">Python</a>
    </p>
    </div>
    <p class="outer-text first-item" id="second">
    <b>
                    Data Science is funny.
                </b>
    </p>
    <p class="outer-text">
    <b>
                    All I need is Love.
                </b>
    </p>
    </body>
    </html>




```python
list(html.children)
```




    ['\n', <head>
     <title>Very Simple HTML Code by PinkWink</title>
     </head>, '\n', <body>
     <div>
     <p class="inner-text first-item" id="first">
                     Happy PinkWink.
                     <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
     </p>
     <p class="inner-text second-item">
                     Happy Data Science.
                     <a href="https://www.python.org" id="py-link">Python</a>
     </p>
     </div>
     <p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>
     <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>
     </body>, '\n']




```python
body = list(html.children)[3]
body
```




    <body>
    <div>
    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>
    <p class="inner-text second-item">
                    Happy Data Science.
                    <a href="https://www.python.org" id="py-link">Python</a>
    </p>
    </div>
    <p class="outer-text first-item" id="second">
    <b>
                    Data Science is funny.
                </b>
    </p>
    <p class="outer-text">
    <b>
                    All I need is Love.
                </b>
    </p>
    </body>




```python
soup.body
```




    <body>
    <div>
    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>
    <p class="inner-text second-item">
                    Happy Data Science.
                    <a href="https://www.python.org" id="py-link">Python</a>
    </p>
    </div>
    <p class="outer-text first-item" id="second">
    <b>
                    Data Science is funny.
                </b>
    </p>
    <p class="outer-text">
    <b>
                    All I need is Love.
                </b>
    </p>
    </body>




```python
list(body.children)
```




    ['\n', <div>
     <p class="inner-text first-item" id="first">
                     Happy PinkWink.
                     <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
     </p>
     <p class="inner-text second-item">
                     Happy Data Science.
                     <a href="https://www.python.org" id="py-link">Python</a>
     </p>
     </div>, '\n', <p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>, '\n', <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>, '\n']




```python
soup.find_all('p')
```




    [<p class="inner-text first-item" id="first">
                     Happy PinkWink.
                     <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
     </p>, <p class="inner-text second-item">
                     Happy Data Science.
                     <a href="https://www.python.org" id="py-link">Python</a>
     </p>, <p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>, <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>]




```python
#p 한개만 찾기
soup.find('p')
```




    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>




```python
#p이면서 class가 outer-text인것 찾기
soup.find_all(class_="outer-text")
```




    [<p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>, <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>]




```python
soup.find_all(class_="outer-text")
```




    [<p class="outer-text first-item" id="second">
     <b>
                     Data Science is funny.
                 </b>
     </p>, <p class="outer-text">
     <b>
                     All I need is Love.
                 </b>
     </p>]




```python
soup.head
```




    <head>
    <title>Very Simple HTML Code by PinkWink</title>
    </head>




```python
#find는 첫번째만 보여주니 그 다음것 찾기
soup.head.next_sibling
```




    '\n'




```python
soup.head.next_sibling.next_sibling
```




    <body>
    <div>
    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>
    <p class="inner-text second-item">
                    Happy Data Science.
                    <a href="https://www.python.org" id="py-link">Python</a>
    </p>
    </div>
    <p class="outer-text first-item" id="second">
    <b>
                    Data Science is funny.
                </b>
    </p>
    <p class="outer-text">
    <b>
                    All I need is Love.
                </b>
    </p>
    </body>




```python
body.p
```




    <p class="inner-text first-item" id="first">
                    Happy PinkWink.
                    <a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>
    </p>




```python
body.p.next_sibling.next_sibling
```




    <p class="inner-text second-item">
                    Happy Data Science.
                    <a href="https://www.python.org" id="py-link">Python</a>
    </p>




```python
#text만 가져오기
for each_tag in soup.find_all('p'):
    print(each_tag.get_text())
```

    
                    Happy PinkWink.
                    PinkWink
    
    
                    Happy Data Science.
                    Python
    
    
    
                    Data Science is funny.
                
    
    
    
                    All I need is Love.
                
    



```python
#body 전체에 get_text()를 하면 태그가 있던 자리는 줄바꿈 표시가 되고 전체 텍스트를 보여준다
body.get_text()
```




    '\n\n\n                Happy PinkWink.\n                PinkWink\n\n\n                Happy Data Science.\n                Python\n\n\n\n\n                Data Science is funny.\n            \n\n\n\n                All I need is Love.\n            \n\n'




```python
links = soup.find_all('a')
links
```




    [<a href="http://www.pinkwink.kr" id="pw-link">PinkWink</a>,
     <a href="https://www.python.org" id="py-link">Python</a>]




```python
for each in links:
    href = each['href']
    text = each.string
    print(text + ' -> ' + href)
```

    PinkWink -> http://www.pinkwink.kr
    Python -> https://www.python.org



```python
#url로 접근하는 경우 urlopen이라는 함수 사용
from urllib.request import urlopen
```


```python
url = "http://info.finance.naver.com/marketindex/"
page = urlopen(url)

soup = BeautifulSoup(page, "html.parser")

print(soup.prettify())
```

    <script language="javascript" src="http://finance.naver.com/template/head_js.nhn?referer=info.finance.naver.com&amp;menu=marketindex&amp;submenu=market">
    </script>
    <script src="/js/jindo.min.ns.1.5.3.euckr.js" type="text/javascript">
    </script>
    <script src="/js/jindo.1.5.3.element-text-patch.js" type="text/javascript">
    </script>
    <div id="container" style="padding-bottom:0px;">
     <script language="JavaScript" src="/js/flashObject.js?20180502015110">
     </script>
     <div class="market_include">
      <div class="market_data">
       <div class="market1">
        <div class="title">
         <h2 class="h_market1">
          <span>
           환전 고시 환율
          </span>
         </h2>
        </div>
        <!-- data -->
        <div class="data">
         <ul class="data_lst" id="exchangeList">
          <li class="on">
           <a class="head usd" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_USDKRW" onclick="clickcr(this, 'fr1.usdt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              미국 USD
             </span>
            </h3>
            <div class="head_info point_dn">
             <span class="value">
              1,076.00
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              4.00
             </span>
             <span class="blind">
              하락
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_USDKRW" onclick="clickcr(this, 'fr1.usdc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_USDKRW.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31 16:49
            </span>
            <span class="source">
             KEB하나은행 기준
            </span>
            <span class="count">
             고시회차
             <span class="num">
              282
             </span>
             회
            </span>
           </div>
          </li>
          <li class="">
           <a class="head jpy" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_JPYKRW" onclick="clickcr(this, 'fr1.jpyt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              일본 JPY(100엔)
             </span>
            </h3>
            <div class="head_info point_dn">
             <span class="value">
              990.02
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              2.40
             </span>
             <span class="blind">
              하락
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_JPYKRW" onclick="clickcr(this, 'fr1.jpyc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_JPYKRW.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31 16:49
            </span>
            <span class="source">
             KEB하나은행 기준
            </span>
            <span class="count">
             고시회차
             <span class="num">
              282
             </span>
             회
            </span>
           </div>
          </li>
          <li class="">
           <a class="head eur" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_EURKRW" onclick="clickcr(this, 'fr1.eurt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              유럽연합 EUR
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              1,260.27
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              3.80
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_EURKRW" onclick="clickcr(this, 'fr1.eurc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_EURKRW.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31 16:49
            </span>
            <span class="source">
             KEB하나은행 기준
            </span>
            <span class="count">
             고시회차
             <span class="num">
              282
             </span>
             회
            </span>
           </div>
          </li>
          <li class="">
           <a class="head cny" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_CNYKRW" onclick="clickcr(this, 'fr1.cnyt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              중국 CNY
             </span>
            </h3>
            <div class="head_info point_dn">
             <span class="value">
              168.17
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              0.31
             </span>
             <span class="blind">
              하락
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/exchangeDetail.nhn?marketindexCd=FX_CNYKRW" onclick="clickcr(this, 'fr1.cnyc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_CNYKRW.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31 16:49
            </span>
            <span class="source">
             KEB하나은행 기준
            </span>
            <span class="count">
             고시회차
             <span class="num">
              282
             </span>
             회
            </span>
           </div>
          </li>
         </ul>
        </div>
        <!-- //data -->
       </div>
       <div class="market2">
        <div class="title">
         <h2 class="h_market2">
          <span>
           국제 시장 환율
          </span>
         </h2>
        </div>
        <!-- data -->
        <div class="data">
         <ul class="data_lst" id="worldExchangeList">
          <li class="on">
           <a class="head jpy_usd" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_USDJPY" onclick="clickcr(this, 'fr2.jpyut', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              일본 엔/달러
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              108.8900
             </span>
             <span class="txt_jpy">
              <span class="blind">
               엔
              </span>
             </span>
             <span class="change">
              0.0600
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_USDJPY" onclick="clickcr(this, 'fr2.jpyuc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_USDJPY.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             모닝스타 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head usd_eur" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_EURUSD" onclick="clickcr(this, 'fr2.eurdt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              달러/유로
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              1.1611
             </span>
             <span class="txt_usd">
              <span class="blind">
               달러
              </span>
             </span>
             <span class="change">
              0.0046
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_EURUSD" onclick="clickcr(this, 'fr2.eurdc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_EURUSD.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             모닝스타 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head usd_gbp" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_GBPUSD" onclick="clickcr(this, 'fr2.gbpdt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              달러/영국파운드
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              1.3275
             </span>
             <span class="txt_usd">
              <span class="blind">
               달러
              </span>
             </span>
             <span class="change">
              0.0001
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_GBPUSD" onclick="clickcr(this, 'fr2.gbpdc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_GBPUSD.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             모닝스타 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head usd_idx" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_USDX" onclick="clickcr(this, 'fr2.indt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              달러인덱스
             </span>
            </h3>
            <div class="head_info point_dn">
             <span class="value">
              94.1100
             </span>
             <span class="change">
              0.6700
             </span>
             <span class="blind">
              하락
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_USDX" onclick="clickcr(this, 'fr2.indc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/FX_USDX.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             ICE 기준
            </span>
           </div>
          </li>
         </ul>
        </div>
        <!-- //data -->
       </div>
       <div class="market3">
        <div class="title">
         <h2 class="h_market3">
          <span>
           유가·금시세
          </span>
         </h2>
        </div>
        <!-- data -->
        <div class="data">
         <ul class="data_lst" id="oilGoldList">
          <li class="on">
           <a class="head wti" href="/marketindex/worldOilDetail.nhn?marketindexCd=OIL_CL&amp;fdtc=2" onclick="clickcr(this, 'fr3.wtit', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              WTI
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              68.21
             </span>
             <span class="txt_usd">
              <span class="blind">
               달러
              </span>
             </span>
             <span class="change">
              1.48
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldOilDetail.nhn?marketindexCd=OIL_CL&amp;fdtc=2" onclick="clickcr(this, 'fr3.wtic', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/OIL_CL.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             NYMEX(뉴욕상업거래소) 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head gasoline" href="/marketindex/oilDetail.nhn?marketindexCd=OIL_GSL" onclick="clickcr(this, 'fr3.oilt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              휘발유
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              1607.12
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              0.44
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/oilDetail.nhn?marketindexCd=OIL_GSL" onclick="clickcr(this, 'fr3.oilc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/OIL_GSL.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31
            </span>
            <span class="source">
             한국석유공사 Opinet 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head gold_inter" href="/marketindex/worldGoldDetail.nhn?marketindexCd=CMDT_GC&amp;fdtc=2" onclick="clickcr(this, 'fr3.agoldt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              국제 금
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              1301.5
             </span>
             <span class="txt_usd">
              <span class="blind">
               달러
              </span>
             </span>
             <span class="change">
              2.50
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/worldGoldDetail.nhn?marketindexCd=CMDT_GC&amp;fdtc=2" onclick="clickcr(this, 'fr3.agoldc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/CMDT_GC.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.30
            </span>
            <span class="source">
             COMEX(뉴욕상품거래소) 기준
            </span>
           </div>
          </li>
          <li class="">
           <a class="head gold_domestic" href="/marketindex/goldDetail.nhn" onclick="clickcr(this, 'fr3.kgoldt', '', '', event);">
            <h3 class="h_lst">
             <span class="blind">
              국내 금
             </span>
            </h3>
            <div class="head_info point_up">
             <span class="value">
              45172.42
             </span>
             <span class="txt_krw">
              <span class="blind">
               원
              </span>
             </span>
             <span class="change">
              57.01
             </span>
             <span class="blind">
              상승
             </span>
            </div>
           </a>
           <a class="graph_img" href="/marketindex/goldDetail.nhn" onclick="clickcr(this, 'fr3.kgoldc', '', '', event);">
            <img alt="" height="153" src="http://imgfinance.naver.net/chart/marketindex/CMDT_GD.png" width="295"/>
           </a>
           <div class="graph_info">
            <span class="time">
             2018.05.31 16:46
            </span>
            <span class="source">
             신한은행 기준
            </span>
            (
            <span class="num">
             45
            </span>
            회차)
           </div>
          </li>
         </ul>
        </div>
        <!-- //data -->
       </div>
      </div>
     </div>
     <div class="marketindex_content" id="content">
      <div class="section_news">
       <h3 class="h_news2">
        <span>
         주요 뉴스
        </span>
       </h3>
       <div class="list_area">
        <ul>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=015&amp;articleId=0003952258&amp;category=" onclick="clickcr(this, 'mhn.list', '015_0003952258', '0', event);">
            [환율마감]원·달러 환율 하락 마감…107
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 15:33
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=277&amp;articleId=0004249207&amp;category=" onclick="clickcr(this, 'mhn.list', '277_0004249207', '1', event);">
            3.8兆 추경에도 KDI 성장률 전망 그대
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 13:39
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=215&amp;articleId=0000640813&amp;category=" onclick="clickcr(this, 'mhn.list', '215_0000640813', '2', event);">
            기업 경기전망 다시 '부정적'‥"유가·원자
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 13:33
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=277&amp;articleId=0004248867&amp;category=" onclick="clickcr(this, 'mhn.list', '277_0004248867', '3', event);">
            정유株, 국제유가 반등에 동반 상승…SK이
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 09:34
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=001&amp;articleId=0010118670&amp;category=" onclick="clickcr(this, 'mhn.list', '001_0010118670', '4', event);">
            [특징주] 국제유가 반등에 정유주 강세
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 09:24
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=417&amp;articleId=0000320292&amp;category=" onclick="clickcr(this, 'mhn.list', '417_0000320292', '5', event);">
            [오늘의 환율전망] 원/달러, 1076원
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 08:52
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=018&amp;articleId=0004115133&amp;category=" onclick="clickcr(this, 'mhn.list', '018_0004115133', '6', event);">
            [외환브리핑]한숨 돌린 '이탈렉시트' 우려
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 08:49
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=001&amp;articleId=0010118556&amp;category=" onclick="clickcr(this, 'mhn.list', '001_0010118556', '7', event);">
            하나금투 "국제유가 60달러 중반서 안정될
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 08:46
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=001&amp;articleId=0010118543&amp;category=" onclick="clickcr(this, 'mhn.list', '001_0010118543', '8', event);">
            대신증권 "국제유가 하반기 하향 안정…배럴
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 08:36
          </span>
         </li>
         <li>
          <p>
           <a href="/marketindex/news/newsRead.nhn?officeId=008&amp;articleId=0004058685&amp;category=" onclick="clickcr(this, 'mhn.list', '008_0004058685', '9', event);">
            태광, 유가상승에 주가상승 여력-케이프증권
           </a>
           <img alt="NEW" height="8" src="http://static.naver.com/nfinance/ico_new.gif" width="8"/>
          </p>
          <span>
           05.31 08:30
          </span>
         </li>
        </ul>
       </div>
       <a class="btn_more" href="/marketindex/news/newsList.nhn" onclick="clickcr(this, 'mhn.more', '', '', event);">
        <img alt="더보기" height="18" src="http://static.naver.com/nfinance/btn_more.gif" width="34"/>
       </a>
      </div>
      <div class="tab_default1" id="tab_section">
       <ul>
        <li class="on">
         <a href="./?tabSel=exchange#tab_section" onclick="clickcr(this, 'mtb.exnoti', '', '', event);">
          <span class="tab1">
           환전고시 환율
          </span>
         </a>
        </li>
        <li class="">
         <a href="./?tabSel=worldExchange#tab_section" onclick="clickcr(this, 'mtb.interex', '', '', event);">
          <span class="tab2">
           국제시장 환율
          </span>
         </a>
        </li>
        <li class="">
         <a href="./?tabSel=gold#tab_section" onclick="clickcr(this, 'mtb.oilgold', '', '', event);">
          <span class="tab3">
           유가 금시세
          </span>
         </a>
        </li>
        <li class="">
         <a href="./?tabSel=materials#tab_section" onclick="clickcr(this, 'mtb.material', '', '', event);">
          <span class="tab4">
           원자재
          </span>
         </a>
        </li>
       </ul>
       <h2 class="blind">
        환전고시 환율
       </h2>
      </div>
      <div class="section_calculator">
       <h3 class="h_calculator">
        <span>
         환율계산기 (매매기준율 기준)
        </span>
       </h3>
       <div class="calculator">
        <div class="inner">
         <div class="input">
          <div class="selectbox-noscript" id="sInput">
           <select class="selectbox-source" id="select_from">
            <option label="1" value="1">
             대한민국 원 KRW
            </option>
            <option class="selectbox-default" label="1" selected="selected" value="1076.0">
             미국 달러 USD
            </option>
            <option label="1" value="1076.0">
             미국 달러 USD
            </option>
            <option label="1" value="1260.27">
             유럽연합 유로 EUR
            </option>
            <option label="100" value="9.9002">
             일본 엔 JPY
            </option>
            <option label="1" value="168.17">
             중국 위안 CNY
            </option>
            <option label="1" value="137.11">
             홍콩 달러 HKD
            </option>
            <option label="1" value="35.98">
             대만 달러 TWD
            </option>
            <option label="1" value="1433.88">
             영국 파운드 GBP
            </option>
            <option label="1" value="2794.81">
             오만 리알 OMR
            </option>
            <option label="1" value="836.93">
             캐나다 달러 CAD
            </option>
            <option label="1" value="1089.68">
             스위스 프랑 CHF
            </option>
            <option label="1" value="122.57">
             스웨덴 크로나 SEK
            </option>
            <option label="1" value="816.2">
             호주 달러 AUD
            </option>
            <option label="1" value="753.36">
             뉴질랜드 달러 NZD
            </option>
            <option label="1" value="48.86">
             체코 코루나 CZK
            </option>
            <option label="1" value="1.71">
             칠레 페소 CLP
            </option>
            <option label="1" value="240.87">
             터키 리라 TRY
            </option>
            <option label="1" value="0.45">
             몽골 투그릭 MNT
            </option>
            <option label="1" value="301.65">
             이스라엘 세켈 ILS
            </option>
            <option label="1" value="169.3">
             덴마크 크로네 DKK
            </option>
            <option label="1" value="132.04">
             노르웨이 크로네 NOK
            </option>
            <option label="1" value="286.91">
             사우디아라비아 리얄 SAR
            </option>
            <option label="1" value="3561.03">
             쿠웨이트 디나르 KWD
            </option>
            <option label="1" value="2847.46">
             바레인 디나르 BHD
            </option>
            <option label="1" value="292.94">
             아랍에미리트 디르함 AED
            </option>
            <option label="1" value="1516.13">
             요르단 디나르 JOD
            </option>
            <option label="1" value="60.04">
             이집트 파운드 EGP
            </option>
            <option label="1" value="33.64">
             태국 바트 THB
            </option>
            <option label="1" value="805.06">
             싱가포르 달러 SGD
            </option>
            <option label="1" value="270.59">
             말레이시아 링깃 MYR
            </option>
            <option label="100" value="0.07769999999999999">
             인도네시아 루피아 IDR
            </option>
            <option label="1" value="295.52">
             카타르 리얄 QAR
            </option>
            <option label="1" value="3.26">
             카자흐스탄 텡게 KZT
            </option>
            <option label="1" value="807.47">
             브루나이 달러 BND
            </option>
            <option label="1" value="15.94">
             인도 루피 INR
            </option>
            <option label="1" value="9.29">
             파키스탄 루피 PKR
            </option>
            <option label="1" value="12.73">
             방글라데시 타카 BDT
            </option>
            <option label="1" value="20.5">
             필리핀 페소 PHP
            </option>
            <option label="1" value="54.53">
             멕시코 페소 MXN
            </option>
            <option label="1" value="288.96">
             브라질 레알 BRL
            </option>
            <option label="100" value="0.0472">
             베트남 동 VND
            </option>
            <option label="1" value="86.31">
             남아프리카 공화국 랜드 ZAR
            </option>
            <option label="1" value="17.34">
             러시아 루블 RUB
            </option>
            <option label="1" value="3.95">
             헝가리 포린트 HUF
            </option>
            <option label="1" value="292.81">
             폴란드 즈워티 PLN
            </option>
           </select>
           <div class="selectbox-box" onclick="clickcr(this, 'exl*c.clist1', '', '', event);">
            <div class="selectbox-label">
            </div>
           </div>
           <div class="selectbox-layer ly_calculator">
            <div class="selectbox-list">
            </div>
           </div>
          </div>
          <div class="input_area" id="input_from">
           <input id="input_from_money" maxlength="10" onclick="clickcr(this, 'exl*c.unit1', '', '', event);" onfocus="changeActiveInput('from', 'to'); return false;" onkeyup="calcExchange('from', 'to', 'on', event);" type="text" value="1"/>
           <img alt="" height="13" id="img_from_monetary" src="http://static.naver.com/nfinance/img_money_USD.gif" width="26"/>
          </div>
         </div>
         <div class="same">
          <img alt="" height="15" src="http://static.naver.com/nfinance/ico_same.gif" width="28"/>
         </div>
         <div class="view">
          <div class="selectbox-noscript" id="sView">
           <select class="selectbox-source" id="select_to">
            <option class="selectbox-default" label="1" value="1">
             대한민국 원 KRW
            </option>
            <option label="1" value="1">
             대한민국 원 KRW
            </option>
            <option label="1" value="1076.0">
             미국 달러 USD
            </option>
            <option label="1" value="1260.27">
             유럽연합 유로 EUR
            </option>
            <option label="100" value="9.9002">
             일본 엔 JPY
            </option>
            <option label="1" value="168.17">
             중국 위안 CNY
            </option>
            <option label="1" value="137.11">
             홍콩 달러 HKD
            </option>
            <option label="1" value="35.98">
             대만 달러 TWD
            </option>
            <option label="1" value="1433.88">
             영국 파운드 GBP
            </option>
            <option label="1" value="2794.81">
             오만 리알 OMR
            </option>
            <option label="1" value="836.93">
             캐나다 달러 CAD
            </option>
            <option label="1" value="1089.68">
             스위스 프랑 CHF
            </option>
            <option label="1" value="122.57">
             스웨덴 크로나 SEK
            </option>
            <option label="1" value="816.2">
             호주 달러 AUD
            </option>
            <option label="1" value="753.36">
             뉴질랜드 달러 NZD
            </option>
            <option label="1" value="48.86">
             체코 코루나 CZK
            </option>
            <option label="1" value="1.71">
             칠레 페소 CLP
            </option>
            <option label="1" value="240.87">
             터키 리라 TRY
            </option>
            <option label="1" value="0.45">
             몽골 투그릭 MNT
            </option>
            <option label="1" value="301.65">
             이스라엘 세켈 ILS
            </option>
            <option label="1" value="169.3">
             덴마크 크로네 DKK
            </option>
            <option label="1" value="132.04">
             노르웨이 크로네 NOK
            </option>
            <option label="1" value="286.91">
             사우디아라비아 리얄 SAR
            </option>
            <option label="1" value="3561.03">
             쿠웨이트 디나르 KWD
            </option>
            <option label="1" value="2847.46">
             바레인 디나르 BHD
            </option>
            <option label="1" value="292.94">
             아랍에미리트 디르함 AED
            </option>
            <option label="1" value="1516.13">
             요르단 디나르 JOD
            </option>
            <option label="1" value="60.04">
             이집트 파운드 EGP
            </option>
            <option label="1" value="33.64">
             태국 바트 THB
            </option>
            <option label="1" value="805.06">
             싱가포르 달러 SGD
            </option>
            <option label="1" value="270.59">
             말레이시아 링깃 MYR
            </option>
            <option label="100" value="0.07769999999999999">
             인도네시아 루피아 IDR
            </option>
            <option label="1" value="295.52">
             카타르 리얄 QAR
            </option>
            <option label="1" value="3.26">
             카자흐스탄 텡게 KZT
            </option>
            <option label="1" value="807.47">
             브루나이 달러 BND
            </option>
            <option label="1" value="15.94">
             인도 루피 INR
            </option>
            <option label="1" value="9.29">
             파키스탄 루피 PKR
            </option>
            <option label="1" value="12.73">
             방글라데시 타카 BDT
            </option>
            <option label="1" value="20.5">
             필리핀 페소 PHP
            </option>
            <option label="1" value="54.53">
             멕시코 페소 MXN
            </option>
            <option label="1" value="288.96">
             브라질 레알 BRL
            </option>
            <option label="100" value="0.0472">
             베트남 동 VND
            </option>
            <option label="1" value="86.31">
             남아프리카 공화국 랜드 ZAR
            </option>
            <option label="1" value="17.34">
             러시아 루블 RUB
            </option>
            <option label="1" value="3.95">
             헝가리 포린트 HUF
            </option>
            <option label="1" value="292.81">
             폴란드 즈워티 PLN
            </option>
           </select>
           <div class="selectbox-box" onclick="clickcr(this, 'exl*c.clist2', '', '', event);">
            <div class="selectbox-label">
            </div>
           </div>
           <div class="selectbox-layer ly_calculator">
            <div class="selectbox-list">
            </div>
           </div>
          </div>
          <div class="input_area" id="input_to">
           <input id="input_to_money" maxlength="10" onclick="clickcr(this, 'exl*c.unit2', '', '', event);" onfocus="changeActiveInput('to', 'from'); return false;" onkeyup="calcExchange('to', 'from', 'on', event);" type="text"/>
           <img alt="" height="13" id="img_to_monetary" src="http://static.naver.com/nfinance/img_money_KRW.gif" width="26"/>
          </div>
         </div>
        </div>
       </div>
      </div>
      <div class="section_exchange">
       <div id="section_ex1">
        <h3 class="blind" id="exchange1">
         환전 고시 환율
        </h3>
        <div class="exchange_info">
         <span class="date">
          2018.05.31 16:49
         </span>
         <span class="standard">
          KEB하나은행 기준
         </span>
         <span class="round">
          고시회차
          <em>
           282
          </em>
          회
         </span>
        </div>
        <iframe frameborder="0" height="1378px" id="frame_ex1" marginheight="0" marginwidth="0" scrolling="no" src="/marketindex/exchangeList.nhn" title="환전 고시 환율" width="100%">
        </iframe>
       </div>
       <ul class="tbl_info">
        <li>
         대부분의 통화명은 1달러가 다른 통화 기준으로 얼마인가를 나타내기 위해 국가명+화폐명/달러로 표기했습니다.
         <br/>
         예외로 유로, 영국파운드 등은 1유로가 달러로 얼마인가를 표기하는 경우가 많기 때문에 달러/유로로 표기했습니다.
        </li>
        <li>
         심볼은 앞에 위치한 통화에 1이 생략된 형태로 USDJPY인 경우 1USD(달러)가 JPY(일본 엔)으로 얼마인가를 의미합니다.
        </li>
        <li>
         통화명과 심볼로 네이버 금융검색을 하실 경우 해당 환율을 바로 조회하실 수 있습니다.
        </li>
       </ul>
      </div>
      <script language="javascript" src="/js/jindoComponent/jindo.Component.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.UIComponent.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.HTMLComponent.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.Timer.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.LayerManager.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.LayerPosition.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.RolloverArea.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.RolloverClick.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/jindoComponent/jindo.SelectBox.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script charset="euckr" language="javascript" src="/js/jindoComponent/jindo.TextRange.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script charset="euckr" language="javascript" src="/js/jindoComponent/jindo.WatchInput.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script charset="euckr" language="javascript" src="/js/jindoComponent/jindo.Formatter.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script charset="euckr" language="javascript" src="/js/jindoComponent/jindo.NumberFormatter.1.0.1.js?20180502015110" type="text/javascript">
      </script>
      <script language="javascript" src="/js/exchange.js?20180502015110" type="text/javascript">
      </script>
      <script type="text/javascript">
       // exchangeDetail.jsp에도 동일 스크립트 있음 - 로딩시 디자인이 0.5초간 디자인이 안뜬다는 이슈로 include하지 않고 같은 스크립트를 두벌로 관리함
    
    //환율 계산
    function calcExchange(str1, str2, cssOn, event) {
    	var oEvent = event || window.event;
        var sKeyCode = (undefined === oEvent) ? undefined : jindo.$Event(oEvent).key().keyCode;
    	
    	if (sKeyCode != 13 && sKeyCode != 27 && sKeyCode != 37 && sKeyCode != 38 && sKeyCode != 110 && sKeyCode != 229) {
    		if (str1 == '' && str2 == '') {
    			if (jindo.$('input_to').className == 'input_area') {
    				str1 = 'from';
    				str2 = 'to';
    			} else {
    				str1 = 'to';
    				str2 = 'from';
    			}
    		}
    		
    		var regExp = new RegExp("[^0-9\.\,]");
    	    var sInputValue = jindo.$('input_' + str1 + '_money').value;
    		
    	    if(regExp.test(sInputValue)){
    			alert('숫자, 소수점(.)만 입력하실 수 있습니다.');
    			jindo.$('input_' + str1 + '_money').value = revertInputText(sInputValue);
    			return false;
    		}
    		
    		// 사용자가 입력한 콤마(,) 제거
    	    if (sInputValue.substr(sInputValue.length - 1, 1) == ',') {
    	    	jindo.$('input_' + str1 + '_money').value = revertInputText(sInputValue);
    	    	return false;
    	    }
    		
    		// 맨 앞에 있는 숫자 0 없애기
    		if (sInputValue == '0' || sInputValue == '.' || sInputValue == ',') {
    			jindo.$('input_' + str1 + '_money').value = revertInputText(sInputValue);
    			return false;
    		}
    		
    		// 소수점 2개가 없도록
    		var match = sInputValue.match(/\./g);
    		if (match != null && match.length >= 2) {
    			jindo.$('input_' + str1 + '_money').value = revertInputText(sInputValue);
    			return false;
    		}
    		
    		// 소수점을 입력한 경우, 일단 대기
    		var pointPosIndex = sInputValue.indexOf('.');
    		if (pointPosIndex != -1 && pointPosIndex == sInputValue.length - 1) {
    			return false;
    		}
    		
    		// 소수점 2자리 유지
    		if (pointPosIndex != -1 && sInputValue.substring(pointPosIndex + 1, sInputValue.length).length > 2) {
    			jindo.$('input_' + str1 + '_money').value = revertInputText(sInputValue);
    			return false;
    		}
    		
    		var e_select_from	= jindo.$('select_'+str1);
    		var e_select_to	= jindo.$('select_'+str2);
    	
    		var input_from_money	= jindo.$('input_'+str1+'_money').value ;
    		var input_from		= e_select_from.options[e_select_from.selectedIndex].value ;
    		var input_to		= e_select_to.options[e_select_to.selectedIndex].value ;
    		var unit_from	= e_select_from.options[e_select_from.selectedIndex].text ;
    		var unit_to		= e_select_to.options[e_select_to.selectedIndex].text ;
    		input_from_money = input_from_money.replace(/ |,|\t/g, "") ;
    		input_from	= input_from.replace(/ |,|\t/g, "") ;
    		input_to	= input_to.replace(/ |,|\t/g, "") ;
    		unit_from = unit_from.substr(unit_from.length-3, 3);
    		unit_to = unit_to.substr(unit_to.length-3, 3);
    	
    		var str1_result = input_from_money * 1 ;
    		var str1_str	= str1_result.toFixed(0) ;
    		var str1_len = str1_str.length ;
    		var str1_result_str = new String("") ;
    	
    		if(str1_str > str1_result)
    			str1_str = new String(str1_str-1) ;
    	
    		if (str1_len >= 3) {
    			for (i = str1_len - 3; i > 0; i-=3)
    				str1_result_str = "," + str1_str.substr(i, 3) + str1_result_str ;
    	
    			str1_result_str = str1_str.substr(0, 3+i) + str1_result_str ;
    	
    			for (var i=0; i<input_from_money.length; i++) {
    				if (input_from_money.substr(i,1) != '0') {
    					input_from_money = input_from_money.substring(i,input_from_money.length) ;
    					break;
    				}
    			}
    	
    			if (str1_str != input_from_money) {
    				str1_result_str += str1_result.toFixed(input_from_money.split(".")[1].length).substr(str1_len, input_from_money.split(".")[1].length + 1) ;
    			}
    		} else
    			str1_result_str = input_from_money ;
    	
    		var str2_result = input_from_money * input_from / input_to ;
    		var str2_str	= str2_result.toFixed(0) ;
    		var str2_len = str2_str.length ;
    		var str2_result_str = new String("") ;
    	
    		if (str2_str > str2_result)
    			str2_str = new String(str2_str-1) ;
    	
    		if (str2_len >= 3) {
    			for (i = str2_len - 3; i > 0; i-=3)
    				str2_result_str = "," + str2_str.substr(i, 3) + str2_result_str ;
    	
    			str2_result_str = str2_str.substr(0, 3+i) + str2_result_str ;
    			str2_result_str += str2_result.toFixed(2).substr(str2_len, 3) ;
    		} else
    			str2_result_str = str2_result.toFixed(2) ;
    	
    		jindo.$('input_'+str1+'_money').value = str1_result_str;
    		jindo.$('input_'+str2+'_money').value = str2_result_str;
    		jindo.$('img_'+str1+'_monetary').src = "http://static.naver.com/nfinance/img_money_"+unit_from+".gif";
    		jindo.$('img_'+str2+'_monetary').src = "http://static.naver.com/nfinance/img_money_"+unit_to+".gif";
    		jindo.$Element(jindo.$('input_'+str1)).addClass("on");
    		jindo.$Element(jindo.$('input_'+str2)).removeClass("on");
    		if (cssOn == "off"){
    			jindo.$Element(jindo.$('input_'+str1)).removeClass("on");
    		}
    	}
    }
    
    function revertInputText(sOrgText) {
    	var sResult = sOrgText;
    	
    	if (sOrgText != '') {
    		sResult = sOrgText.substr(0, sOrgText.length - 1);
    	}
    	
    	return sResult;
    }
    
    jindo.$Fn(function(){
    	chartMouseOverEvent('exchangeList');		
       }).attach(document, "domready");
      </script>
     </div>
     <script language="javascript" src="http://finance.naver.com/js/jindo_ellipse.js?20180502015110">
     </script>
     <script language="javascript" src="/js/util.js?20180502015110">
     </script>
     <script type="text/javascript">
      function ellipseTopNewsTitle() {
    	jindo.EllipseText.factory(jindo.$$(".news_list ul li"), {nAssistWidth: 10});
    }
    
    
    var basicDates;
    
    function initDate() {
    	basicDates = jindo.$H();
    	basicDates.add('', '');
    	basicDates.add('', '');
    	basicDates.add('', '');
    	basicDates.add('', '');
    	basicDates.add('', '');
    	basicDates.add('', '');
    }
    
    var basicDescriptions;
    
    function initDescription() {
    	basicDescriptions = jindo.$H();
    	basicDescriptions.add('CMDT_CDY','<em></em>  기준<span>단위:</span>');
    	basicDescriptions.add('CMDT_PDY','<em></em>  기준<span>단위:</span>');
    	basicDescriptions.add('CMDT_NG','<em></em>  기준<span>단위:</span>');
    	basicDescriptions.add('CMDT_S','<em></em>  기준<span>단위:</span>');
    	basicDescriptions.add('CMDT_C','<em></em>  기준<span>단위:</span>');
    	basicDescriptions.add('CMDT_SB','<em></em>  기준<span>단위:</span>');
    }
    
    function setEvent(num, imgChartUrl){	
    	var parentElemnt = jindo.$$('.tbl_market')[num];
    	var elementList = jindo.$$('tr',parentElemnt);
    	
    	jindo.$Fn(function(e){	
    		var elementListSize = elementList.length;
    		
    		for(var i = 0 ; i < elementListSize ; i ++)
    		{
    			var selectedElement = jindo.$Element(elementList[i]);
    			var selectedClassName = selectedElement.className();
    			if (selectedClassName != "") {
    				selectedElement.removeClass(selectedClassName);
    				selectedElement.addClass(selectedClassName.replace("on",""));
    			}
    		} 
    		
    		var ele = jindo.$Element(jindo.$Event(e).currentElement);
    		var linkUrl = jindo.$$.getSingle('a' , ele.$value()).href;
    		var marketindexCd = linkUrl.split('=')[1];
    		var className = ele.className();
    		ele.removeClass(className);
    		ele.addClass(className+" on");
    		var graphElement = jindo.$Element(jindo.$$('.thum')[num]);
    		graphElement.html('<a href=\"'+linkUrl+'\"><img src=\"http://imgfinance.naver.net/chart/marketindex/' + marketindexCd + '.png\" width=\"295\" height=\"153\" alt=""></a>');
    		
    		if (basicDates.hasKey(marketindexCd)) {
    			jindo.$Element("basicDate").text(basicDates.$(marketindexCd));
    		}
    		if (basicDescriptions.hasKey(marketindexCd)) {
    			jindo.$Element("basicDescription").html(basicDescriptions.$(marketindexCd));
    		}
    	
    	}).attach(elementList, "mouseover");	
    }
    
    jindo.$Fn(function(){
    		initDate();
    		initDescription();
    		chartMouseOverEvent('exchangeList');
    		chartMouseOverEvent('worldExchangeList');
    		chartMouseOverEvent('oilGoldList');
    		//setEvent(0);
    		//setEvent(1);
    		jindo.$$('title')[0].innerHTML = "시장지표 : 네이버 금융";
    }).attach(document, "domready");
     </script>
     <div class="aside" id="marketindex_aside">
      <div class="section_aside">
       <h3 class="h_interest">
        <span>
         국내시장금리
        </span>
       </h3>
       <table class="tbl_exchange market" summary="국제시장 환율 리스트">
        <caption>
         국내시장금리
        </caption>
        <colgroup>
         <col width="94"/>
         <col width="50"/>
         <col width="75"/>
        </colgroup>
        <thead>
         <tr>
          <th>
           구분
          </th>
          <th>
           금리
          </th>
          <th>
           등락율
          </th>
         </tr>
        </thead>
        <tbody>
         <tr class="same">
          <th class="th_inter4">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_CD91" onclick="clickcr(this, 'rid.local', 'IRR_CD91', '1', event);">
            <span>
             CD금리(91일)
            </span>
           </a>
          </th>
          <td>
           1.65
          </td>
          <td>
           <img alt="보합" height="6" src="http://static.naver.com/nfinance/ico_same2.gif" width="7"/>
           0.00
          </td>
         </tr>
         <tr class="up">
          <th class="th_inter1">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_CALL" onclick="clickcr(this, 'met.8', 'IRR_CALL', '2', event);">
            <span>
             콜 금리
            </span>
           </a>
          </th>
          <td>
           1.52
          </td>
          <td>
           <img alt="상승" height="6" src="http://static.naver.com/nfinance/ico_up.gif" width="7"/>
           0.02
          </td>
         </tr>
         <tr class="up">
          <th class="th_inter2">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_GOVT03Y" onclick="clickcr(this, 'met.8', 'IRR_GOVT03Y', '3', event);">
            <span>
             국고채 (3년)
            </span>
           </a>
          </th>
          <td>
           2.20
          </td>
          <td>
           <img alt="상승" height="6" src="http://static.naver.com/nfinance/ico_up.gif" width="7"/>
           0.01
          </td>
         </tr>
         <tr class="same">
          <th class="th_inter3">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_CORP03Y" onclick="clickcr(this, 'met.8', 'IRR_CORP03Y', '4', event);">
            <span>
             회사채 (3년)
            </span>
           </a>
          </th>
          <td>
           2.82
          </td>
          <td>
           <img alt="보합" height="6" src="http://static.naver.com/nfinance/ico_same2.gif" width="7"/>
           0.00
          </td>
         </tr>
         <tr class="up">
          <th class="th_inter5">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_COFIXBAL" onclick="clickcr(this, 'met.8', 'IRR_COFIXBAL', '5', event);">
            <span>
             COFIX 잔액
            </span>
           </a>
          </th>
          <td>
           1.80
          </td>
          <td>
           <img alt="상승" height="6" src="http://static.naver.com/nfinance/ico_up.gif" width="7"/>
           0.02
          </td>
         </tr>
         <tr class="down">
          <th class="th_inter6">
           <a href="/marketindex/interestDetail.nhn?marketindexCd=IRR_COFIXNEW" onclick="clickcr(this, 'met.8', 'IRR_COFIXNEW', '6', event);">
            <span>
             COFIX 신규취급액
            </span>
           </a>
          </th>
          <td>
           1.79
          </td>
          <td>
           <img alt="하락" height="6" src="http://static.naver.com/nfinance/ico_down.gif" width="7"/>
           0.03
          </td>
         </tr>
        </tbody>
       </table>
       <table class="tbl_exchange tbl_exchange_v1 market" style="margin-top:10px;" summary="달러 인덱스">
        <caption>
         달러 인덱스
        </caption>
        <colgroup>
         <col width="88"/>
         <col width="46"/>
         <col width="66"/>
        </colgroup>
        <thead>
         <tr>
          <th>
           구분
          </th>
          <th>
           금리
          </th>
          <th>
           등락율
          </th>
         </tr>
        </thead>
        <tbody>
         <tr class="other_t1 down">
          <th class="th_inter7">
           <a href="/marketindex/worldExchangeDetail.nhn?marketindexCd=FX_USDX&amp;fdtc=4" onclick="clickcr(this, 'rid.dollar', 'FX_USDX', '', event);">
            <span>
             달러 인덱스
            </span>
           </a>
          </th>
          <td>
           94.1100
          </td>
          <td>
           <img alt="하락" height="6" src="http://static.naver.com/nfinance/ico_down.gif" width="7"/>
           0.6700
          </td>
         </tr>
        </tbody>
       </table>
      </div>
      <div class="section_aside">
       <div class="tab_search search3">
        <a href="#" onclick="clickcr(this, 'rch.1', '', '', event); return false;">
         <span>
          최근검색
         </span>
        </a>
        <a href="#" onclick="clickcr(this, 'rch.3', '', '', event); return false;">
         <span>
          MY STOCK
         </span>
        </a>
       </div>
       <h3 class="blind">
        최근검색
       </h3>
       <table class="tbl_search" summary="최근검색 리스트">
        <caption>
         최근검색
        </caption>
        <colgroup>
         <col/>
         <col width="55"/>
         <col width="87"/>
        </colgroup>
        <thead>
         <tr>
          <th>
           업체명
          </th>
          <th>
           거래량
          </th>
          <th>
           전일비
          </th>
         </tr>
        </thead>
        <tbody>
        </tbody>
       </table>
       <div class="more_info">
        <span>
         <a href="#" onclick="clickcr(this, 'rch.5', '', '', event); return false;">
          <img alt="이전" height="15" src="http://static.naver.com/nfinance/btn_prev2.gif" width="17"/>
         </a>
         <a href="#" onclick="clickcr(this, 'rch.6', '', '', event); return false;">
          <img alt="다음" height="15" src="http://static.naver.com/nfinance/btn_next2.gif" width="17"/>
         </a>
        </span>
        <a class="btn_more" href="#" onclick="javascript:openMyitemNew('http://finance.naver.com'); clickcr(this, 'rch.7', '', '', event);">
         <img alt="더보기" height="10" src="http://static.naver.com/nfinance/btn_more5.gif" width="33"/>
        </a>
       </div>
      </div>
      <div class="section_aside">
       <h3 class="h_report">
        <span>
         경제분석 리포트
        </span>
       </h3>
       <ul class="list_report">
        <li>
         <a href="http://finance.naver.com/research/economy_read.nhn?nid=5487" onclick="clickcr(this, 'rer.list', '', '', event);">
          국내외 경제이슈
         </a>
        </li>
        <li>
         <a href="http://finance.naver.com/research/economy_read.nhn?nid=5486" onclick="clickcr(this, 'rer.list', '', '', event);">
          이탈리아 정국 혼란, 이탈렉시트는...
         </a>
        </li>
        <li>
         <a href="http://finance.naver.com/research/economy_read.nhn?nid=5485" onclick="clickcr(this, 'rer.list', '', '', event);">
          美中 충돌 4라운드, 과도한 비관...
         </a>
        </li>
        <li>
         <a href="http://finance.naver.com/research/economy_read.nhn?nid=5484" onclick="clickcr(this, 'rer.list', '', '', event);">
          위기 확산의 필요조건
         </a>
        </li>
        <li>
         <a href="http://finance.naver.com/research/economy_read.nhn?nid=5483" onclick="clickcr(this, 'rer.list', '', '', event);">
          국내외 경제이슈
         </a>
        </li>
       </ul>
       <a class="btn_more" href="http://finance.naver.com/research/economy_list.nhn" onclick="clickcr(this, 'rer.more', '', '', event);">
        <img alt="경제분석 리포트 더보기" height="18" src="http://static.naver.com/nfinance/btn_more.gif" width="34"/>
       </a>
      </div>
     </div>
     <script language="javascript" src="/js/myStock.js?20180502015110" type="text/javascript">
     </script>
     <script language="javascript" src="/js/util.js?20180502015110" type="text/javascript">
     </script>
     <script language="javascript">
      function toggleTabSearch(e){
    	var currentElement = jindo.$Element(jindo.$Event(e).currentElement);
    	var parentElement = currentElement.parent();
    	var id = currentElement.className();
    	var order = parentElement.indexOf(currentElement) + 3;
    	parentElement.className("tab_search search"+ order);
    
    	// 페이징을 위해서 order값에 따라 최근검색인지 mystock인지 type을 저장
    	if (order == 3) {
    		currentType = "recent";
    	} else {
    		currentType = "mystock";
    	}	
    }
    
    jindo.$Fn(function(){
    	if ('true' == 'true') {
    		getStockRightMenuData('000000', 'recent', 1, 'http://finance.naver.com', 'http://static.naver.com/nfinance');
    		
    		var tabSearchArea = jindo.$$.getSingle('.tab_search');
    		var moreInfoArea = jindo.$Element(jindo.$$.getSingle('.tbl_search')).next().$value();
    		
    		jindo.$Fn(function(e) {toggleTabSearch(e); getStockRightMenuData('000000', 'recent', 1, 'http://finance.naver.com', 'http://static.naver.com/nfinance'); }).attach(jindo.$$.getSingle('a' ,tabSearchArea), 'click');		
    		jindo.$Fn(function(e) {toggleTabSearch(e); getStockRightMenuData('000000', 'mystock', 1, 'http://finance.naver.com', 'http://static.naver.com/nfinance'); }).attach(jindo.$$('a' ,tabSearchArea)[1], 'click');
    		jindo.$Fn(function(e) {updatePageForPaging (currentType, 'up', 'http://finance.naver.com', 'http://static.naver.com/nfinance'); }).attach(jindo.$$.getSingle('a', moreInfoArea), 'click');		
    		jindo.$Fn(function(e) {updatePageForPaging (currentType, 'down', 'http://finance.naver.com', 'http://static.naver.com/nfinance'); }).attach(jindo.$$('a', moreInfoArea)[1], 'click');
    	} 
    
    }).attach(document,"domready");
    
    function openMyitemNew(stockHost) {
    	var selectedElement = jindo.$Element(jindo.$$.getSingle(".tab_search"));
    	if (selectedElement != null) {
    		if (selectedElement.hasClass("search1")) {
    			document.location.href = stockHost + '/mystock/recentSearchItemList.nhn';
    		} else {
    			document.location.href = stockHost + '/mystock/itemList.nhn';
    		}
    	}
    }
     </script>
    </div>
    <div id="footer">
     <ul>
      <li class="first">
       <a href="http://www.naver.com/rules/service.html" onclick="clickcr(this, 'fot.service', '', '', event);" target="_blank">
        이용약관
       </a>
      </li>
      <li>
       <a href="http://finance.naver.com/rules.nhn" onclick="clickcr(this, 'fot.policy', '', '', event);" target="_blank">
        금융게시판 운영원칙
       </a>
      </li>
      <li>
       <a href="http://www.naver.com/rules/privacy.html" onclick="clickcr(this, 'fot.privacy', '', '', event);" target="_blank">
        <strong>
         개인정보처리방침
        </strong>
       </a>
      </li>
      <li>
       <a href="http://www.naver.com/rules/disclaimer.html" onclick="clickcr(this, 'fot.limit', '', '', event);" target="_blank">
        책임의 한계와 법적고지
       </a>
      </li>
      <li>
       <a href="https://help.naver.com/support/alias/contents2/finance/finance_1.naver" onclick="clickcr(this, 'fot.help', '', '', event);" target="_blank">
        금융 고객센터
       </a>
      </li>
     </ul>
     <p class="desc">
      네이버(주)에서 제공하는 금융정보는 투자 참고 사항이며, 오류가 발생할 수 있고 지연될 수 있습니다.
      <br/>
      네이버(주)는 제공된 정보에 의한 투자결과에 대한 법적인 책임을 지지 않습니다. 또한 게시된 정보를 무단으로 배포할 수 없습니다.
     </p>
     <address>
      <a class="logo" href="http://www.navercorp.com/" onclick="clickcr(this, 'fot.nhn', '', '', event);" target="_blank">
       <img alt="NAVER" height="11" src="http://static.naver.net/common/footer/ci_naver.gif" width="63"/>
      </a>
      <em>
       Copyright ©
      </em>
      <a href="http://www.navercorp.com/" onclick="clickcr(this, 'fot.nhn', '', '', event);" target="_blank">
       NAVER Corp.
      </a>
      <span>
       All Rights Reserved.
      </span>
     </address>
    </div>
    <script type="text/javascript">
     function isVisible(obj) {
        if (obj == document) return true
     
        if (!obj) return false
        if (!obj.parentNode) return false
        if (obj.style) {
            if (obj.style.display == 'none') return false
            if (obj.style.visibility == 'hidden') return false
        }
     
        if (window.getComputedStyle) {
            var style = window.getComputedStyle(obj, "")
            if (style.display == 'none') return false
            if (style.visibility == 'hidden') return false
        }
     
        var style = obj.currentStyle
        if (style) {
            if (style['display'] == 'none') return false
            if (style['visibility'] == 'hidden') return false
        }
     
        return isVisible(obj.parentNode)
    }
    
    function isChildOf(myobj, containerObj) {
    	while(myobj != undefined) {
    		if (myobj == document.body) {
    			break;
    		} 
    		if (myobj == containerObj) {
    			return true;
    		}
    		myobj = myobj.parentElement;
    	}
    	return false;	
    }
    
    function gnbLayerClose(e){
    	var target = e.target ? e.target : e.srcElement;
    	if (isVisible(document.getElementById('gnb_service_lyr')) || isVisible(document.getElementById('gnb_notice_lyr')) ||isVisible(document.getElementById('gnb_my_lyr')) ) {
    		if (!isChildOf(target, document.getElementById('gnb'))) {
    			gnbAllLayerClose();
    		}
    	}	
    }
    
    var isIE = (navigator.userAgent.toLowerCase().indexOf("msie")!=-1 && window.document.all) ? true:false;
    if (isIE) {
    	document.attachEvent('onmousedown', gnbLayerClose);
    } else {
    	window.addEventListener('mousedown', gnbLayerClose);
    }
    </script>
    



```python
soup.find_all('span', 'value')[0].string
```




    '1,076.00'



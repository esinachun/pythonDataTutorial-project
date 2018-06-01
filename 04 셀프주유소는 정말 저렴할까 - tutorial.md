

```python
from selenium import webdriver
```


```python
#자동으로 웹페이지 띄워보기
driver = webdriver.Chrome('../driver/chromedriver')
driver.get("http://naver.com")                        
```


```python
driver.save_screenshot('../images/001.jpg')
```

    /Users/wonbang/anaconda3/lib/python3.6/site-packages/selenium/webdriver/remote/webdriver.py:1009: UserWarning: name used for saved screenshot does not match file type. It should end with a `.png` extension
      "type. It should end with a `.png` extension", UserWarning)





    True




```python
#자동으로 로그인창 입력
xpath = """//*[@id="account"]/div/a/i"""
driver.find_element_by_xpath(xpath).click()

elem_login = driver.find_element_by_id("id")
elem_login.clear() #입력된 경우 clear
elem_login.send_keys("esinachun")

elem_login = driver.find_element_by_id("pw")
elem_login.clear
elem_login.send_keys("96adeaa6!")

xpath = """//*[@id="frmNIDLogin"]/fieldset/input"""
driver.find_element_by_xpath(xpath).click()
```


```python
driver.get("http://mail.naver.com")
```


```python
from bs4 import BeautifulSoup

html = driver.page_source
soup = BeautifulSoup(html, 'html.parser')
```


```python
raw_list = soup.find_all('div', 'name _ccr(lst.from) ')
raw_list
```




    [<div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8826) _stopDefault" href="#" title='"티몬" &lt;noreply@ticketmonster.co.kr&gt;'>티몬</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8825) _stopDefault" href="#" title='"티몬" &lt;noreply@ticketmonster.co.kr&gt;'>티몬</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8824) _stopDefault" href="#" title='"중고카페 그린유즈 (중고.패션.맘.유아.폰.가전.가구.원룸.차)" &lt;navercafe@naver.com&gt;'>중고카페 그린유즈 (..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8823) _stopDefault" href="#" title='"박경현" &lt;dlrudal8@edgeideas.co.kr&gt;'>박경현</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8822) _stopDefault" href="#" title='"중고카페 그린유즈 (중고.패션.맘.유아.폰.가전.가구.원룸.차)" &lt;navercafe@naver.com&gt;'>중고카페 그린유즈 (..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8821) _stopDefault" href="#" title='"zzixx" &lt;letter@zzixx.com&gt;'>zzixx</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8820) _stopDefault" href="#" title='"중고카페 그린유즈 (중고.패션.맘.유아.폰.가전.가구.원룸.차)" &lt;navercafe@naver.com&gt;'>중고카페 그린유즈 (..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8819) _stopDefault" href="#" title='"히어로" &lt;herosolution@nate.com&gt;'>히어로</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8818) _stopDefault" href="#" title='"중고카페 그린유즈 (중고.패션.맘.유아.폰.가전.가구.원룸.차)" &lt;navercafe@naver.com&gt;'>중고카페 그린유즈 (..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8817) _stopDefault" href="#" title='"중고나라" &lt;navercafe@naver.com&gt;'>중고나라</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8816) _stopDefault" href="#" title='"아사모 -[아이폰, 아이폰8 /8+ , 아이폰X, 아이패드, 애플워치3]" &lt;navercafe@naver.com&gt;'>아사모 -[아이폰, 아..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8815) _stopDefault" href="#" title='"Kakao Developers" &lt;noreply@kakaocorp.com&gt;'>Kakao Developers</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8814) _stopDefault" href="#" title='"중고나라" &lt;navercafe@naver.com&gt;'>중고나라</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8813) _stopDefault" href="#" title='"중소벤처기업부인증법인 (주)한국기업컨설팅" &lt;hdvoice82@naver.com&gt;'>중소벤처기업부인증..</a></div>,
     <div class="name _ccr(lst.from) "><span class="blind">보낸 이:</span><a class="_c1(myContextMenu|showSenderContextLayer|list|8812) _stopDefault" href="#" title='"중고나라" &lt;navercafe@naver.com&gt;'>중고나라</a></div>]




```python
send_list = [raw_list[n].find('a').get_text() for n in range(0, len(raw_list))]
send_list
```




    ['티몬',
     '티몬',
     '중고카페 그린유즈 (..',
     '박경현',
     '중고카페 그린유즈 (..',
     'zzixx',
     '중고카페 그린유즈 (..',
     '히어로',
     '중고카페 그린유즈 (..',
     '중고나라',
     '아사모 -[아이폰, 아..',
     'Kakao Developers',
     '중고나라',
     '중소벤처기업부인증..',
     '중고나라']




```python
driver.close()
```

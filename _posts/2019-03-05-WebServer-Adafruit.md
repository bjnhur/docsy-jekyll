---
title: 'IPv6 WebServer example with WIZnet W6100 chip'
author: bongjun.hur
date: 2019-03-05 13:00
image: /files/covers/home-office-336581_1280.jpg
cover:
  title: "Home office"
  link: https://pixabay.com/photo-336581/
  author:
    name: "Unsplash"
    link: https://pixabay.com/ko/users/Unsplash-242387/
tags: [arduino,WIZnet,W6100,IPv6]
excerpt: WebServer
---

(Modified) 2019-03-03

<a id="forkme" href="https://github.com/WIZnet-ArduinoEthernet/WebServer-Adafruit"></a>

## WebServer Example

WebServer-Adafruit (https://github.com/WIZnet-ArduinoEthernet/WebServer-Adafruit) W6100의 IPv4, IPv6 Dual Stack을 이용한 WebServer Example 입니다.
![](https://66.media.tumblr.com/b48b4dce36ab52df61e60c0ae4a175ee/tumblr_inline_pnx4cmjzSQ1vss9ba_540.png)

Browser로 접속하면 Host의 IPv4 또는 IPv6 주소가 Adafruit의 OLED SSD1306에 출력됩니다.
![](https://66.media.tumblr.com/60270a95722ec3839bef981dcfaaeb3c/tumblr_inline_pnx4f7WPQq1vss9ba_540.png)

## WIZnet Ethernet Library IPv6

Github WIZnet Arduino Ethernet Library (https://github.com/Wiznet/Ethernet)

IPv6 Branch를 선택합니다.

Arduino IDE를 Default로 설치하면 Library Manager를 통해 Download한 Library는

'C:\Users\Your ID\Documents\Arduino\libraries'에 위치 합니다.

Download한 WIZnet Arduino Ethernet Library가 아래와 같은 경로를 갖도록 합니다.

**C:\Users\Your ID\Documents\Arduino\libraries\Ethernet**
![](https://66.media.tumblr.com/0f726c5f209bc2dabb75498afe565297/tumblr_inline_pnx4gkqAv31vss9ba_540.png)![](/assets/images/WIZnetEthernetIPv6.png)

## Adafruit GFX Library

Adafruit GFX Library (https://github.com/adafruit/Adafruit-GFX-Library)

Version 1.4.2로 Test 하였습니다.

Library Manager를 통해 Download 합니다.

## Adafruit SSD1306 Library

Adafruit SSD1306 Library (https://github.com/adafruit/Adafruit_SSD1306)

Version 1.2.9로 Test 하였습니다.

Library Manager를 통해 Download 합니다.

## WebServer-Adafruit

WebServer-Adafruit Download하고, 실행하여 WebServer를 실행합니다. WebServer-Adafruit는 Web Browser로 접속하면 Host의 IPv4 또는 IPv6 주소를 Adafruit의 OLED SSD1306에 출력합니다. 그리고 Message를 전송할 수도 있습니다.

## IPv4 Test
![](https://66.media.tumblr.com/9672b56af8a714ad6d08d353aa2c983a/tumblr_inline_pnx4jaSzDU1vss9ba_540.png)![](https://66.media.tumblr.com/60270a95722ec3839bef981dcfaaeb3c/tumblr_inline_pnx4ksqVnQ1vss9ba_540.png)![](/assets/images/IPv4.png)![](/assets/images/IPv4-Connect-Message.JPG)

## IPv6 LLA
![](https://66.media.tumblr.com/20d5a81620ea8d5152dbb8bb17b5004b/tumblr_inline_pnx4l6tqih1vss9ba_540.png)![](https://66.media.tumblr.com/f97518c65dfb4028df5a4b7c30833249/tumblr_inline_pnx4mmE5a31vss9ba_540.png)

## Bug 발견

버그가 발견되었다. 이젠 직접 본격적으로 라이브러리나 예제를 개선해 볼까나~~
![](https://66.media.tumblr.com/14e5c7d83244f3c61e2357cf5dda8ea3/tumblr_inline_pnx4ovAvsg1vss9ba_540.png)

메시지를 출력하는 과정에서 메시지 이외의 패킷 내용이 표기되어 이를 수정하고자 한다.
![](https://66.media.tumblr.com/f5d904b58f9b1046e89cb213462f714c/tumblr_inline_pnx4pn1LrS1vss9ba_540.png)

일단, 이 예제를 Clone 하여 자신의 로컬 PC에 개발 환경을 구축하고, 문제가 있는 부분을 빨리 수정한다. (남들이 하기전에 82828282)
![](https://66.media.tumblr.com/2748c74f6749b76520865f3752aaea34/tumblr_inline_pnx4t4PTEG1vss9ba_540.png)

다행이 아주 간단하게 해결 할 수 있었다. 메시지의 끝을 체크하는 코드를 추가하여 테스트 해보자..우선 컴파일
![](https://66.media.tumblr.com/f70ec9d7bc8db52869654ea552a5f489/tumblr_inline_pnx4vhy6Os1vss9ba_540.png)

다운로드 후 실행..다시 해볼까?
![](https://66.media.tumblr.com/14e5c7d83244f3c61e2357cf5dda8ea3/tumblr_inline_pnx4x6tp9E1vss9ba_540.png)

결과는&nbsp; 아래와 같이&nbsp;동작이 잘 되었다.&nbsp;
![](https://66.media.tumblr.com/95189959afb54280c0f59b6d81a7e940/tumblr_inline_pnx4y0yaiP1vss9ba_540.png)

그럼 이제 GitHub 저장소를 업데이트 해보자.

## Reusable Library Update

Clone 되어 있는 환경에서 일단&nbsp;“hotfix” 라는 브랜치를 만들어, 로컬에서 테스트 한 코드를 수정해서 commit 을 진행한다.
![](https://66.media.tumblr.com/6756661fa1c85f434e8c85bd7b9f61b1/tumblr_inline_pnx54jY4UT1vss9ba_540.png)

이미 테스트해서 검증한 소스이므로, 검증 과정은 생략하고 (원래는 이 부분이 가장 중요하다) 이제 master branch로 pull request를 진행해 본다.&nbsp;

메뉴에서 간단하게 선택하면 된다.
![](https://66.media.tumblr.com/e461d9e010742fd4b653360fd90dc7ae/tumblr_inline_pnx592pbLK1vss9ba_540.png)

이 과정에서&nbsp;“hotfix” 브랜치로 작업을 진행했고, 저장소에는 이 브랜치가 없으므로 이 정보를 먼저 업데이트 한다는 메시지가 뜬다. 그냥 “Publish” 하고 진행하면 된다.
![](https://66.media.tumblr.com/282378f8b5298914785c5bcbbf296148/tumblr_inline_pnx5buwdEl1vss9ba_540.png)

이 과정이 종료되면, 브라우저가 GitHub 사이트를 띄우면서 Pull request 과정을 진행하게 된다.
![](https://66.media.tumblr.com/a1a7f0c94058afa78f57f2bbb31b5e12/tumblr_inline_pnx5ecRKdf1vss9ba_540.png)

Pull request 를 보내면, 아래 그림처럼 Pull request 를 처리해서&nbsp;“Merge” 할지 말지 처리하는 버튼이 아래와 같이 등장하게 된다.
![](https://66.media.tumblr.com/1508cb38f5d4c848b432a33937a9a136/tumblr_inline_pnx5exykOW1vss9ba_540.png)

관리자는 코드 리뷰를 먼저하고, 이 코드를 수용할 지 아닌지 결정하면 된다. 해당 코드는 일단 검증이 된 관계로 바로&nbsp;“Merge” 과정을 진행해 보자.

아래와 같이&nbsp;“Merge” 버튼을 누르면 아래와 같이 2가지 중에 하나를 선택해야 한다.
![](https://66.media.tumblr.com/bf0c658d0534a6763ce404c6d711a3db/tumblr_inline_pnx5l1fK3S1vss9ba_540.png)

개발 브랜치의 Commit 내용을 전부 가지고 Merge를 할 것이냐, 아니면 1개의 commit 으로 생략해서 Merge를 할 것이냐 선택을 하는 것이다.

우리는 Merge comment 를 추가로 입력할 수 있으므로, 일반적으로&nbsp;“2번”을 선택하도록 한다. (중요한 commit 이 남아야 한다면 반드시&nbsp;“1번”을 선택하도록!!!)

자 그럼, Merge comment를 추가하고 아래와 같이 버튼을 눌러 master 브랜치를 업데이트 해보자.
![](https://66.media.tumblr.com/89b467f6041f5e78b15fa8f1d30489c5/tumblr_inline_pnx5p1pgxR1vss9ba_540.png)

그럼 성공되었다는 메시지와 함께 요청한 Pull request 는 자동으로 close 된다.
![](https://66.media.tumblr.com/762675fa9b612d3a81c088c1ce753e3b/tumblr_inline_pnx5sglKOO1vss9ba_540.png)

여기서 잠깐!! 작업한&nbsp;“hotfix” 브랜치는 더이상 필요가 없으므로 위의 그림의&nbsp;“Delete branch”를 눌러 삭제하는 것이 좋다.

이 삭제 과정은 로컬에서 아래 그림과 같이 수행해도 된다.
![](https://66.media.tumblr.com/00628319d010c809894c80005c1a7d03/tumblr_inline_pnx5uvWVPs1vss9ba_540.png)

당연히 GitHub 저장소에 있는 브랜치도 같이 삭제하는 것이 좋겠죠 ^^.
![](https://66.media.tumblr.com/e89729e0258277df2aff1682710a5d97/tumblr_inline_pnx5v6xjQ41vss9ba_540.png)

이제 아주 깨끗해진 저장소를 볼 수 있다.
![](https://66.media.tumblr.com/cf732ab1f7d7411cb3eaded638c09b24/tumblr_inline_pnx5xilC0l1vss9ba_540.png)

이상, GitHub 저장소에 오픈된 라이브러리의 활용법과 기여를 하는 방법에 대해 모든 과정을 살펴보았다. 이젠 자신있게 똘똘한 자식들을 많이 만들어 보자. 보물 찾으러 고고!!

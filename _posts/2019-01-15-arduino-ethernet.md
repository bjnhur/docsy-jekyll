---
title: 'The state of Arduino Ethernet Library'
author: bongjun.hur
date: 2019-01-15 13:11
image: /files/covers/home-office-336581_1280.jpg
cover:
  title: "Home office"
  link: https://pixabay.com/photo-336581/
  author:
    name: "Unsplash"
    link: https://pixabay.com/ko/users/Unsplash-242387/
tags: [Arduino,Ethernet,WIZnet,W5500,W5100]
excerpt: Arudino Ethernet materials
---

(Modified) 2019-01-15

최근 Arduino Ethernet Library 업데이트 내용과 유용한 몇개의 라이브러리와 관련 예제를 정리해 본다.

# 라이브러리 정보
## 최근 업데이트 된 라이브러리
- [Arduino Ethernet Library v2.0](https://github.com/arduino-libraries/Ethernet) - Arduino official
    - Runtime에 자동으로 연결되어 있는 칩셋을 알아내고, 알맞는 드라이버를 자동으로 선택하도록 개선되었다.
    - W5100, W5200, W5500 어떤 칩을 사용하는 하드웨어를 연결하더라도 드라이버에서 자동으로 제어할 수 있다.
        - 즉, 칩셋을 변경하기 위해 소스코드를 수정할 필요가 없다!!
    - 최근에 출시된 [Arduino MKR ETH shield](https://www.arduino.cc/en/Guide/MKRETHShield) 제품을 사용한다면 필수!!
        ![MKRETH](https://www.arduino.cc/en/uploads/Guide/MKRETH_featured.jpg)
- [WIZnet fork version - supports W5100S & W6100](https://github.com/wiznet/Ethernet)
    - WIZnet version, W5100S와 W6100등의 최신 칩셋을 지원하기 위해 WIZnet 에서 개발중인 드라이버 버전
    - Arduino MKR zero 보드를 이용한 응용 예제
        - <iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/bjnhur/rgb-control-with-mobile-app-f83f48/embed' width='350'></iframe>
        - <iframe frameborder='0' height='327.5' scrolling='no' src='https://www.hackster.io/bjnhur/simple-remote-display-with-mobile-app-3862e7/embed' width='350'></iframe>
        - Mobile app 으로 제어하기 ; Arduino Ethernet Library v2.0을 이용한 예제 구현 및 Blogging, WIZnet IoT Tool을 이용하여 Mobile device 에서 간단하게 아두이노 보드를 다룰 수 있다.
            1. [스마트폰으로 간단하게 Arduino 제어하기 (1)](https://ts.devbj.com/568) - Arduino MKR ETH + Arduino MKR Zero platform
            2. [스마트폰으로 간단하게 Arduino 제어하기 (2)](https://ts.devbj.com/570) - WIZnet IoT Tool app
            3. [스마트폰으로 간단하게 Arduino 제어하기 (3)](https://ts.devbj.com/579) - Simple remote display function with WIZnet IoT Tool

## 과거 Reference

- [Arduino Ethernet Library 2.0.0 - PJRC](https://www.pjrc.com/arduino-ethernet-library-2-0-0/) - 사실 Arduino Ethenret library v2.0의 원조 라이브러리, 이 저자가 최근 official version 릴리즈를 담당해주었다.
    - **Benchmarks & Test Results 를 포함하고 있다. 이 페이지는 필독!!!!**    
    - SPI 속도로 인해 W5100 보다 W5200/W5500 이 나은 속도를 보이고 있음을 알 수 있다. (숫자는 Byte/sec)
    - ![Result](/assets/images/img016.png)

- [Adafruit Ethernet2](https://github.com/adafruit/Ethernet2)
    - Adafruit에서 만든 W5500을 지원하기 위해 만들어진 라이브러리
    - **업데이트 중단 선언!** 최근 릴리즈된 Arduino Ethernet library v2.0 를 쓸 것을 권고
    - [Adafruit Ethernet FeatherWing to Ubidots over HTTP](https://help.ubidots.com/connect-your-devices/connect-the-adafruit-ethernet-featherwing-to-ubidots-over-http)
        - 아주 작은 모듈로 제작된 FeatherWing과 대표적인 IoT Cloud 솔루션인 Ubidots 와 연결하는 예제
        - 소스코드와 구현 결과물은 링크페이지에 자세히 나와 있다.
        - ![FeatherWing](https://downloads.intercomcdn.com/i/o/43890083/196c3120392350e8e8fed88d/3201-00.jpg){: width="480"}
    - [Arduino Ethernet + SD Card](https://learn.adafruit.com/arduino-ethernet-sd-card?view=all)
        - 대표적인 웹서버 예제로 Arduino Ethernet shield에 있는 SD 카드의 파일정보를 읽어 제공하는 tutorial이다.
        - 소스코드와 구현방법을 순차적으로 아주 잘 정리해 두어 초보자가 아주 쉽게 따라할 수 있다.
        - ![Webserver screen](https://cdn-learn.adafruit.com/assets/assets/000/052/969/medium800/arduino_compatibles_browseroot.gif?1523569856)
        - [Github source](https://github.com/adafruit/Adafruit_Learning_System_Guides/tree/master/Arduino_Ethernet_SD_Card)

- [WIZ_Ethernet_Library-IDE1.6.x-master.zip](https://github.com/SeeedDocument/W5500_Ethernet_Shield_v1.0/blob/master/res/WIZ_Ethernet_Library-IDE1.6.x-master.zip)
    - W5500 을 지원하기 위해 Seeed Studio 에서 수정한 라이브러리
    - WIZnet 에서 제공하고 있는 [WIZ_Ethernet_Library for IDE1.5.x](https://github.com/Wiznet/WIZ_Ethernet_Library) 소스와 유사하다.
    - Arduino IDE1.6.x 이하 버전에서만 사용해야 하며, compile-time 에 반드시 chipset 을 선택해야 한다. 아래 코드 참조
        - Select device: W5100, W5200 or W5500

        ```cpp
        // In the W5100.h file(\libraries\Ethernet\utility\w5100.h), uncomment the device(shield) you want to use.
        #ifndef	W5100_H_INCLUDED
        #define	W5100_H_INCLUDED

        #include <avr/pgmspace.h>
        #include <SPI.h>

        typedef uint8_t SOCKET;
        //#define W5100_ETHERNET_SHIELD
        //#define W5200_ETHERNET_SHIELD
        #define W5500_ETHERNET_SHIELD
        ```

        - in Main .ino file

        ```cpp
        // By default, "WIZ550io_WITH_MACADDRESS" is commented and if you uncomment it, you can use the MAC address stored in the WIZ550io.
        #if defined(W5500_ETHERNET_SHIELD)
        //#define WIZ550io_WITH_MACADDRESS // Use assigned MAC address of WIZ550io
        #include "w5500.h"
        #endif
        ```

    - [W5500 Ethernet Shield v1.0 Webserver](http://wiki.seeedstudio.com/W5500_Ethernet_Shield_v1.0/)
        - 가장 기본적인 온도와 습도값을 보여주는 웹서버 기능을 잘 구현한 예제로 초보자가 쉽게 따라할 수 있도록 구성되어 있다.
        - 소스코드는 물론 하드웨어 연결구조 및 설명이 자세히 되어 있다.
        - ![Webserver for temperature & humidity](https://github.com/SeeedDocument/W5500_Ethernet_Shield_v1.0/raw/master/img/temp%26humi%20on%20web.png)

- [Seeed Studio Ethernet Shield V2.0 Library](https://github.com/Seeed-Studio/Ethernet_Shield_W5200)
    - [W5200 Shield 제품](https://www.seeedstudio.com/W5200-Ethernet-Shield-p-1577.html) 출시와 함께 만들어서 배포
    - W5200 Shield 제품을 사용하고 있다면 아직도 유용한 라이브러리
    - [Webserver Example](https://seeeddoc.github.io/Ethernet_Shield_V2.4/)
        - 웹서버를 이용한 I/O 제어를 하는 간단하고 명쾌한 예제의 소스코드와 설명이 잘 정리되어 있다.
        - ![Result](https://seeeddoc.github.io/Ethernet_Shield_V2.4/img/Arduino-ethernetshield-toggle-led-webpage-led-state-dialog.png)

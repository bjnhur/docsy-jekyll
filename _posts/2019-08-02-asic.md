---
title: "ASIC materials"
author: "Bongjun Hur"
categories: documentation
tags: documentation asic
article_header:
  type: cover
  image:
    src:
---

# ASIC
(Last modified) 2019-01-16

<!-- toc orderedList:0 -->

- [ASIC](#asic)
- [HDL](#hdl)
	- [Verilog](#verilog)
	- [VHDL](#vhdl)
	- [Etc](#etc)
- [EDA Tool (Synopsys, Cadence)](#eda-tool-synopsys-cadence)
	- [Synopsys Design Compier](#synopsys-design-compier)
	- [Synopsys VCS](#synopsys-vcs)
- [반도체 일반](#반도체-일반)

<!-- tocstop -->

## ASIC
  * [ASIC Design Tutorials](http://www.eda.ncsu.edu/wiki/Tutorial:ASIC_Design_Tutorials) - 위키사이트, 전체흐름을 살펴보자. 설계, FPGA, 검증.
  * [HDL Based Digital Design with Programmable Logic](http://www.dejazzer.com/ee478/lectures.html) - HDL, FPGA 등 기본하드웨어 설계 강의노트
  * [2018-IDEC-연구원-교육 Cell-Based 설계 Flow 교육](https://ts.devbj.com/571) - 동영상강의, 기본 칩 개발에 필요한 필수 기술들의 강의, 필수 시청!!

## HDL
설계에 사용되는 hdl 언어(VHDL, Verilog, SystemVerilog, ...) 관련 자료를 모아두자.

### Verilog
* [http://www.testbench.in/](http://www.testbench.in/) - 테스트 벤치, SystemVerilog ~~갑자기 접속이 안됨 ㅜㅜ~~ 접속재개 ;)
* [Verilog 설계 팁](http://ts.devbj.com/226) - IDEC 2012 한글자료
* [Test bench 테스트벤치 작성 가이드](http://ts.devbj.com/210) - 카운터예제로 정리해둔 영어자료
* [VCD file](http://ts.devbj.com/209) - Value Change Dump 파일, 소스코드에서 VCD 파일을 어떻게 만드는지 호출하는 함수들에 대한 간략한 소개


### VHDL
* [VHDL-Online](http://www.vhdl-online.de/start) - 위키형태의 사이트처럼 되어 있으나 깔끔하게 잘 정리되어 있다. 본좌~~
* [VHDL, Verilog 강의](http://www.physi.uni-heidelberg.de/~angelov/VHDL/) - 독일대학의 강의자료 페이지
  - localcopy : [Designing with VHDL](/files/localcopy/Designing with VHDL.pdf), [Simulation with VHDL](files/localcopy/Simulation with VHDL.pdf)
* [VHDL Tutorial: Learn by Example](http://esd.cs.ucr.edu/labs/tutorial/) - 예제를 중심, 2010 리비전된 내용.
* [Essential VHDL Design Examples](https://www.vahana.com/examples.htm) - 시간나면 하나씩 뜯어보자
  * [All examples (localcopy)](/files/localcopy/examples.zip)
* [8051 Synthesizable VHDL Model](http://www.cs.ucr.edu/~dalton/i8051/)
* [VHDL verification courses](http://www.stefanvhdl.com/vhdl/html/) - verification code 를 아주 작은 예제로 처음부터 끝까지 쉽지만 꼭 따라해야함.

### Etc
* none

## EDA Tool (Synopsys, Cadence)
* [EDA 툴 설치가이드](http://ts.devbj.com/208) - DC, PrimeTime, NCVerilog, Formality 의 설치가이드 한글자료 모음 from IDEC
* [How the gate count of a design is determined?](http://ts.devbj.com/217) - 게이트카운트 구해보기 대략적으로 (간단하게 보통 NAND2 게이트 면적으로 나눠서 알아낸다.)

* [VLSI IP site](http://www.vlsiip.com/index.html) - tutorial, IP, 인터뷰 방법 소개등등 많은 자료가 잘 정리되어 있음. 아래 몇개는 링크가져옴
  * [Design Compiler Tutorial and Sample Commands](http://www.vlsiip.com/dc_shell)
  * [Formality Tutorial and Sample Commands](http://www.vlsiip.com/formality)
  * [Power Analysis](http://www.vlsiip.com/power)
  * [Some Frequently used Unix Commands](http://www.vlsiip.com/unix)

### Synopsys Design Compier
* [Design Compiler 관련글](http://ts.devbj.com/438)
  - [Design Compiler 정리](http://blog.naver.com/PostList.nhn?blogId=beahey&from=postList&categoryNo=85)
  - [Donny님 블로그](http://www.donny.co.kr/)
    * [마이크로프로세서 설계 무작정 따라하기 Part-III (1회)](http://www.donny.co.kr/simplecore/simplecore3-1.pdf)
    * [마이크로프로세서 설계 무작정 따라하기 Part-III (2회)](http://www.donny.co.kr/simplecore/simplecore3-2.pdf)
    * [마이크로프로세서 설계 무작정 따라하기 Part-III (3회)](http://www.donny.co.kr/simplecore/simplecore3-3.pdf)
    * [마이크로프로세서 설계 무작정 따라하기 Part-III (4회)](http://www.donny.co.kr/simplecore/simplecore3-4.pdf)
    * [마이크로프로세서 설계 무작정 따라하기 Part-III (최종회)](http://www.donny.co.kr/simplecore/simplecore3-5.pdf)
* [set_false_path/set_case_analysis](http://ts.devbj.com/219) - 간단한 설명, 타이밍과 관련이 있지만 합성에 중요한 변수가 된다.

### Synopsys VCS
* [Simulating verilog VHDL using Synopsys VCS - 칩 설계 검증 툴](http://ts.devbj.com/415)
* [VCS and coverage by Aviral Mittal](http://www.vlsiip.com/vcs/) - 기초적인 내용. 정리 잘되어 있음
* [Open Masca: Simulating mixed language HDL using VCS](http://salinasv.blogspot.kr/2011/05/simulating-mixed-language-hdl-using-vcs.html) - 간략하게 굿.
* [Simulation with VCS](http://documents.mx/documents/5-simulation-vcs.html) - Synopsys 자체 자료니, 좋은 자료인듯. 원본은 어디서 찾아봐야할 듯.
* [RTL Simulation using Synopsys VCS](http://www.csl.cornell.edu/courses/ece5745/handouts/ece5745-tut1-vcs.pdf) - 2016버전, 너무 간단하지만 그냥 명령어 옵션 구경할 만함.
* Gate-Level Simulation With Synopsys VCS Simulator [Synopsys VCS Support (PDF) chapter in volume 3 of the Quartus II Development Software Handbook](https://www.altera.com/content/dam/altera-www/global/en_US/pdfs/literature/hb/qts/qts_qii5v3.pdf) - 정말 좋은 자료. 방대한 양이 질리겠지만 타이밍,합성관련 정보가 짱
  - [(localcopy)Quartus II Development Software Handbook](/files/localcopy/qts_qii5v3.pdf)
* 연세대 한글자료 - [Mixed Signal Simulation](http://soc.yonsei.ac.kr/class/material/dft_class/06_abist_synopsys.pdf)

## 반도체 일반
* [반도체 패키징 공정](https://ts.devbj.com/564)
    1. Back Grinding 공정 : 전공정에서 가공된 웨이퍼의 후면을 얇게 갈아내는 공정
    2. Sawing(Dicing) 공정 : 웨이퍼를 개별 단위(net die)로 잘라내는 공정
    3. Die Attaching 공정 : 회로기판(substrate)에 칩을 붙여 고정하는 공정
    4. Wire Bonding : Gold Wire로 칩을 전기적으로 연결하는 공정
    5. Molding : EMC 물질로 칩이 실장된 기판을 감싸는 공정
    6. Marking : 레이저로 개별 제품에 제품 정보를 새기는 공정
    7. Solder Ball Mount : 회로기판에 솔더 볼을 붙여 아웃단자를 만드는 공정
    8. PKG Sawing : 모듈/보드/카드에 실장하도록 개별 반도체로 잘라내는 공정
* [ESD Test - HBM, MM, CDM](http://ts.devbj.com/425)
* [MTBF/MTTF/MTTR](http://datasyncxml.tistory.com/118)

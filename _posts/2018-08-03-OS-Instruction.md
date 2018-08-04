---
layout: post
title:  "About OS, 운영체제 강의 정리 1강"
date:   2018-08-03
excerpt: "이화여대 반효경 교수 운영체제 강의"
project: true
tag:
- OS
- 운영체제
- 강의 정리

comments: true
---
# 1강. 운영체제 소개

[강의 링크](https://core.ewha.ac.kr/publicview/C0101020140307151724641842?vmode=f)

# Operating System, 운영체제란?

컴퓨터 하드웨어 바로 위에 설치되어 사용자 및 다른 모든 소프트웨어와 하드웨어를 연결하는 소프트웨어 계층. 좁은 의미로 커널(핵심부분, 메모리에 상주) , 넓은 의미로 각종 주변 시스템 유틸티를 포함하는 개념.

## 운영체제의 목적

컴퓨터 시스템의 자원(CPU)을 효율적으로 형평성있게 관리하고 컴퓨터 시스템을 편리하게  사용할 수 있는 환경을 제공하는 것

## 운영체제의 분류

1. 동시작업 가능 여부에 따라
  - 단일 작업(Single tasking)

    한번에 하나의 작업만 처리한다.

  - 다중 작업(Multi tasking)

    동시에 두개 이상의 작업 처리한다. 지금의 운영체제의 대부분이 해당한다.

2. 사용자의 수에 따라

- 단일 사용자(Single User)
- 다중 사용자(Multi User)

3. 처리방식에 따라

- 일괄 처리(batch processing)

  작업 요청의 일정량을 모아 한꺼번에 처리한다. 작업이 완전 종료될 때까지 기다려야 한다. (과거의 방식)

- 시분할(time sharing)

  여러 작업을 수행할 때 일정한 시간 단위로 분할하여 컴퓨터가 처리. 일괄처리 방식에 비해 짧은 응답시간을 갖음.

  Interactive한 방식

- 실시간(Realtime OS)

  정해진 시간 안에 어떠한 일이 반드시 종료 됨이 보장되어야 하는 실시간 시스템을 위한 OS. (원자로/공장 제어, 반도체 장비, 로보트 제어)

  확장된 개념으로 Hard Realtime System (경성 실시간 시스템), Soft Realtime System(연성 실시간 시스템)이 있다.

## 여러가지 운영체제

- 유닉스

  운영체제를 만들기 위해 C언어를 만들었다.

  C언어 기반의 높은 이식성을 갖음. 최소한의 커널구조. 복잡한 시스템에 맞게 확장이 용이함. 소스코드 공개. 프로그램 개발에 용이.

  System V, FreeBSD, SunOS, Solaris, Linux같은 다양한 서브 버전을 갖고있다.

- DOS (Disk Operating System)

  MS사에서 개발. 단일 사용자용 운영체제. 기억장치가 640KB의 한계를 갖는다.

- MS Windows

  다중 작업용 GUI기반 운영체제. PNP, 네트워크 환경 강화. 불안정성. 풍부한 지원 소프트웨어

- 이외에도 스마트 디바이스를 이용한 운영체제 ; 안드로이드, IOS등이 있다.

## 운영체제의 구조

- CPU 스케쥴링

  자원(CPU)을 어떤 프로그램에, 얼마나 시간을 할당 할지 고민하는 방법.

  CPU, Memory, Disk의 처리속도 차이 때문에 시간소모가 발생하기 때문에 이를 해결하기 위한 방법들.

- 메모리 관리

  한정된 메모리를 관리하는 방법.

  운영체제와 여러 프로그램이 메모리 자원을 사용한다. 프로그램 별로 필요한 메모리의 용량도 다르다.

- 디스크 파일 관리

  디스크도 스케쥴링이 필요하다. 디스크는 디스크 헤드가 이동하며 데이터를 읽는다. 따라서 순서대로 일을 처리할 수도 있지만 헤드에 가까운 위치에 있는 것 부터 먼저 효율적으로 처리할 것인지 결정한다. 엘리베이터 스케쥴링과 비슷하다.

- I/O Device (입/출력 장치)

  I/O Device는 기본적으로 CPU에 비해 매우 느린장치다. 그래서 최대한 CPU를 방해하지 않도록 인터럽트를 이용해서 정보를 처리한다.
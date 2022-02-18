---
title: 방화벽 (Firewall)
category: Computer
---

# 방화벽 (Firewall)

 

 

## 1. 방화벽이란

1. 미리 정의된 보안 규칙에 기반하여, 들어오고 나가는 네크워크 트래픽을 모니터링하고 제어하는 네트워크 보안 시스템이다.

1. 신뢰할 수 있는 내부 네트워크와 신뢰할 수 없는 외부 네트워크 (= 인터넷) 간의 장벽을 구성한다.

1. 서로 다른 네트워크를 지나는 데이터를 허용하거나 거부하거나 검열, 수정하는 하드웨어나 소프트웨어 장치이다.

- 내부 네트워크 = LAN

- 외부 네트워크 = WAN

 

## 2. 방화벽의 역할

신뢰 수준이 다른 네트워크 구간들 사이에 놓여서, 신뢰 수준이 낮은 네트워크로부터 오는 해로운 트래픽이 신뢰 수준이 높은 네트워크로 오지 못하게 막는다.

 

## 3. 정책 기반의 방화벽

방화벽은 다양한 수준의 정책으로 네트워크 간의 트래픽을 제어한다.

1. 일반 수준의 정책 : 외부에서 내부로 전송되는 모든 트래픽을 차단하거나 허용

1. 고급 수준의 정책 : "외부의 경쟁회사로부터 내부 서버로 오는, 길이 500byte 이상의 HTTP 트래픽을 허용하되 로그를 남긴다" 와 같은 복잡한 정책

 

## 4. 방화벽의 역사

초기에는 네트워크 장비 중 하나인 라우터 (= Router) 가 방화벽의 역할을 전담했다.

이후 외부 공격 형태가 다양해지고 치밀해짐에 따라 방화벽 기술도 그에 맞춰 진화했다.

1. 1세대 방화벽 : 패킷 필터

1. 2세대 방화벽 : 상태 기반 방화벽 (= Stateful)

1. 3세대 방화벽 : 애플리케이션 방화벽

<br> 

### 4-1. 패킷 필터

패킷 자체만을 보고 미리 설정된 정책에 따라 허용 또는 거부를 결정하는 초창기 방화벽.

방화벽 내부에서 세션을 관리하지 않는 기본 형태의 방화벽이다.

특정한 IP를 허용 또는 거부하거나 특정한 포트를 허용 또는 거부하는 용도로 사용된다.

<br>  

### 4-2. 상태 기반 방화벽 (= Stateful)

패킷 단위의 검사가 아닌, 세션 단위의 검사를 수행한다.

<br> 

### 4-3. 애플리케이션 방화벽

초창기에는 네트워크를 기반으로 하던 공격 패턴이 점차 발달하여 일상적인 트래픽과 같은 특성을 가지면서 시스템을 공격하는 형태로 발전하게 되었다.

패킷 필터 기반의 방화벽으로는 이러한 공격을 방어하기 어렵기 때문에, 애플리케이션 방화벽은 패킷의 내용을 검사하고 더 나아가 애플리케이션에 어떠한 영향을 미칠지 분석한다.

- ex) IPS, WAF, UTM

 

## 5. 방화벽의 작동 원리

기본적으로 방화벽은 모든 접근을 거부한 후, 허용할 접근만 단계적으로 허용하는 방식을 따른다.

예를 들어, 방화벽은 약 65000개의 통신 포트 모두를 차단한 후 접근을 허용하는 특정 포트만을 열어둔다.

통신 포트 뿐 아니라, 외부로부터 접근하는 IP 주소나 특정 프로그램에 따라 접근/거부 여부를 결정할 수 있다.

이러한 보안 규칙 (= ACL) 설정이 모두 접근 제어 목록에 포함되어 일괄 적용된다.

방화벽의 접근 제어 목록은 대개 관리자가 구성, 설정하기 편하도록 직관적인 형태로 출력되며, 보안 규칙 적용 즉시 결과를 확인할 수 있도록 제공된다.
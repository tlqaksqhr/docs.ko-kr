---
title: "인터넷 프로토콜 버전 6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "IPv6, 향상"
  - "IPv4"
  - "IPv6"
  - "인터넷 프로토콜 버전 6, 개선"
  - "인터넷 프로토콜 버전 6"
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 인터넷 프로토콜 버전 6
인터넷 프로토콜 버전 6 \(IPv6\) 인터넷의 네트워크 계층에 대 한 표준 프로토콜의 새로운 제품군입니다.  IPv6 주소 고갈, 보안, 자동 구성, 확장성 및 등에 관계와 많은 현재 버전의 인터넷 프로토콜 모음 \(IPv4 라고\) 문제를 해결 하기 위해 설계 되었습니다.  IPv6 새로운 종류의 피어\-투\-피어 및 모바일 응용 프로그램을 포함 하 여 응용 프로그램을 사용할 수 있도록 인터넷의 기능을 확장 합니다.  현재 IPv4 프로토콜의 주요 문제는 다음과 같습니다.  
  
-   주소 공간의 빠른 고갈입니다.  
  
     네트워크 주소가 여러 개인 주소를 단일 공용 IP 주소로 매핑하는 변환기 \(Nat\)을 사용 하는 이어졌습니다.  이 메커니즘에 의해 생성의 주요 문제는 오버 헤드 및 엔드\-투\-엔드 연결 부족 처리 됩니다.  
  
-   계층 구조 지원 결여  
  
     해당 미리 정의 된 고유한 클래스 조직이 인해 IPv4 true 계층 지원을 부족합니다.  실제로 네트워크 토폴로지를 매핑하는 방법에는 IP 주소를 구성 하려면 불가능 합니다.  이 중요 한 설계 결함으로 인해 IPv4 패킷을 인터넷의 모든 위치에 제공할 수 있는 큰 라우팅 테이블을 만듭니다.  
  
-   복잡 한 네트워크를 구성 합니다.  
  
     I p v 4와 주소 정적으로 할당 되어야 합니다 또는 DHCP와 같은 구성 프로토콜을 사용 합니다.  이상적인 상황에서는 호스트는 DHCP 하 부 구조의 관리에 의존 되지 않습니다.  대신, 자체에서 찾을 수 있는 네트워크 세그먼트에 따라 구성할 수 있을 것입니다.  
  
-   기본 제공 인증 및 기밀성의 부족 합니다.  
  
     IPv4 지원이 교환된 데이터를 암호화 하거나 인증을 제공 하는 모든 메커니즘을 필요 하지 않습니다.  이 i p v 6으로 변경합니다.  인터넷 프로토콜 보안 \(IPSec\)은 IPv6 지원 요구 사항입니다.  
  
 새 프로토콜 제품군은 다음과 같은 기본 요구 사항을 충족 해야 합니다.  
  
-   대규모 라우팅 및 주소와 낮은 오버 헤드  
  
-   자동 구성에 대 한 다양 한 연결 상황입니다.  
  
-   기본 제공 인증 및 기밀성입니다.  
  
 자세한 내용은 [IPv6 주소 지정](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6 라우팅](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 자동 구성](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [IPv6 사용 및 사용 안 함](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) 및 [방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)를 참조하십시오.  
  
## 참조  
 다음 인터넷 엔지니어링 작업 강제 사이트에서 찾을 수 있는 RFC 문서 선택된 됩니다 \([http:\/\/www.ietf.org](http://www.ietf.org/)\).  
  
-   RFC 1287, 미래 인터넷 아키텍처를 향해입니다.  
  
-   RFC 1454, IP의 다음 버전에 대 한 제안 비교 합니다.  
  
-   RFC 2373, IP 버전 6 주소 지정 아키텍처입니다.  
  
-   RFC 2374는 IPv6 집계 가능한 글로벌 유니캐스트 주소 형식.  
  
 I p v 6와 관련 된 정보를 찾을 수도 있습니다는 [Technet에서 IPv6 영역](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## 참고 항목  
 [IPv6 소켓 샘플](http://go.microsoft.com/fwlink/?LinkID=179568)   
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [소켓](../../../docs/framework/network-programming/sockets.md)
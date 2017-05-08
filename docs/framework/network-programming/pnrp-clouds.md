---
title: "PNRP 클라우드 | Microsoft Docs"
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
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# PNRP 클라우드
PNRP "클라우드" 네트워크를 통해 서로 통신할 수 있는 노드 집합을을 나타냅니다.  "클라우드" 용어 "피어 메시" 및 "피어 투 피어 그래프"와 같습니다.  
  
 노드 간 통신은 한 클라우드 내에서만 수행되어야 합니다.  <xref:System.Net.PeerToPeer.Cloud> 인스턴스는 대\/소문자를 구분하는 이름으로 고유하게 식별됩니다.  단일 피어 또는 노드를 둘 이상의 클라우드에 연결할 수 있습니다.  
  
 클라우드는 네트워크 인터페이스와 밀접하게 관련되어 있습니다.  서로 다른 서브넷에 두 개의 네트워크 카드가 연결되어 있는 다중 홈 컴퓨터의 경우 인터페이스별로 각 링크 로컬 주소에 대해 하나씩 반환되는 두 개의 클라우드와 전역 범위 클라우드 하나를 포함하여 모두 세 개의 클라우드가 반환됩니다.  
  
 PNRP "범위가 서로 쉽게 찾을 수 있는 컴퓨터 그룹인 세 구름 범위"를 사용 합니다.  
  
-   글로벌 클라우드는 글로벌 IPv6 주소 범위 및 글로벌 주소에 해당 하 고 전체 IPv6 인터넷 상의 모든 컴퓨터를 나타냅니다.  단일 글로벌 클라우드가입니다.  
  
-   링크\-로컬 클라우드는 링크 로컬 IPv6 주소 범위 및 링크\-로컬 주소에 해당합니다.  링크\-로컬 클라우드는 특정 링크는 일반적으로 동일한 로컬로 연결 된 서브넷입니다.  링크\-로컬 클라우드를 여러 개 사용할 수 있습니다.  
  
 세 번째 클라우드는 사이트별 클라우드는 사이트 IPv6 주소 범위 및 사이트 로컬 주소에 해당합니다.  PNRP에서는 아직 지원 되지 않지만이 클라우드는 사용 되지 않습니다.  
  
## 구름  
 PNRP 클라우드의의 인스턴스에 의해 표현 되는 <xref:System.Net.PeerToPeer.Cloud> 클래스입니다.  피어 그룹의 구름에 사용 되는 enumerable의 인스턴스가 표시 됩니다 <xref:System.Net.PeerToPeer.CloudCollection> 클래스입니다.  알려진 현재 피어에 PNRP 클라우드의 컬렉션 정적 호출 하 여 얻을 수 있습니다 <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A> 메서드.  
  
 개별 클라우드는 256 문자 유니코드 문자열로 나타낼 고유한 이름을 갖습니다.  이러한 이름은 위에서 언급 한 범위와 함께 클라우드 클래스의 고유 인스턴스를 생성 하는 데 사용 됩니다.  이러한 인스턴스 수 serialize 되 고 재구성에 대 한 영구 사용 합니다.  
  
 클라우드 인스턴스를 만들거나 가져온 후에 알려진 피어 메시를 만들려면 피어 이름은 등록할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Net.PeerToPeer.Cloud>   
 [피어 이름 확인 프로토콜](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)
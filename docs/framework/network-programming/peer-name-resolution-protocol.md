---
title: "피어 이름 확인 프로토콜 | Microsoft Docs"
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
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 피어 이름 확인 프로토콜
피어\-투\-피어 환경에서 피어 특정 이름 확인 시스템 서로의 네트워크 위치 \(주소, 프로토콜 및 포트\)를 해결 하려면 이름 또는 기타 유형의 식별자를 사용 합니다.  과거에는 기본적으로 임시 연결 뿐만 아니라 다른 도메인 이름 시스템 \(DNS\) 내 단점으로 피어 이름 확인 복잡할 되었습니다.  
  
 Microsoft ® Windows ® 피어\-투\-피어 네트워킹 플랫폼 피어 이름 확인 프로토콜 \(PNRP\), 보안, 확장성 및 동적 이름 등록 및 이름 확인 프로토콜에 대 한 Windows XP를 처음 개발 된 및 다음 Windows Vista ™에서 업그레이드이 문제가 해결 되었습니다.  PNRP는 기존의 이름 확인 시스템과 응용 프로그램 개발자를 위한 새로운 가능성을 열어에서 매우 다르게 작동 합니다.  
  
 PNRP에 피어 이름은 시스템 또는 개별 응용 프로그램이 나 서비스는 컴퓨터에 적용할 수 있습니다.  피어 이름 확인 주소, 포트 및 확장된 된 페이로드가 포함 됩니다.  내결함성, 병목 현상 및 부실 주소를 반환 하는 이름 확인이이 시스템의 혜택을 포함 합니다. 프로토콜 모바일 사용자를 찾을 수 있는 뛰어난 솔루션을 만듭니다.  
  
 보안 측면에서 피어 이름은 가능 \(보호 된\) 보안으로 게시 또는 보안 되지 않은 \(보호 되지 않음\).  PNRP 공개 키 암호화를 통해 스푸핑으로부터 피어 이름을 보호 합니다 사용 합니다. 정보와 컴퓨터와 서비스 이름을 지정할 수 있습니다.  
  
-   피어 이름 확인 프로토콜에 다음 속성을 보여 줍니다.  
  
-   분산 되 고 거의 사용 하지.  서버는만 부트스트랩 프로세스가 필요 합니다.  
  
-   제 3의 도움 없이 이름 게시를 보호 합니다.  DNS 이름 게시와는 달리 PNRP 이름 게시 순간 및 금융 비용 없이입니다.  
  
-   PNRP 업데이트를 실시간으로 부실 주소는 없습니다.  
  
-   또한 이름 확인 서비스를 허용 하 여 컴퓨터를 통해 PNRP 이름 확인을 확장 합니다.  
  
## System.Net.PeerToPeer 네임 스페이스  
  
-   PNRP 기능으로 정의 되는 <xref:System.Net.PeerToPeer> .NET Framework 3.5 버전 내에서 네임 스페이스입니다.  사용 가능한 PNRP 서비스 피어 이름 등록 및 확인 하는 데 사용할 수 있는 형식 집합을 제공 합니다.  
  
-   \(PNRP 및 사용자 지정 피어 확인자 만들어지고 인스턴스화된 형식을 사용 하 여 제공 된 <xref:System.ServiceModel.PeerResolvers> 네임 스페이스입니다.\)  
  
-   사용 가능한 PNRP 서비스 이름 등록 및 확인에 사용 되는 기본 형식을 다음과 같습니다.  
  
-   <xref:System.Net.PeerToPeer.Cloud>: 해당 범위를 포함 하 여 사용 가능한 PNRP 클라우드를 설명 하는 정보를 정의 합니다.  
  
-   <xref:System.Net.PeerToPeer.PeerName>: 정의 피어 이름을 등록 하 고 이후에 피어 클라우드 내에서 해결 하는 데 사용할 수 있습니다.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRecord>: 피어 피어에 연결할 수 있는 네트워크 끝점을 포함에 대 한 등록 정보를 포함 하는 PNRP 클라우드에서 레코드를 정의 합니다.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRegistration>: 등록 프로세스를 시작 하 고 중지할 피어 이름을 등록 하는 방법을 비롯 하 여 피어 이름 정의 합니다.  
  
-   <xref:System.Net.PeerToPeer.PeerNameResolver>: 해상도 대 한 동기 및 비동기 메서드를 포함 하 여 해당 네트워크 끝점이, 피어 이름을 확인 하는 프로세스를 정의 합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.PeerResolvers>   
 <xref:System.Net.PeerToPeer>   
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [PeerToPeer 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179571)
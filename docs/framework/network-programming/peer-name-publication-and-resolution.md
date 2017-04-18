---
title: "피어 이름 게시 및 확인 | Microsoft Docs"
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
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# 피어 이름 게시 및 확인
## 피어 이름 게시  
 새 PNRP ID를 게시 하려면 피어 다음을 수행 합니다.  
  
-   인접 캐시 \(캐시의 최하위 수준에 PNRP Id를 등록 한 피어\)에 PNRP 게시 메시지를 보내는 해당 캐시를 시드합니다.  
  
-   클라우드에서 인접해 있지 않은 임의 노드를 선택 하 고 자체 P2P ID에 대 한 PNRP 이름 확인 요청을 보냅니다.  결과 끝점 확인 프로세스는 임의 노드의 캐시를 구름에서 게시 피어의 PNRP ID를 시드합니다.  
  
 PNRP 버전 2 노드에서 다른 P2P Id만 확인 하는 경우 PNRP Id를 게시 하지 않습니다.  NT\\CurrentVersion\\PeerNet\\PNRP\\IPV6\-Global\\SearchOnly \= 1 레지스트리 값 \(REG\_DWORD 형식\) 지정 피어만 PNRP 이름 게시에는 이름 확인에 사용 하는 것입니다.  이 레지스트리 값은 그룹 정책은 통해도 구성할 수 있습니다.  
  
## 피어 이름 확인  
 다른 피어에 PNRP에서 찾는 네트워크 또는 구름의 두 단계로 이루어진 프로세스입니다.  
  
1.  끝점 확인  
  
2.  PNRP ID 확인  
  
 끝점 확인 단계에서 다른 컴퓨터에 있는 서비스의 PNRP ID를 확인 하려는 피어 해당 원격 피어의 IPv6 주소를 결정 합니다.  원격 피어 컴퓨터 또는 서비스의 PNRP ID에 연결 된 또는 게시 하는 것입니다.  
  
 원격 끝점이 PNRP 클라우드 \(cloud\)에 등록 되어 있는지 확인 한 후 요청 하는 피어에 PNRP ID 확인 단계 요청 해당 피어 끝점에 원하는 서비스의 PNRP ID를 보냅니다.  끝점 설명 서비스의 PNRP ID를 확인 하는 회신을 보냅니다 및 최대 4 킬로바이트의 추가 정보를 요청 하는 피어에서 나중 통신용으로 사용할 수 있습니다.  예를 들어 원하는 끝점이 게임 서버인 경우 추가 피어 이름 레코드 데이터 게임, 플레이 레벨, 현재 플레이어 수에 대 한 정보를 포함할 수 있습니다.  
  
 끝점 확인 단계에서 PNRP는 반복적인 프로세스의 확인을 수행 하는 노드에서 연속적으로 대상 PNRP ID에 가까운 노드 연결을 담당 하는 PNRP ID를 게시 노드를 찾는 데 사용  
  
 PNRP에서 이름 확인을 수행 하려면 항목 자체 캐시에 대상 PNRP ID와 일치 하는 항목이 피어 검토  발견 되 면 피어 피어에 PNRP 요청 메시지를 보냅니다 및 응답을 기다리는 경우입니다.  PNRP ID에 대 한 항목이 없으면 피어는 PNRP 요청 메시지를 대상 PNRP ID에 가장 근접 한 PNRP ID를 가진 항목에 해당 하는 피어 보냅니다.  PNRP 요청 메시지를 받은 노드는 자체 캐시를 조사 하 고 다음을 수행:  
  
-   PNRP ID가 있으면 요청 된 끝점 피어가 요청한 피어에 직접 응답 합니다.  
  
-   PNRP ID를 찾을 수 없는 경우 캐시에는 PNRP ID가 대상 PNRP ID에 가깝습니다 요청한 피어에 대상 PNRP ID에 근접 한 PNRP ID를 가진 항목을 나타내는 피어의 IPv6 주소를 포함 하 여 요청 피어 응답을 보냅니다.  요청 노드 응답에서 IP 주소를 사용 하 여 IPv6 주소로 응답 하거나 캐시를 검사 다른 PNRP 요청 메시지를 보냅니다.  
  
-   캐시에 대상 PNRP ID에 가깝게 PNRP ID는 PNRP ID를 찾을 수 없는 경우 요청 받은 피어가 요청한 피어가이 조건을 나타내는 응답을 보냅니다.  그러면 요청한 피어는 다음 다음에 가장 가까운 PNRP ID를 선택  
  
 요청한 피어는이 프로세스를 연속적으로 반복 결국 PNRP ID를 등록 하는 노드를 찾는 계속 됩니다.  
  
 내는 <xref:System.Net.PeerToPeer> 네임 스페이스 간의 다 대 다 관계가 <xref:System.Net.PeerToPeer.PeerName> 망에 통신할 끝점 및 PNRP 클라우드를 포함 한 레코드.  중복 되거나 오래 된 항목 또는 여러 노드가 피어 이름의 경우 PNRP 노드 현재 정보를 사용 하 여 얻을 수 있는 <xref:System.Net.PeerToPeer.PeerNameResolver> 클래스입니다.  <xref:System.Net.PeerToPeer.PeerNameResolver> 메서드 전망 하나 다 피어 피어 이름 레코드와 같은 하나의 피어에 많은 구름 단순화 하기 위해 단일 피어 이름을 사용 합니다.  관계형 테이블 조인을 사용 하 여 실행 쿼리를 유사 합니다.  개체가 성공적으로 완료 되 면 반환 된 <xref:System.Net.PeerToPeer.PeerNameRecordCollection> 에 지정 된 피어 이름을.  예를 들어 피어 이름이 컬렉션에 있는 모든 피어 이름 레코드에 발생 하는 구름으로 정렬.  이 피어 이름을 PNRP 기반 응용 프로그램에서 관련 데이터를 요청할 수 있습니다 수 있습니다.  
  
## 참고 항목  
 <xref:System.Net.PeerToPeer>
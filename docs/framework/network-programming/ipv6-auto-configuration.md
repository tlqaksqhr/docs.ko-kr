---
title: "IPv6 자동 구성 | Microsoft Docs"
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
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# IPv6 자동 구성
I p v 6에 대 한 중요 한 목표 중 하나는 노드 플러그 앤 플레이 지원 하기 위해입니다.  즉, IPv6 네트워크에 노드를 연결 하 고 사용자의 개입 없이 자동으로 구성할 수 있어야 합니다.  
  
## 자동 구성의 종류  
 IPv6 다음 형식의 자동 구성을 지원합니다.  
  
-   **상태 저장 자동 구성은**.  I p v 6의 동적 호스트 구성 프로토콜 하므로 이러한 종류의 구성은 특정 수준의 사용자의 개입 필요 \(DHCPv6\) 서버 설치 및 노드를 관리 합니다.  DHCPv6 서버에 구성 정보를 제공 하는 노드의 목록을 유지 합니다.  서버 시간 각 주소를 사용 중 이며 한 때 재할당에 대해 사용할 수 있습니다 알 수 있도록 또한 상태 정보를 유지 합니다.  
  
-   **상태 비저장 자동 구성**.  이 유형의 구성은 소규모 조직이 나 개인에 적합합니다.  이 경우 각 호스트는 수신된 된 라우터 광고의 내용에서 주소를 결정합니다.  주소의 네트워크 ID 부분을 정의 하는 IEEE eui\-64 표준을 사용 링크 호스트 주소의 고유성 이라고 가정할 수 있습니다.  
  
 주소 결정에 관계 없이 노드에서 해당 잠재 주소가 로컬 링크에 고유한 지 확인 해야 합니다.  네트워크 환경 요청을 보내어 이루어집니다 메시지에 발생할 수 있는 주소입니다.  노드가 응답을 받으면 주소가 이미 사용 되 고 다른 주소를 결정 해야 알 수 있습니다.  
  
## IPv6 이동성  
 모바일 장치의 확산 새 요구 사항을 도입 했습니다: 장치 IPv6 인터넷에서의 위치를 임의로 변경 하 고 기존 연결을 계속 유지할 수 있어야 합니다.  이 기능을 제공 하려면 모바일 노드는 홈 주소에는 항상 도달할 수 있는 할당 됩니다.  집 모바일 노드는 홈 링크에 연결 및 홈 주소를 사용 합니다.  모바일 노드가 홈에서 되 면 라우터는 일반적으로, 홈 에이전트를 모바일 노드와 통신 중인 노드 간에 메시지를 릴레이 합니다.  
  
## 참고 항목  
 [인터넷 프로토콜 버전 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [소켓](../../../docs/framework/network-programming/sockets.md)
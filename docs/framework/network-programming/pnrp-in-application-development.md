---
title: "응용 프로그램 개발의 PNRP | Microsoft Docs"
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
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 응용 프로그램 개발의 PNRP
Windows Vista에서는 네트워킹 응용 프로그램 이름 게시 및 확인 기능에 단순화 된 PNRP API 응용 프로그래밍 인터페이스를 통해 \(\) 액세스할 수 있습니다.  
  
## 피어 이름 확인 프로토콜을 구현합니다.  
 단순화 된 PNRP API와 클라우드 명시적으로 이름과 주소를 등록 하려면 지정 되지 않은. PNRP 구성 요소는 자동으로 적절 한 클라우드 조인 및 클라우드 내에 게시할 주소를 결정 합니다.  
  
 아주 단순화 된 PNRP 이름 확인에 대 한 Windows vista에서에서 PNRP 이름 이제 getaddrinfo \(\) Windows 소켓 함수에 통합 되었습니다.  PNRP를 사용 하 여 이름을 IPv6 주소로 확인 하려면 응용 프로그램 getaddrinfo \(\) 함수 정규화 된 도메인 이름 \(FQDN\) name.prnp를 확인할 수 있습니다.  net의 이름과 피어 이름을 확인 하 고 있습니다.  Pnrp입니다.  net 도메인은 Windows Vista에서 PNRP 이름 확인을 위해 예약 된 도메인이입니다.  
  
 PeerChannel 및 WCF와 같은 내부 아키텍처에서 PeerToPeer 응용 프로그램 간에 전달 되는 메시지 처리 됩니다 여전히 [큰 데이터 및 스트리밍](http://go.microsoft.com/fwlink/?LinkID=179652).  
  
## 참고 항목  
 <xref:System.Net.PeerToPeer>
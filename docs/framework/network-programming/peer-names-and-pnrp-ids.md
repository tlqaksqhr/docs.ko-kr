---
title: "피어 이름 및 PNRP ID | Microsoft Docs"
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
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# 피어 이름 및 PNRP ID
피어 이름 통신, 컴퓨터, 사용자, 그룹, 서비스 등 IPv6 주소로 확인 될 수 있는 피어와 연결 될 수 있는 끝점을 나타냅니다.  피어 이름 확인 프로토콜 \(PNRP\) 클라우드 멤버를 식별 하는 데 사용 되는 PNRP id를 생성 하기 위한 통계적으로 고유한 피어 이름을 사용 합니다.  
  
## 피어 이름  
 피어 이름으로 등록할 수 있습니다 보안 되거나 보안.  사용자는 중복 된 이름을 등록할 수 보안 되지 않은 이름은 위장 될 수 있는 텍스트 문자열입니다.  보안 되지 않은 이름은 개인 또는 보호 된 네트워크에 가장 적합 합니다.  보안 된 이름은 인증서와 디지털 서명으로 보호 됩니다.  원래 게시자만 이름에 대 한 소유권을 증명할 수 있습니다.  
  
 PNRP 활동에 참여 하는 피어 범위와 클라우드 조합이 비교적 안전한 환경을 제공 합니다.  그러나 보안 된 피어 이름을 사용 하 여 네트워킹 응용 프로그램의 전반적인 보안을 보장 하지 않습니다.  응용 프로그램의 보안은 실제 구현에 따라 다릅니다.  
  
 보안 된 피어만 해당 소유자가 등록 된 이름과 공개 키 암호화로 보호 되는.  보안 된 피어 이름은 해당 개인 키가 피어 엔터티에 의해 소유로 간주 됩니다.  소유권 서명 개인 키를 사용 하는 인증 된 피어 주소를 통해 \(CPA\) 입증 될 수 있습니다.  악의 있는 사용자가 해당 개인 키 없이 피어 이름의 소유권을 위조할 수 없습니다.  
  
## PNRP Id  
 ![PNRP ID](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.png "fdc9e8a0\-4a1c\-488d\-a019\-bc3a1973220c")  
  
 PNRP Id는 다음으로 구성 되어 있습니다.  
  
-   순위가 높은 128 비트, 피어\-투\-피어 \(P2P\) ID 라고 하며 끝점에 할당 된 피어 이름의 해시가입니다.  피어 이름이 다음과 같은 형식:  *Authority.Classifier*.  보안 된 이름에 대 한  *기관* 보안 해시 알고리즘 1 \(SHA1\) 16 진수 문자에서 피어 이름 공개 키의 해시입니다.  보안 되지 않은 이름에는  *기관* 는 단일 문자 "0"입니다.  *분류자* 응용 프로그램을 식별 하는 문자열입니다.  없음 피어 이름 분류자를 포함 하 여 149 자를 초과할 수 있는 `null` 종결자.  
  
-   하위 128 비트 동일한 클라우드에서 동일한 P2P ID의 여러 인스턴스를 식별 하도록 생성 된 수 있는 서비스 위치에 사용 됩니다.  
  
 이 P2P ID와 서비스 위치가이 조합 등록 한 컴퓨터에서 여러 PNRP Id를 수 있습니다.  
  
## 참고 항목  
 <xref:System.Net.PeerToPeer.PeerName>   
 <xref:System.Net.PeerToPeer>
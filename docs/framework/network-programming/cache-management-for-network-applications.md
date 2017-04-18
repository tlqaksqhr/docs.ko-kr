---
title: "네트워크 응용 프로그램에 대한 캐시 관리 | Microsoft Docs"
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
  - "캐시[.NET Framework], 네트워크 응용 프로그램"
  - "네트워크 리소스, 캐싱"
  - "인터넷, 캐싱"
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# 네트워크 응용 프로그램에 대한 캐시 관리
이 주제와 관련된 하위 주제가 캐싱을 사용 하 여 가져온 리소스에 대 한 설명의 <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, 및 <xref:System.Net.FtpWebRequest> 클래스입니다.  
  
 캐시는 응용 프로그램에서 요청한 리소스의 임시 저장소를 제공합니다.  응용 프로그램 같은 리소스를 두 번 이상 요청 하면이 서버에서 re\-requesting 오버 헤드를 방지 하는 캐시에서 리소스를 반환할 수 있습니다.  캐싱은 요청한 리소스를 가져오는 데 필요한 시간이 줄어들어 응용 프로그램 성능이 향상 됩니다.  캐싱 또한 네트워크 트래픽을 서버 방문 횟수를 줄임으로써 줄일 수 있습니다.  캐싱 성능이 향상 되는 동안 리소스를 반환 하는 위험 증가 프로그램인 부실 리소스 캐싱 사용 했던 경우에 서버에서 전송 된 동일한 없음을 의미 합니다.  
  
 캐싱 권한이 없는 사용자 또는 프로세스가 중요 한 데이터를 읽을 수 있습니다.  캐시 된 인증된 응답은 추가 권한 부여 없이 캐시에서 가져올 수 있습니다.  캐싱이 설정 되 면 변경 <xref:System.Net.WebRequest.CachePolicy%2A> 에 <xref:System.Net.Cache.RequestCacheLevel> 또는 <xref:System.Net.Cache.RequestCacheLevel> 이 요청에 대 한 캐싱을 사용 하지 않도록 설정 합니다.  
  
 보안 문제로 인해 캐시 된  **하지** 중간 계층 시나리오에서는 권장 합니다.  
  
## 단원 내용  
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)  
 설명 하는 캐시 정책을 정의 하는 방법 이며.  
  
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 위치 기반 캐시 정책 하이퍼텍스트 전송 프로토콜 \(http 및 https\) 리소스를 사용할 수 있는 각 유형을 정의합니다.  
  
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 시간 기반 캐시 정책을 사용자 지정 하는 데 사용할 수 있는 조건을 설명 합니다.  
  
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 캐싱을 사용 하는 요청 및 캐시 정책을 프로그래밍 방식으로 만드는 방법에 설명 합니다.  
  
## 참조  
 <xref:System.Net.Cache>  
 정의 형식 및 열거형을 사용 하 여 가져온 리소스에 대 한 캐시 정책을 정의 하는 데는 <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, 및 <xref:System.Net.FtpWebRequest> 클래스입니다.
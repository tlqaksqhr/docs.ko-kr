---
title: "캐시 정책 조작 -최대 사용 기간 및 최대 부실 | Microsoft Docs"
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
  - "최대 부실"
  - "캐시된 리소스의 새로 고침"
  - "시간, 캐시된 리소스"
  - "최대 보존 기간 정책"
  - "캐시된 리소스의 부실"
  - "캐시된 리소스의 보존 기간"
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 캐시 정책 조작 -최대 사용 기간 및 최대 부실
클라이언트 응용 프로그램에 최신 콘텐츠가 반환 됩니다 보장 하기 가장 보수적인 캐시 정책에 항상 상호 작용의 클라이언트 캐시 정책 및 서버 유효성 재검사가 요구 됩니다.  이 항목의 모든 예제는 1 월 1 일에 캐시 되 고 4 월에 만료 되는 리소스에 대 한 캐시 정책을 보여 줍니다.  
  
 다음 예제는 만료 후 최대 시간 값 \(`maxStale`\)의 최대 사용 기간을 함께 사용 \(`maxAge`\).  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 5 일 및 지정 하지 않는 한 `maxStale` , 값에 따라는 `maxAge` 콘텐츠입니다 사용할 수 있는 6 월까지.  그러나 서버의 유효성 재검사가 요구 사항에 따라 콘텐츠는 4 월에 만료 됩니다.  콘텐츠 만료 날짜 \(빨리\) 보다 보수적 이므로 우선 `maxAge` 정책.  따라서 내용 4 월에 만료 되 고 최대 사용 기간에 도달 하지 않더라도 다시 확인 되어야 합니다.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 5 일 및 `maxStale` \= 3 일 따라는 `maxAge` 값을 콘텐츠는 사용할 수 6 월까지.  따라는 `maxStale` 값을 콘텐츠는 사용할 수 7 월까지.  따라서 콘텐츠는 1 월에서 6 됨 가져옵니다.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 5 일 및 `maxStale` \= 1 일에 따라는 `maxAge` 값을 콘텐츠는 사용할 수 6 월까지.  따라 하는 `maxStale` 콘텐츠입니다 사용 가능한 5 월까지.  따라서 콘텐츠는 1 월 5 일 됨 가져옵니다.  
  
 최대 시대 콘텐츠 만료 날짜 보다 더 보수적인 캐싱 동작이 항상 우선 하 고 만료 후 최대 시간 값을 주지 않습니다.  만료 후 최대 시간을 설정 하면 다음 예제는 설명 \(`maxStale`\) 값 때 최대 사용 기간 \(`maxAge`\) 콘텐츠 만료 시간에 도달할 때:  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 1 일 및 값을 지정 하지 않은 `maxStale` 유효성 검사 값을 콘텐츠입니다 하므로 2 월에 만료 되지 않은 경우에.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 1 일 및 `maxStale` \= 3 일 콘텐츠는 1 월 보다 보수적인 정책 설정을 적용 하려면 2에서 유효성 검사 하므로.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 1 일 및 `maxStale` \= 1 일 콘텐츠를 2 월에 유효성 검사 하므로.  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [캐시 정책 상호 작용 \- 최대 보존 기간 및 최소 새로 고침](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
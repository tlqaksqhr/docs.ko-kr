---
title: "캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침 | Microsoft Docs"
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
  - "시간 기반 캐시 정책"
  - "유효성 다시 검사 정책"
  - "캐시[.NET Framework], 시간 기반 정책"
  - "캐시된 리소스의 새로 고침"
  - "최대 보존 기간 정책"
  - "최소 새로 고침 정책"
  - "캐시된 리소스의 보존 기간"
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침
클라이언트 응용 프로그램에 최신 콘텐츠가 반환 됩니다 보장 하기 가장 보수적인 캐시 정책에 항상 상호 작용의 클라이언트 캐시 정책 및 서버 유효성 재검사가 요구 됩니다.  이 항목의 모든 예제는 1 월 1 일에 캐시 되 고 4 월에 만료 되는 리소스에 대 한 캐시 정책을 보여 줍니다.  
  
 다음 예제는 결과의 최대 사용 기간 상호 작용에서 캐시 정책 설명 \(`maxAge`\) 및 만료 전 최소 시간 \(`minFresh`\) 값.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 2 일 및 `minFresh` 지정 하지 않으면 유효성 검사 내용입니다 하므로 1 월 3 일.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 2 일 및 `minFresh` \= 1 일에 따라 `maxAge`, 3 월까지 새로운 콘텐츠입니다.  에 따라 `minFresh`, 3 월까지 새로운 콘텐츠입니다.  다시 따라서 콘텐츠는 1 월 3 일 확인 되어야 합니다.  
  
-   캐시 정책을 설정 하는 경우 `maxAge` \= 2 일 및 `minFresh` \= 2 일에 따라 `maxAge`, 3 월까지 새로운 콘텐츠입니다.  에 따라 `minFresh` 2 월까지 새로운 콘텐츠입니다.  다시 따라서 내용 2 월에 확인 되어야 합니다.  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [캐시 정책 조작 \-최대 사용 기간 및 최대 부실](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
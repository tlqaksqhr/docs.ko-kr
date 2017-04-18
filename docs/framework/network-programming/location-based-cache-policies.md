---
title: "위치 기반 캐시 정책 | Microsoft Docs"
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
  - "사용 가능한 경우 캐시 정책"
  - "다시 로드 정책"
  - "위치 기반 캐시 정책"
  - "캐시 전용 정책"
  - "로컬 캐시"
  - "중간 캐시"
  - "캐시 없이 저장 안 함 정책"
  - "캐시[.NET Framework], 위치 기반 정책"
  - "유효성 다시 검사 정책"
  - "캐시된 리소스의 새로 고침"
  - "캐시 또는 다음 캐시 전용 정책"
  - "새로 고침 정책 "
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 위치 기반 캐시 정책
위치 기반 캐시 정책 최신성 위치 요청 된 리소스를 가져올 수 있습니다 따라 유효한 캐시 된 항목을 정의 합니다.  캐시 된 리소스가 잘못 된 사용 하지 않는 경우 서버에 지정 된 유효성 재검사가 요구 사항을 위반 하지.  위치 기반 캐시 정책을 프로그래밍 방식으로 사용 하 여 만든 것은 <xref:System.Net.Cache.RequestCachePolicy> 또는 <xref:System.Net.Cache.HttpRequestCachePolicy> 클래스 생성자입니다.  위치 기반 정책 유형을 사용 하는 생성자에 전달 되는 <xref:System.Net.Cache.RequestCacheLevel> 또는 <xref:System.Net.Cache.HttpRequestCacheLevel> 열거형 값입니다.  위치 기반 캐시 정책을 만드는 코드 예제를 보려면  [방법: 응용 프로그램에 대해 위치 기반 캐시 정책 설정](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md).  다음 섹션에서는 각 유형의 하이퍼텍스트 전송 프로토콜 \(http 및 https\) 리소스에 대 한 위치 기반 캐시 정책에 설명합니다.  
  
## 사용할 수 있는 경우에 캐시 정책  
 유효한 요청 된 리소스가 로컬 캐시에 있으면 캐시 된 리소스가 사용 됩니다. 그렇지 않으면 리소스 요청이 서버로 전송 됩니다.  클라이언트와 서버 사이의 캐시에서 요청한 리소스를 사용할 수 있으면 중간 캐시에 의해 요청을 처리할 수 있습니다.  
  
## 캐시 전용 정책  
 유효한 요청 된 리소스가 로컬 캐시에 있으면 캐시 된 리소스가 사용 됩니다.  이 캐시 정책 수준을 지정 하지 않으면는 <xref:System.Net.WebException> 항목의 로컬 캐시에 없으면 예외가 throw 됩니다.  
  
## 캐시 또는 다음 캐시 전용 정책  
 유효한 요청 된 리소스가 로컬 캐시 또는 로컬 영역 네트워크에 있는 중간 캐시에 경우 캐시 된 리소스가 사용 됩니다.  <xref:System.Net.WebException> 예외가 throw됩니다.  HTTP 캐싱 프로토콜에서이 하면\-캐시 캐시 제어 지시문을 사용 하 여 이루어집니다.  
  
## 없음 캐시 없음 저장 정책  
 요청한 리소스는 캐시에서 사용 되지 않는 및 모든 캐시에 저장 되지 않습니다.  요청 된 리소스를 로컬 캐시에 있으면 제거 됩니다.  이 정책 수준 들도 자원 제거 해야 중간 캐시를 나타냅니다.  HTTP 캐싱 프로토콜에서 아니요 저장소 캐시 제어 지시문을 사용 하 여 수행 됩니다.  
  
## 정책 새로 고침  
 서버에서 가져온 또는 로컬 캐시 이외의 캐시에 있는 경우 요청 된 리소스를 사용할 수 있습니다.  중간 캐시에서 요청을 만족시키려면 먼저 캐시에서 서버를 기준으로 캐시된 엔트리의 유효성을 다시 검사해야 합니다.  HTTP 캐싱 프로토콜에서이 최대 사용 기간을 사용 하 여 수행할 수 \= 0 캐시 제어 지시문과 no\-cache Pragma 헤더입니다.  
  
## 정책 다시 로드  
 요청한 리소스는 서버에서 가져와야 합니다.  응답은 로컬 캐시에 저장 되어 있습니다.  HTTP 캐싱 프로토콜에서 no\-cache 캐시 제어 지시문과 no\-cache Pragma 헤더를 사용 하 여 수행 됩니다.  
  
## 정책 유효성을 다시 검사  
 캐시에 있는 리소스 복사본을 서버에 있는 복사본과 비교합니다.  서버에 있는 복사본이 더 최신이면 이 복사본을 사용하여 요청을 만족시키고 캐시의 복사본을 바꿉니다.  캐시에 있는 복사본이 서버의 복사본과 동일하면 캐시된 복사본이 사용됩니다.  HTTP 캐싱 프로토콜에서 이 작업은 조건부 요청을 사용하여 수행됩니다.  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
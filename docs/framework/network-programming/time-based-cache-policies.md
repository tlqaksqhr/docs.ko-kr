---
title: "시간 기반 캐시 정책 | Microsoft Docs"
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
  - "캐시 동기화 날짜 정책"
  - "캐시[.NET Framework], 시간 기반 정책"
  - "캐시된 리소스의 새로 고침"
  - "시간, 캐시된 리소스"
  - "최대 보존 기간 정책"
  - "동기화, 캐시"
  - "캐시된 리소스의 부실"
  - "기본 시간 기반 캐시 정책"
  - "최대 부실 정책"
  - "콘텐츠 캐시 정책"
  - "만료된 콘텐츠"
  - "최소 새로 고침 정책"
  - "캐시된 리소스의 보존 기간"
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 시간 기반 캐시 정책
시간 기반 캐시 정책은 리소스 검색 된 리소스를 사용 하 여 헤더가 반환 시간 및 현재 시간을 사용 하 여 캐시 엔트리를 정의 합니다.  시간 기반 캐시 정책을 설정할 때 사용 할 수 있습니다는 <xref:System.Net.Cache.HttpRequestCacheLevel> 시간 기반 정책 또는 사용자 지정 된 시간 기반 정책을 만듭니다.  HTTP \(하이퍼텍스트 전송 프로토콜\)를 사용 하 여 가져온 리소스에 대 한 기본 시간 기반 정책을 사용 하는 경우 정확한 캐시 동작은 캐시 된 응답 하 여 13 및 14에 RFC 2616의 섹션에 지정 된 동작을 포함 하는 헤더에 의해 결정 됩니다 [http:\/\/www.ietf.org](http://www.ietf.org/).  HTTP 리소스에 대 한 기본 시간 기반 정책을 설정 하는 방법을 보여 주는 코드 예제를 보려면  [방법: 응용 프로그램에 대 한 Default Time\-Based 캐시 정책 설정](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).  만들고 캐시 정책을 사용 하 여 보여 주는 코드 예제를 보려면  [구성 캐싱을 네트워크 응용 프로그램에서](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## 캐시 된 항목의 유효성을 확인 하는 조건  
 시간 기반 캐시 정책을 사용자 지정 하려면 다음 조건 중 하나 이상의 캐시 된 항목의 유효성을 확인 하려면 사용을 지정할 수 있습니다.  
  
-   최대 사용 기간  
  
-   만료 후 최대 시간  
  
-   만료 전 최소 시간  
  
-   캐시 동기화 날짜  
  
> [!NOTE]
>  기본 시간 기반 캐시 정책을 사용 하 여 응용 프로그램에 대 한 기본 캐시 정책을 설정 하는 함께 혼동 해서는 안됩니다.  시간 기반 정책은 요청이 나 응용 프로그램 수준에서 사용할 수 있는 특정 정책이입니다.  응용 프로그램에 대 한 기본 캐시 정책을 요청에 설정 된 정책이 있는 경우에 적용 정책 \(위치 기반 또는 시간 기반\)입니다.  응용 프로그램에 대 한 기본 캐시 정책을 설정 하는 자세한 내용은 <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### 최대 사용 기간  
 최대 사용 기간 정책 조건은 캐시 된 리소스 복사본을 사용할 수 있는 기간을 지정 합니다.  다시 캐시 된 리소스 복사본이 지정 된 시간 보다 오래 된 경우 리소스는 서버에서 내용에 대해 확인 하 여 확인 되어야 합니다.  최대 사용 기간 만료 후 사용할 리소스를 허용 하는 경우 만료 후 최대 시간 값도 지정 되지 않은 경우이 조건입니다 적용 없습니다.  
  
### 만료 후 최대 시간  
 만료 후 최대 시간 정책 조건은 캐시 된 리소스 복사본을 사용할 수 있는 콘텐츠 만료 후 시간을 지정 합니다.  리소스가 만료 된 후에 사용할 수 있도록 유일한 캐시 정책 조건입니다.  
  
### 만료 전 최소 시간  
 만료 전 최소 시간 정책 조건은 캐시 된 리소스 복사본을 사용할 수 있는 콘텐츠 만료 전에 시간을 지정 합니다.  이 정책이 캐시 엔트리를 만료 만료 날짜 이전에 발생 하는 것과 같습니다. 따라서 최소 시간과 최대 확인 설정을 상호 배타적입니다.  
  
## 캐시 동기화 날짜  
 캐시 동기화 날짜 정책 조건은 다시 경우 리소스의 캐시 된 복사본을 서버에서 내용에 대해 확인 하 여 확인 되어야 합니다 결정 합니다.  항목이 캐시 된 이후에 콘텐츠가 변경 되 면 서버에서 검색, 캐시에 저장 되 고 응용 프로그램에 반환 합니다.  내용을 변경 하지 않은 경우 해당 타임 스탬프를 업데이트 하 고 캐시 된 콘텐츠는 응용 프로그램을 가져옵니다.  
  
 캐시 동기화 날짜를 사용하여 캐시된 콘텐츠의 유효성을 다시 검사해야 할 절대 날짜를 지정할 수 있습니다.  새 캐시 항목이 캐시 동기화 날짜 이전의 마지막 검사 하는 경우 서버 유효성 재검사가 여전히 발생 합니다.  캐시에서 항목이 캐시 동기화 날짜 이후에 캐시 엔트리의 유효성을 다시 검사 하 고 유효성을 추가 또는 캐시 된 항목을 무효화 하는 서버의 유효성 재검사 요구 하는 경우에 사용 됩니다.  캐시 동기화 날짜를 이후 날짜로 설정하면 캐시 동기화 날짜가 지날 때까지는 요청이 있을 때마다 엔트리의 유효성이 다시 검사됩니다.  
  
 시간 기반 캐시 정책 조건 결합 효과 대 한 정보는 다음 항목을 제공 합니다.  
  
-   [캐시 정책 조작 \-최대 사용 기간 및 최대 부실](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [캐시 정책 상호 작용 \- 최대 보존 기간 및 최소 새로 고침](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
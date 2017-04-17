---
title: "캐시 정책 | Microsoft Docs"
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
  - "위치 기반 캐시 정책"
  - "캐시[.NET Framework], 정책"
  - "요청 캐시 정책"
  - "캐시된 리소스의 새로 고침"
  - "콘텐츠 캐시 정책"
  - "만료된 콘텐츠"
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 캐시 정책
캐시 정책은 요청을 요청된 리소스의 캐시된 복사본으로 충족시킬 수 있는지 여부를 확인하는 데 사용되는 규칙을 정의합니다.  응용 프로그램 유효성에 대 한 클라이언트 캐시 요구 사항을 지정 하지만 유효한 캐시 정책은 클라이언트 캐시 요구 사항, 서버의 콘텐츠 만료 요구 사항 및 서버의 유효성 재검사 요구에서 결정 됩니다.  클라이언트 캐시 정책 및 서버 요구 사항의 상호 작용 항상 최신 콘텐츠가 클라이언트 응용 프로그램에 반환 됩니다 있도록 가장 보수적인 캐시 정책이 됩니다.  
  
 캐시 정책은 위치 기반 또는 시간 기반입니다.  위치 기반 캐시 정책 최신성 위치 요청 된 리소스에서 수행할 수 있습니다 기반으로 캐시 된 항목을 정의 합니다.  시간 기반 캐시 정책 헤더의 리소스와 현재 시간을 반환 사용 하 여 리소스를 검색할 때마다 캐시 된 항목을 정의 합니다.  대부분의 응용 프로그램 기본 시간 기반 캐시 정책, RFC 2616에 지정 된 캐싱 정책을 구현 수 [http:\/\/www.ietf.org](http://www.ietf.org/).  
  
 다음 표에 설명 된 클래스는 캐시 정책을 지정 하는 데 사용 됩니다.  
  
|클래스 이름|설명|  
|------------|--------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|위치 및 시간 기반 캐시 정책을 사용 하 여 요청 된 리소스를 나타내는 <xref:System.Net.HttpWebRequest> 개체입니다.|  
|<xref:System.Net.Cache.RequestCachePolicy>|위치 기반 캐시 정책을 나타냅니다 또는 <xref:System.Net.Cache.RequestCacheLevel> 시간 기반 캐시 정책을 사용 하 여 요청 된 리소스에 대 한 <xref:System.Net.WebRequest> 개체입니다.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|시간 기반을 만드는 데 사용 되는 값을 지정 합니다. <xref:System.Net.Cache.HttpRequestCachePolicy> 개체입니다.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|위치 및 시간 기반을 만드는 데 사용 되는 값을 지정 합니다. <xref:System.Net.Cache.HttpRequestCachePolicy> 개체입니다.|  
|<xref:System.Net.Cache.RequestCacheLevel>|위치 기반을 만드는 데 사용 되는 값을 지정 또는 <xref:System.Net.Cache.RequestCacheLevel> 시간 기반 <xref:System.Net.Cache.RequestCachePolicy> 개체입니다.|  
  
 모든 응용 프로그램에 요청 하거나 개별 요청에 대 한 캐시 정책을 정의할 수 있습니다.  응용 프로그램 수준의 캐시 정책과 요청 수준의 캐시 정책을 모두 지정 하는 경우 요청 수준의 정책이 사용 됩니다.  프로그래밍 방식으로 또는 응용 프로그램 또는 컴퓨터 구성 파일을 사용 하는 응용 프로그램 수준의 캐시 정책을 지정할 수 있습니다.  자세한 내용은 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)을 참조하십시오.  
  
 캐시 정책을 만들려면 인스턴스를 만들어 정책 개체를 만들어야 합니다의 <xref:System.Net.Cache.RequestCachePolicy> 또는 <xref:System.Net.Cache.HttpRequestCachePolicy> 클래스입니다.  요청 시 정책을 지정 하는 요청 설정 <xref:System.Net.WebRequest.CachePolicy%2A> 정책 개체의 속성입니다.  프로그래밍 방식으로 응용 프로그램 수준 정책을 설정 하면 설정 된 <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> 정책 개체의 속성.  
  
 만들고 캐시 정책을 사용 하 여 보여 주는 코드 예제를 보려면  [구성 캐싱을 네트워크 응용 프로그램에서](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
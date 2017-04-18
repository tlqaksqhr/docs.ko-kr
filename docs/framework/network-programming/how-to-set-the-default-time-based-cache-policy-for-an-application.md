---
title: "방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정 | Microsoft Docs"
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
  - "캐시[.NET Framework], 시간 기반 정책"
  - "기본 시간 기반 캐시 정책"
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정
기본 시간 기반 캐시 정책 13 및 14에 RFC 2616의 섹션에 정의 된 캐시 동작 및 캐시 된 리소스와 보낸 헤더에서 정의 된 캐시 동작 하는 응용 프로그램 수 [http:\/\/www.ietf.org](http://www.ietf.org/).  이 대부분의 응용 프로그램에 대 한 적절 한 캐시 동작입니다.  
  
### 응용 프로그램에 대 한 기본 자동 정책을 설정 하려면  
  
1.  기본 시간 기반 정책 개체를 만듭니다.  
  
2.  정책 개체가 응용 프로그램 도메인의 기본값으로 설정 합니다.  
  
## 예제  
 이 단원의 두 예제는 동일한 정책을 만듭니다.  
  
 다음 예제에서는 기본 시간 기반 정책을 만들어 응용 프로그램 도메인의 기본값으로 설정 합니다.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 기본 시간 기반 캐시 정책을 사용 하 여 만들 수 있습니다는 <xref:System.Net.Cache.RequestCachePolicy> 클래스는 다음 예제와 같이:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
  
```  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
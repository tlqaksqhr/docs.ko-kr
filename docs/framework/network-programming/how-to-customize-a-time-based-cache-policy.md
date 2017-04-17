---
title: "방법: 시간 기반 캐시 정책을 사용자 지정 | Microsoft Docs"
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
  - "시간 기반 캐시 정책 사용자 지정"
  - "캐시[.NET Framework], 시간 기반 정책 "
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 방법: 시간 기반 캐시 정책을 사용자 지정
시간 기반 캐시 정책을 만들 때 최대 사용 기간 만료 전 최소 시간, 만료 후 최대 시간 또는 캐시 동기화 날짜에 대 한 값을 지정 하 여 캐싱 동작을 사용자 지정할 수 있습니다.  <xref:System.Net.Cache.HttpRequestCachePolicy> 개체 이러한 값의 유효한 조합을 지정할 수 있는 여러 생성자를 제공 합니다.  
  
### 캐시 동기화 날짜를 사용 하는 시간 기반 캐시 정책을 만들려면  
  
-   캐시 동기화 날짜를 전달 하 여 사용 하는 시간 기반 캐시 정책을 만들는 <xref:System.DateTime> 개체의 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자입니다.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 결과 다음과 같습니다.  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### 만료 전 최소 시간을 기반으로 하는 시간 기반 캐시 정책을 만들려면  
  
-   지정 하 여 만료 전 최소 시간을 기반으로 하는 시간 기반 캐시 정책을 만드는 <xref:System.Net.Cache.HttpCacheAgeControl> 으로 `cacheAgeControl` 통과 하는 매개 변수 값은 <xref:System.TimeSpan> 개체의 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 다음 호출을:  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
  
```  
  
### 최소 시간과 최대 보관 기간을 기준으로 하는 시간 기반 캐시 정책을 만들려면  
  
-   최소 시간과 최대 보관 기간을 지정 하 여 기반으로 하는 시간 기반 캐시 정책을 만드는 <xref:System.Net.Cache.HttpCacheAgeControl> 으로 `cacheAgeControl` 매개 변수 값 및 두 전달 <xref:System.TimeSpan> 개체에 <xref:System.Net.Cache.HttpRequestCachePolicy> 초 만료 전 최소 시간을 지정 하 고 리소스에 대 한 최대 보존 기간을 지정 하려면 생성자를 허용 하는 캐시에서 반환 되는 개체에 대 한.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 다음 호출을:  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
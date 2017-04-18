---
title: "방법: 응용 프로그램에 대해 위치 기반 캐시 정책 설정 | Microsoft Docs"
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
  - "명시적 캐시 동작 정의"
  - "위치 기반 캐시 정책"
  - "로컬 캐시"
  - "요청 캐시 정책"
  - "캐시[.NET Framework], 위치 기반 정책"
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 방법: 응용 프로그램에 대해 위치 기반 캐시 정책 설정
위치 기반 캐시 정책은 요청한 리소스의 위치를 기준으로 캐싱 동작을 명시적으로 정의 하는 응용 프로그램을 수 있습니다.  이 항목에서는 캐시 정책을 프로그래밍 방식으로 설정 하는 방법을 보여 줍니다.  정책 구성 파일을 사용 하 여 응용 프로그램 설정에 대 한 내용은 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### 응용 프로그램에 대 한 위치 기반 캐시 정책을 설정 하려면  
  
1.  Create a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> object.  
  
2.  정책 개체가 응용 프로그램 도메인의 기본값으로 설정 합니다.  
  
### 캐시에서 요청 된 리소스를 사용 하는 정책을 설정 하려면  
  
-   가능한 경우 캐시에서 요청한 리소스를 사용 하 고 그렇지 않은 경우 캐시 레벨을 설정 하 여 서버에 요청 전송 하는 정책을 만드는 <xref:System.Net.Cache.HttpRequestCacheLevel>.  모든 캐시 클라이언트와 서버, 원격 캐시를 포함 하 여 요청을 완료할 수 있습니다.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 캐시 된 리소스를 제공 하는 것을 금지 하는 정책을 설정 하려면  
  
-   모든 캐시 캐시 레벨을 설정 하 여 요청 된 리소스를 제공 하는 것을 금지 하는 정책을 만드는 <xref:System.Net.Cache.HttpRequestCacheLevel>.  이 정책 수준 존재 하 고 원격 캐시 하는 자원도 제거 해야 함을 나타냅니다 로컬 캐시에서 리소스를 제거 합니다.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 로컬 캐시에 있는 경우에 요청한 리소스를 반환 하는 정책을 설정 하려면  
  
-   로컬 캐시에 캐시 레벨을 설정 하 여 있는 경우에 요청한 리소스를 반환 하는 정책을 만드는 <xref:System.Net.Cache.HttpRequestCacheLevel>.  요청 된 리소스가 캐시에 없는 경우는 <xref:System.Net.WebException> 예외가 throw 됩니다.  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 로컬 캐시에서 리소스를 제공 하지 못하도록 하는 정책을 설정 하려면  
  
-   로컬 캐시의 캐시 수준으로 설정 하 여 요청 된 리소스를 제공 하지 못하도록 하는 정책을 만드는 <xref:System.Net.Cache.HttpRequestCacheLevel>.  중간 캐시에서 요청 된 리소스의 유효성 검사 하므로 성공적으로 경우 중간 캐시는 요청한 리소스를 제공할 수 있습니다.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 요청한 리소스를 캐시에서 제공 하는 것을 금지 하는 정책을 설정 하려면  
  
-   모든 캐시 캐시 레벨을 설정 하 여 요청 된 리소스를 제공 하는 것을 금지 하는 정책을 만드는 <xref:System.Net.Cache.HttpRequestCacheLevel>.  서버에서 반환한 리소스를 캐시에 저장할 수 있습니다.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### 서버의 리소스가 캐시 된 복사본 보다 최신 이면 요청 된 리소스를 제공 하는 캐시 정책 설정  
  
-   서버의 리소스가 캐시 레벨을 설정 하 여 캐시 된 복사본 보다 오래 된 경우 요청 된 리소스를 제공 하는 캐시 정책 만들기 <xref:System.Net.Cache.HttpRequestCacheLevel>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## 참고 항목  
 [네트워크 응용 프로그램에 대한 캐시 관리](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [캐시 정책](../../../docs/framework/network-programming/cache-policy.md)   
 [위치 기반 캐시 정책](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [시간 기반 캐시 정책](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
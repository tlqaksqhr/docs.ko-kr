---
title: "&lt;applicationPool&gt; 요소(웹 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<applicationPool> 요소"
  - "applicationPool 요소"
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;applicationPool&gt; 요소(웹 설정)
ASP.NET 응용 프로그램이 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전에서 통합 모드로 실행 중인 경우 ASP.NET에서 프로세스 전체의 동작을 관리하기 위해 사용하는 구성 설정을 지정합니다.  
  
> [!IMPORTANT]
>  이 요소와 이 요소가 지원하는 기능은 ASP.NET 응용 프로그램이 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전에서 호스팅되는 경우에만 작동합니다.  
  
## 구문  
  
```  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`maxConcurrentRequestsPerCPU`|ASP.NET에서 각 CPU에 대해 허용하는 동시 요청 수를 지정합니다.|  
|`maxConcurrentThreadsPerCPU`|각 CPU의 응용 프로그램 풀에 대해 실행할 수 있는 동시 스레드 수를 지정합니다.  요청을 처리하기 위해 각 CPU에 대해 사용할 수 있는 관리되는 스레드 수를 제한할 수 있기 때문에 이 기능을 통해 ASP.NET 동시성을 다른 방법으로 제어할 수 있습니다.  이 설정의 기본값은 0으로, CLR 스레드 풀에서는 만들 수 있는 스레드 수가 제한되지만 ASP.NET에서는 각 CPU에 대해 만들 수 있는 스레드 수가 제한되지 않음을 의미합니다.|  
|`requestQueueLimit`|하나의 프로세스에서 ASP.NET에 대해 큐에 대기시킬 수 있는 최대 요청 수를 지정합니다.  하나의 응용 프로그램 풀에서 두 개 이상의 ASP.NET 응용 프로그램이 실행되는 경우 응용 프로그램 풀에 있는 모든 응용 프로그램에 대한 누적 요청 집합은 이 설정의 영향을 받습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|ASP.NET에서 호스트 응용 프로그램과 상호 작용하는 방법에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전을 통합 모드에서 실행하는 경우 이 요소 조합을 사용하여 ASP.NET에서 스레드를 관리하고 ASP.NET 응용 프로그램이 IIS 응용 프로그램 풀에서 호스팅될 때 요청을 큐에 대기시키는 방법을 구성할 수 있습니다.  IIS 6을 실행하거나 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]을 클래식 모드나 ISAPI 모드에서 실행하는 경우에는 이러한 설정이 무시됩니다.  
  
 `applicationPool` 설정은 특정 버전의 .NET Framework에서 실행되는 모든 응용 프로그램 풀에 적용되며,  aspnet.config 파일에 포함되어 있습니다.  이 파일의 버전에는 .NET Framework 버전 2.0 및 4용 버전이 있습니다. .NET Framework 버전 3.0 및 3.05은 버전 2.0과 aspnet.config 파일을 공유합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[win7](../../../../../includes/win7-md.md)]에서 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]을 실행하는 경우 모든 응용 프로그램 풀에 대해 별도의 aspnet.config 파일을 구성할 수 있습니다.  이렇게 하면 각 응용 프로그램 풀에 맞게 스레드의 성능을 조정할 수 있습니다.  
  
 `maxConcurrentRequestsPerCPU`에 대한 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]의 기본 설정인 "5000"을 사용하면 각 CPU에 대한 요청이 실제로 5,000개 이상 있지 않는 한 ASP.NET에서 제어하는 요청 제한을 효과적으로 해제하고  대신 CLR 스레드 풀에 따라 각 CPU의 동시성을 자동으로 관리할 수 있습니다.  비동기 요청 처리를 광범위하게 사용하거나 네트워크 I\/O에서 차단된 장기 실행 요청이 많이 있는 응용 프로그램은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]의 늘어난 기본 제한을 통해 이점을 얻을 수 있습니다.  `maxConcurrentRequestsPerCPU`를 0으로 설정하면 관리되는 스레드가 ASP.NET 요청을 처리하는 데 사용되지 않습니다.  응용 프로그램이 IIS 응용 프로그램 풀에서 실행되는 경우 요청이 IIS I\/O 스레드에 머물기 때문에 IIS 스레드 설정에 의해 동시성이 제한됩니다.  
  
 `requestQueueLimit` 설정은 ASP.NET 응용 프로그램의 Web.config 파일에 설정되는 [processModel](http://msdn.microsoft.com/ko-kr/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) 요소의 `requestQueueLimit` 특성과 같은 방식으로 작동합니다.  그러나 aspnet.config 파일의 `requestQueueLimit` 설정은 Web.config 파일의 `requestQueueLimit` 설정을 재정의합니다.  즉, 두 특성이 모두 설정된 경우\(기본 설정\), aspnet.config 파일의 `requestQueueLimit` 설정이 우선합니다.  
  
## 예제  
 다음 예제에서는 아래와 같은 경우에 aspnet.config 파일에서 ASP.NET 프로세스 전체의 동작을 구성하는 방법을 보여 줍니다.  
  
-   응용 프로그램이 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 응용 프로그램 풀에서 호스팅되는 경우  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]이 통합 모드에서 실행되고 있는 경우  
  
-   응용 프로그램에서 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 또는 이후 버전을 사용하고 있는 경우  
  
 이 예제의 값은 기본값입니다.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## 요소 정보  
  
|||  
|-|-|  
|네임스페이스||  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있음||  
  
## 참고 항목  
 [\<system.web\> 요소\(웹 설정\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
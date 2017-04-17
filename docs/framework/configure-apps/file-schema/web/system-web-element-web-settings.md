---
title: "&lt;system.web&gt; 요소(웹 설정) | Microsoft Docs"
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
  - "<system.Web> 요소"
  - "ASP.NET 구성 시스템"
  - "구성 파일[ASP.NET]"
  - "system.Web 요소"
  - "Web.config 구성 파일[ASP.NET]"
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;system.web&gt; 요소(웹 설정)
ASP.NET 호스팅 계층에서 프로세스 전체의 동작을 관리하는 방법에 대한 정보를 포함합니다.  
  
## 구문  
  
```  
<system.web>  
</system.web>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|aspnet.config 파일에서 IIS 응용 프로그램 풀에 대한 구성 설정을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<적용\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 응용 프로그램에 사용되는 모든 구성 파일의 루트 요소를 지정합니다.|  
  
## 설명  
 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]에서는 `system.web` 요소와 해당 자식 `applicationPool` 요소가 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]에 추가되었습니다.  [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전을 통합 모드에서 실행하는 경우 이 요소 조합을 사용하여 ASP.NET에서 스레드를 관리하는 방법과 ASP.NET이 IIS 응용 프로그램 풀에서 호스팅될 때 ASP.NET에서 요청을 큐에 대기시키는 방법을 구성할 수 있습니다.  [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전을 클래식 모드나 ISAPI 모드에서 실행하는 경우에는 이러한 설정이 무시됩니다.  
  
## 예제  
 다음 예제에서는 ASP.NET이 IIS 응용 프로그램 풀에서 호스팅될 때 aspnet.config 파일에서 ASP.NET 프로세스 전체의 동작을 구성하는 방법을 보여 줍니다.  이 예제에서는 IIS가 통합 모드에서 실행되고 있고 응용 프로그램에서 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 또는 이후 버전을 사용하고 있다고 가정합니다.  이 동작은 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]보다 이전 버전의 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]에서는 발생하지 않습니다.  이 예제의 값은 기본값입니다.  
  
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
 [\<applicationPool\> 요소\(웹 설정\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
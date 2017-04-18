---
title: "&lt;performanceCounter&gt; 요소(네트워크 설정) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<performanceCounter> 요소"
  - "performanceCounter 요소"
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;performanceCounter&gt; 요소(네트워크 설정)
네트워킹 성능 카운터를 사용하거나 사용하지 않도록 지정합니다.  
  
## 구문  
  
```  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|네트워킹 성능 카운터의 설정 여부를 지정합니다.  기본값은 `false`입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
 네트워킹 성능 카운터는 구성 파일에 사용할 수 있도록 설정해야 합니다.  모든 네트워킹 성능 카운터는 구성 파일에 있는 단일 설정으로 사용하거나 사용하지 않도록 설정됩니다.  개별 네트워킹 성능 카운터를 활성화하거나 비활성화할 수 없습니다.  특정 네트워킹 성능 카운터에 대한 자세한 내용은 [Networking Performance Counters](http://msdn.microsoft.com/ko-kr/d1860235-f643-46ae-846c-ff0ed8b0e3cd)를 참조하십시오.  
  
 네트워킹 성능 카운터를 사용하지 않는 것이 기본값입니다.  
  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 **활성화된** 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 네트워킹 성능 카운터를 사용하도록 <xref:System.Net> 및 관련 네임스페이스를 구성하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Networking Performance Counters](http://msdn.microsoft.com/ko-kr/d1860235-f643-46ae-846c-ff0ed8b0e3cd)
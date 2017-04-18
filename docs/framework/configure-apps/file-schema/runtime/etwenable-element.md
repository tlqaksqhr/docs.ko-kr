---
title: "&lt;etwEnable&gt; 요소 | Microsoft Docs"
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
  - "<etwEnable> 요소"
  - "etwEnable 요소"
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;etwEnable&gt; 요소
공용 언어 런타임 이벤트에 대한 이벤트 추적을 위해 Windows\(ETW\)를 사용할지 여부를 지정합니다.  
  
## 구문  
  
```  
<etwEnable enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> ETW를 사용해야 하는지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|true|Enable ETW  이는 Windows Vista 및 Windows Server 2008 운영 체제부터 Windows 버전의 기본값입니다.|  
|false|ETW 사용 안 함.  이전 버전의 Windows에 대한 기본값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 Windows Vista부터 ETW는 기본적으로 사용할 수 있습니다.  이 요소를 사용하여 응용 프로그램에 대한 ETW를 사용하지 않도록 설정합니다.  이전 버전의 Windows에서는 이 요소를 사용하여 응용 프로그램에 대해 ETW를 활성화합니다.  
  
> [!NOTE]
>  레지스트리 설정을 사용하여 서버에서 전역적으로 ETW를 사용하거나 사용하지 않도록 설정할 수 있습니다.  [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 응용 프로그램에 대한 ETW 추적을 사용하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [.NET Framework 로깅 제어](../../../../../docs/framework/performance/controlling-logging.md)
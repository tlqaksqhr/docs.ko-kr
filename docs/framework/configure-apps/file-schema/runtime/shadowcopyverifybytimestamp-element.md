---
title: "&lt;shadowCopyVerifyByTimestamp&gt;요소 | Microsoft Docs"
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
  - "<shadowCopyTimeStampVerification> 요소"
  - "shadowCopyTimeStampVerification 요소"
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;shadowCopyVerifyByTimestamp&gt;요소
섀도 복사가 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 기본 시작 동작을 사용하거나 .NET Framework의 이전 버전의 시작 동작으로 되돌릴지 여부를 지정합니다.  
  
## 구문  
  
```  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> 어셈블리를 섀도 복사하기 전에 업데이트되었는지 여부를 확인하기 위해 시작할 때 섀도 복사를 사용하는 응용 프로그램 도메인이 어셈블리 타임 스탬프를 비교할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|true|시작할 때 마지막으로 섀도 복사 디렉터리에 복사된 이후로 업데이트된 어셈블리만 복사합니다.  [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]의 기본값입니다.|  
|false|시작할 때 모든 파일을 복사한 이전 버전의 .NET Framework의 시작 동작으로 되돌립니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]부터 어셈블리는 해당 타임스탬프가 섀도 복사 디렉터리에 마지막으로 복사된 이후 변경된 것을 나타내는 경우에만 섀도 복사됩니다.  따라서 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)에 설명한 대로 섀도 복사를 사용하는 많은 응용 프로그램의 경우 시작 시간이 개선됩니다.  어셈블리 업데이트의 높은 비율과 빈도수를 가진 응용 프로그램은 동작의 변경에서 도움이 되지 않습니다.  이 경우, .NET Framework 이전 버전 동작을 복원 하기 위해 이 요소를 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]에서 섀도 복사의 기본 시작 동작을 비활성화하고 이전 버전의 .NET Framework의 시작 동작으로 되돌리는 방법을 보여줍니다.  
  
```  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 섀도 복사](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
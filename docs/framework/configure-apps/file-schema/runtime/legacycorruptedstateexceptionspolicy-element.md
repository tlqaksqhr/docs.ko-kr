---
title: "&lt;legacyCorruptedStateExceptionsPolicy&gt; 요소 | Microsoft Docs"
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
  - "<legacyCorruptedStateExceptionsPolicy> 요소"
  - "legacyCorruptedStateExceptionsPolicy 요소"
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;legacyCorruptedStateExceptionsPolicy&gt; 요소
공용 언어 런타임에서 관리 코드를 사용하여 액세스 위반과 기타 손상된 상태 예외를 catch할 수 있는지 여부를 지정합니다.  
  
## 구문  
  
```  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 응용 프로그램에서 액세스 위반 같은 손상된 상태 예외를 catch하도록 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|응용 프로그램에서 액세스 위반 같은 손상된 상태 예외를 catch하지 않습니다.  이 값이 기본값입니다.|  
|`true`|응용 프로그램에서 액세스 위반 같은 손상된 상태 예외를 catch합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 3.5 및 이전 버전에서는 공용 언어 런타임에서 관리 코드를 사용하여 손상된 프로세스 상태로 인해 발생한 예외를 catch할 수 있습니다.  액세스 위반은 이러한 예외 형식의 한 예입니다.  
  
 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터는 관리 코드가 `catch` 블록에서 이러한 형식의 예외를 더 이상 catch하지 않지만  이러한 변경 내용을 재정의하고 손상된 상태 예외를 다음과 같은 두 가지 방법으로 처리할 수 있습니다.  
  
-   `<legacyCorruptedStateExceptionsPolicy>` 요소의 `enabled` 특성을 `true`로 설정합니다.  이 구성 설정은 프로세스 전체에 적용되고 모든 메서드에 영향을 줍니다.  
  
 또는  
  
-   예외 `catch` 블록이 포함된 메서드에 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName> 특성을 적용합니다.  
  
 이 구성 요소는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램 동작을 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이전의 동작으로 되돌리고 모든 손상된 상태 예외를 catch하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>   
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
---
title: "&lt;gcAllowVeryLargeObjects&gt; 요소 | Microsoft Docs"
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
  - "<gcAllowVeryLargeObjects> 요소"
  - "gcAllowVeryLargeObjects 요소"
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# &lt;gcAllowVeryLargeObjects&gt; 요소
64 비트 플랫폼에서, 전체 크기가 2기가바이트 \(GB\) 보다 큰 배열을 지원합니다.  
  
## 구문  
  
```  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 64 비트 플랫폼에서 총 크기가 2GB 보다 큰 배열은 사용할지 여부를 지정 합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|총 크기가 2GB 보다 큰 배열은 사용할 수 없습니다.  이 값이 기본값입니다.|  
|`true`|64 비트 플랫폼에서, 총 크기가 2GB 보다 큰 배열을 사용할 수 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 응용 프로그램 구성 파일에서 이 요소를 사용하여 배열 크기를 2 GB 보다 큰 배열을 사용할 수 있지만, 개체 또는 배열 크기에 대한 다른 제한을 변경하지 않습니다.  
  
-   배열에 있는 요소의 최대 수는 <xref:System.UInt32.MaxValue?displayProperty=fullName> 입니다.  
  
-   단일 차원에 최대 인덱스는 바이트 배열 및 단일 바이트 구조체의 배열의 경우 2,147,483,591\(0x7FFFFFC7\) 이고 다른 형식의 경우 2,146,435,071\(0X7FEFFFFF\) 입니다.  
  
-   문자열과 그 외 배열이 아닌 개체의 최대 크기는 변경되지 않습니다.  
  
> [!CAUTION]
>  이 기능을 사용하기 전에, 모든 배열의 크기가 2GB 보다 작다고 가정하는, 안전하지 않은 코드가 응용 프로그램에 포함 되지 않도록 확인하시기 바랍니다.  예를 들어, 배열을 버퍼처럼 사용하는 안전하지 않은 코드가 배열이 2GB를 초과하지 않는다는 가정하에 작성됐을 경우, 해당 코드는 버퍼 오버런에 취약할 수 있습니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램에서 이 기능을 사용하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
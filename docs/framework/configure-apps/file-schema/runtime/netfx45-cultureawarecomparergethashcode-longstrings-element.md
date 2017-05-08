---
title: "&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; 요소 | Microsoft Docs"
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
  - "NetFx45_CultureAwareComparerGetHashCode_LongStrings 요소"
  - "<NetFx45_CultureAwareComparerGetHashCode_LongStrings> 요소"
  - "GetHashCode 메서드"
  - "해시 코드, 계산"
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; 요소
런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 메서드에 대한 해시 코드를 계산하기 위해 고정된 양의 메모리를 사용할지 여부를 지정합니다.  
  
 \<configuration\>  
\<runtime\>  
\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>  
  
## 구문  
  
```vb  
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 해시 코드를 계산할 때 공용 언어 런타임에서 고정된 양의 메모리를 할당할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|0|공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 메서드에 가변적인 양의 메모리를 할당합니다. 이 값이 기본값입니다.|  
|1|공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 메서드에 고정적인 양의 메모리를 할당합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 기본적으로, 공용 언어 런타임은 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 메서드에 가변적인 양의 메모리를 할당하고, 이 메서드가 \(길이가 수백만 자 이상인\) 매우 큰 문자열의 해시 코드를 계산하려고 할 때 <xref:System.ArgumentException>이 throw될 수 있습니다. 이 요소를 응용 프로그램 구성 파일에 추가하고 `enabled` 특성을 "1"로 설정하여 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 메서드가 해시 코드의 계산을 위해 고정된 양의 메모리를 할당하는 대체 알고리즘을 사용하도록 지정할 수 있습니다.  
  
> [!IMPORTANT]
>  `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 요소는 [!INCLUDE[win8](../../../../../includes/win8-md.md)] 이상의 버전에 사용되지 않습니다.  
  
## 참고 항목  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>   
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
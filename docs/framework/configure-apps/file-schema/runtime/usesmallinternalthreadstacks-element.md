---
title: "&lt;UseSmallInternalThreadStacks&gt; 요소 | Microsoft Docs"
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
  - "<UseSmallInternalThreadStacks> 요소"
  - "UseSmallInternalThreadStacks 요소"
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;UseSmallInternalThreadStacks&gt; 요소
CLR\(공용 언어 런타임\)은 스레드에 대한 기본 스택 크기를 사용하는 대신 내부적으로 사용하는 특정 스레드를 만들 때 명시적 스택 크기를 지정하여 메모리 사용을 줄이도록 요청합니다.  
  
## 구문  
  
```  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|enabled|필수 특성입니다.<br /><br /> 내부적으로 사용하는 특정 스레드를 만들 때 기본 스택 크기 대신 CLR이 명시적 스택 크기를 사용하도록 요청할지 여부를 지정합니다.  명시적 스택 크기는 1MB 기본 스택 크기보다 작습니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|true|명시적 스택 크기를 요청합니다.|  
|false|기본 스택 크기를 사용합니다.  [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]의 기본값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 CLR이 내부 스레드에 사용하는 명시적 스레드 크기는 요청이 적용되면 기본 크기보다 작기 때문에 이 구성 요소는 프로세스에서 감소된 가상 메모리 사용을 요청하는 데 사용됩니다.  
  
> [!IMPORTANT]
>  이 구성 요소는 절대 요구 사항이 아닌 CLR 요청입니다.  [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]에서는 x 86 아키텍처의 경우에만 요청이 수행됩니다.  이 요소는 CLR의 향후 버전에서 완전히 무시되거나 선택한 내부 스레드에 항상 사용되는 명시적 스택 크기에 의해 대체될 수 있습니다.  
  
 더 작은 가상 메모리에 대해 이 구성 요소 거래 안정성 지정은 더 작은 스택 크기에서 스택 오버플로가 발생할 가능성이 더 크기 때문에 CLR이 요청을 허가하는 경우 사용합니다.  
  
## 예제  
 다음 예제에서는 CLR이 내부적으로 사용하는 특정 스레드에 대해 명시적 스택 크기를 사용하도록 요청하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
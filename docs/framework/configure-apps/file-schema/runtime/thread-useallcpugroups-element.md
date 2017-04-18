---
title: "&lt;Thread_UseAllCpuGroups&gt; 요소 | Microsoft Docs"
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
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;Thread_UseAllCpuGroups&gt; 요소
런타임이 모든 CPU 그룹에서 관리되는 스레드를 분포하는지 여부를 지정합니다.  
  
## 구문  
  
```vb  
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 모든 CPU 그룹에서 관리되는 스레드를 분포하는지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임은 여러 CPU 그룹에 관리되는 스레드를 분포하지 않습니다.  이 값이 기본값입니다.|  
|`true`|컴퓨터에 여러 CPU 그룹과 [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소가 사용되는 경우 런타임은 여러 CPU 그룹에 관리되는 스레드를 배포합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 컴퓨터에 여러 CPU 그룹이 있을 경우 이 요소를 사용하면 런타임에 모든 CPU 그룹에 관리되는 스레드를 배포합니다.  이 기능을 사용하려면 가비지 수집을 모든 CPU 그룹으로 확장하고 힙을 만들고 균형 조정할 때 모든 코어를 계정으로 가져오는 [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소도 활성화해야 합니다.  [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소를 사용하려면 [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소를 사용할 수 있어야 합니다.  이러한 요소를 사용할 수 없으면 `<Thread_UseAllCpuGroups>` 요소를 사용해도 효과가 없습니다.  
  
## 예제  
 다음 예제에서는 복수 CPU 그룹에 지원을 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<GCCpuGroup\> 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
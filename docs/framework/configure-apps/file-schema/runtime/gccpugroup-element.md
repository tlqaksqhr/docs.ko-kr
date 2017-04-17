---
title: "&lt;GCCpuGroup&gt; 요소 | Microsoft Docs"
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
  - "<GCCpuGroup> 요소"
  - "GCCpuGroup 요소"
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;GCCpuGroup&gt; 요소
가비지 수집이 여러 CPU 그룹을 지원하는지 여부를 지정합니다.  
  
## 구문  
  
```  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 가비지 수집이 여러 CPU 그룹을 지원하는지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|가비지 수집은 여러 CPU 그룹 지원을 하지 않습니다.  이 값이 기본값입니다.|  
|`true`|서버 가비지 수집이 설정 되어 있으면 가비지 수집은 여러 CPU 그룹을 지원합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 컴퓨터에 여러 CPU 그룹이 있고 서버 가비지 수집이 설정 되어 있을 때 \(다음 [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소를 참고하십시오.\), 이 요소를 사용하는 것은 모든 CPU의 그룹에서 가비지 수집을 확장하고 힙을 만들고 균형을 맞출 때 모든 코어를 사용하도록 합니다.  
  
> [!NOTE]
>  이 요소는 가비지 수집 스레드에만 적용 됩니다.  런타임을 사용자 스레드 CPU의 모든 그룹에서 배포할 수 있도록 하려면 [\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 요소를 설정해야 합니다.  
  
## 예제  
 다음 예제에서는 복수 CPU 그룹에 가라지 수집을 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/ko-kr/ba2c6c67-5778-497c-9fac-5f793b5500c7)   
 [워크스테이션 및 서버 가비지 수집](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
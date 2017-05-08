---
title: "&lt;ThrowUnobservedTaskExceptions&gt; 요소 | Microsoft Docs"
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
  - "<ThrowUnobservedTaskExceptions> 요소"
  - "ThrowUnobservedTaskExceptions 요소"
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;ThrowUnobservedTaskExceptions&gt; 요소
작업이 처리 되지 않은 예외에서 실행 중인 프로세스를 종료 해야 하는지 여부를 지정 합니다.  
  
## 구문  
  
```vb  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 작업이 처리 되지 않은 예외에서 실행 중인 프로세스를 종료 해야 하는지 여부를 지정 합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|예외가 처리 되지 않은 작업에 대해 실행 중인 프로세스는 종료 되지 않습니다.  이 값이 기본값입니다.|  
|`true`|예외가 처리 되지 않은 작업에 대해 실행 중인 프로세스는 종료 됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
|||  
  
## 설명  
 만약 <xref:System.Threading.Tasks.Task> 와 연결된 예외가 관찰 되어 지지 않은 경우라면, 부모 작어비 연결 되어 있지 않은 <xref:System.Threading.Tasks.Task.Wait%2A> 연산자가 없고, <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> 속성은 작업 예외가 관찰 되지 않은 상태로 읽혀 지지 않습니다.  
  
 기본적으로, [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에서, 관찰 되지 않은 예외를 갖는 <xref:System.Threading.Tasks.Task> 가 가비지 수집되어 질 떄, 종료자에서 예외를 throw 하고 프로세스를 종료 합니다.  프로세스 종료는 가비지 수집 및 종료 시기에 의해 결정 됩니다.  
  
 개발자가 작업 기반 비동기 코드를 더 쉽게 작성할 수 있게 하기 위해서, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]가 관찰되지 않은 예외에 대한 기본 예외 동작을 변경합니다.  아직 관찰 되지 않은 예외는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트를 발생 시키지만, 기본적으로 프로세스는 종료 되지 않습니다.  대신, 예외는 이벤트가 발생한 이후 이벤트 처리기가 예외를 관찰했는지의 여부에 상관없이 런타임에 의해 무시되어 집니다.  
  
 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에서, [\<ThrowUnobservedTaskExceptions\> 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) 를 응용 프로그램 구성 파일에서 예외를 throw 하는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 동작을 사용할 수 있습니다.  
  
 다음 방법 중 하나로 예외 동작을 지정할 수도 있습니다.  
  
-   환경 변수 `COMPlus_ThrowUnobservedTaskExceptions` \(`set COMPlus_ThrowUnobservedTaskExceptions=1`\)를 설정합니다.  
  
-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework key 에서 레지스트리 DWORD 값을 ThrowUnobservedTaskExceptions \= 1로 설정합니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램 구성 파일을 사용 하여 작업에서 예외를 throw를 사용 하는 방법을 보여 줍니다.  
  
```  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
  
```  
  
## 예제  
 다음 예제에서는 작업에서 관찰 되지 않은 예외가 throw 되는 방법을 보여 줍니다.  출시 된 프로그램이 제대로 작동 하려면 코드를 실행 해야 합니다.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
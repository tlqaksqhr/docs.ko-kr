---
title: "&lt;switches&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#switches"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<switches> 요소"
  - "switches 요소"
  - "추적 스위치, <switches> 요소"
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;switches&gt; 요소
추적 스위치와 추적 스위치를 설정할 수준이 들어 있습니다.  
  
## 구문  
  
```  
  
      <switches>   
</switches>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<추가\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|추적 스위치를 설정할 수준을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`System.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
  
## 설명  
 추적 스위치를 구성 파일에 넣으면 추적 스위치 수준을 변경할 수 있습니다.  스위치가 <xref:System.Diagnostics.BooleanSwitch>이면 이를 설정 또는 해제할 수 있고,  스위치가 <xref:System.Diagnostics.TraceSwitch>이면 스위치에 다른 수준을 할당하여 추적 형식을 지정하거나 응용 프로그램에서 출력하는 메시지를 디버깅할 수 있습니다.  
  
## 예제  
 다음 예제에서는 **\<switch\>** 요소를 사용하여`General` 추적 스위치를 [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) 수준으로 설정한 다음, `Data` Boolean 추적 스위치를 활성화하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Switch>   
 <xref:System.Diagnostics.TraceSwitch>   
 <xref:System.Diagnostics.BooleanSwitch>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
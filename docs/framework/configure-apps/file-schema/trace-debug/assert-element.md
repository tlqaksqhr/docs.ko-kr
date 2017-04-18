---
title: "&lt;assert&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assert"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assert> 요소"
  - "assert 요소"
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;assert&gt; 요소
<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정하고 메시지를 쓸 파일 이름도 지정합니다.  
  
## 구문  
  
```  
  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`assertuienabled`|선택적 특성입니다.<br /><br /> **Debug.Assert** 메서드가 **false**인 경우 메시지 상자를 표시할지 지정합니다.|  
|`logfilename`|선택적 특성입니다.<br /><br /> **Debug.Assert**가 **false**인 경우 메시지를 쓸 파일 이름을 지정합니다.|  
  
## assertuienabled 특성  
  
|값|설명|  
|-------|--------|  
|`true`|메시지 상자를 표시합니다.  이 값이 기본값입니다.|  
|`false`|메시지 상자를 표시하지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
  
## 설명  
 **\<assert\>** 요소의 두 특성은 모두 선택적입니다.  메시지를 쓸 파일을 지정하지 않고 메시지 상자를 비활성화할 수도 있고 메시지 상자가 활성화된 상태에서 메시지를 쓸 파일을 지정할 수도 있습니다.  
  
## 예제  
 다음 예제에서는 **Debug.Assert**를 호출할 때 메시지 상자 표시를 비활성화하고 메시지를 `c:\log.txt`에 쓰는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Debug>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
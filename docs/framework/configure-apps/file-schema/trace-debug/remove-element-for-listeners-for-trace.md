---
title: "&lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;remove&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> 요소"
  - "remove 요소"
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;remove&gt; 요소
**Listeners** 컬렉션에서 수신기를 제거합니다.  
  
## 구문  
  
```  
  
<remove name="listener name" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**name**|필수 특성입니다.<br /><br /> **Listeners** 컬렉션에서 제거할 수신기 이름입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|메시지를 수집하여 저장하고 라우트하는 수신기를 지정합니다.  수신기는 추적 출력을 적절한 대상으로 안내합니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`trace`|ASP.NET 추적 서비스를 구성합니다.|  
  
## 설명  
  
> [!NOTE]
>  `Listeners` 컬렉션에서 <xref:System.Diagnostics.DefaultTraceListener>를 제거하면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 메서드의 동작이 변경됩니다.  `Assert` 또는 `Fail` 메서드를 호출하면 메시지 상자가 정상적으로 표시되지만 `Listeners` 컬렉션에 <xref:System.Diagnostics.DefaultTraceListener>가 없는 경우에는 메시지 상자가 표시되지 않습니다.  
  
## 예제  
 다음 예제에서는 추적 **Listeners** 컬렉션에서 기본 추적 수신기를 제거하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
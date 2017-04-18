---
title: "Enabling JIT-Attach Debugging | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "JIT-attach debugging"
  - "debugging [.NET Framework], JIT-attach debugging"
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Enabling JIT-Attach Debugging
JIT 연결 디버깅이란 오류 발생 시 프로세스에 디버거를 연결하는 동작을 나타내며, 이 연결은 특정 메서드 또는 함수에 의해 트리거될 수도 있습니다.  
  
 JIT 연결 디버깅은 다음 오류 조건에서 사용됩니다.  
  
-   네이티브 코드 및 관리 코드에서 처리되지 않은 예외  
  
-   <xref:System.Environment.FailFast%2A?displayProperty=fullName> 메서드 또는  [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) 함수 \(Windows 7 제품군\).  
  
-   심각한 런타임 오류  
  
 JIT 연결 디버깅은 다음 메서드 및 함수에 대한 호출을 통해서도 트리거됩니다.  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName> 메서드  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName> 메서드  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) Win32 함수.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이전의 .NET Framework에서는 네이티브 디버거의 동작과 관리되는 디버거의 동작을 제어하는 레지스트리 키를 디버거별로 다르게 제공했습니다.  그러나 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터는 단일 레지스트리 키 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\Current Version\\AeDebug로 제어가 통합되었습니다.  이 키에 대해 여러 가지 값을 설정할 수 있고 이 값을 통해 디버거 호출 여부가 결정되고, 디버거 호출 시 사용자 상호 작용이 필요한 대화 상자를 통해 호출되는지 여부도 결정됩니다.  이 레지스트리 키를 설정하는 방법에 대한 자세한 내용은 MSDN 라이브러리에 있는  [Configuring Automatic Debugging](http://go.microsoft.com/fwlink/?LinkId=181767) 을 참조하십시오.  
  
## 참고 항목  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [쉽게 디버깅할 수 있도록 이미지 만들기](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Enabling Profiling](http://msdn.microsoft.com/ko-kr/3b669676-f0e0-4ebf-8674-68986dd2020d)
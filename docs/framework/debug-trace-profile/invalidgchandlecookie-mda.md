---
title: "invalidGCHandleCookie MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid cookies"
  - "cookies, invalid"
  - "managed debugging assistants (MDAs), invalid cookies"
  - "InvalidGCHandleCookie MDA"
  - "invalid cookies"
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# invalidGCHandleCookie MDA
잘못된 <xref:System.IntPtr> 쿠키를 <xref:System.Runtime.InteropServices.GCHandle>로 변환하려고 할 때 `invalidGCHandleCookie` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 증상  
 <xref:System.IntPtr>의 <xref:System.Runtime.InteropServices.GCHandle>을 사용하거나 검색하려고 시도하는 동안 액세스 위반 및 메모리 손상과 같은 정의되지 않은 동작이 발생했습니다.  
  
## 원인  
 쿠키가 원래 <xref:System.Runtime.InteropServices.GCHandle>에서 쿠키가 만들어지지 않았기 때문에 잘못될 수 있고, 이미 해제된 <xref:System.Runtime.InteropServices.GCHandle>을 나타낼 수 있으며, 다른 응용 프로그램 도메인의 <xref:System.Runtime.InteropServices.GCHandle>에 대한 쿠키이거나, <xref:System.Runtime.InteropServices.GCHandle>인 네이티브 코드로 마샬링되었지만 캐스트가 시도된 <xref:System.IntPtr>로 CLR에 다시 전달되었을 수 있습니다.  
  
## 해결  
 <xref:System.Runtime.InteropServices.GCHandle>의 올바른 <xref:System.IntPtr> 쿠키를 지정합니다.  
  
## 런타임 효과  
 이 MDA를 사용하는 경우 다시 전달된 쿠키 값이 MDA를 사용하지 않는 경우의 값과 다르기 때문에 디버거가 해당 개체로의 루트를 더 이상 추적할 수 없습니다.  
  
## Output  
 잘못된 <xref:System.IntPtr> 쿠키 값이 보고됩니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>   
 <xref:System.Runtime.InteropServices.GCHandle>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
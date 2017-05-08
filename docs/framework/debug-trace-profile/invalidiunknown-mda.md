---
title: "invalidIUnknown MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid IUnknown pointer"
  - "InvalidIUnknown MDA"
  - "invalid IUnknown pointers"
  - "IUnknown pointers"
  - "managed debugging assistants (MDAs), invalid IUnknown pointer"
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# invalidIUnknown MDA
`invalidIUnknown` MDA\(관리 디버깅 도우미\)는 잘못된 `IUnknown` 포인터가 네이티브 코드에서 관리 코드로 전달될 때 활성화됩니다.  `IUnknown` 인터페이스에 대해 쿼리될 때 `IUnknown`에서 성공을 반환하지 못합니다.  
  
## 증상  
 인수 마샬링 중 COM 인터페이스 포인터를 마샬링할 때 예기치 않은 오류가 발생합니다.  
  
## 원인  
 COM 인터페이스의 잘못된 `QueryInterface` 구현이 CLR에 전달되었습니다.  
  
## 해결  
 `QueryInterface` 구현을 수정합니다.  
  
## 런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않습니다.  
  
## 출력  
 오류에 대한 설명입니다.  
  
## 구성  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
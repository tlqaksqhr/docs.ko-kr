---
title: "invalidMemberDeclaration MDA | Microsoft Docs"
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
  - "invalid member declaration"
  - "InvalidMemberDeclaration MDA"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# invalidMemberDeclaration MDA
`invalidMemberDeclaration` MDA\(관리 디버깅 도우미\)는 COM에서 호출할 멤버의 매개 변수를 마샬링하는 방법을 결정하는 동안 발생 하는 오류를 보고하기 위해 활성화됩니다.  
  
## 증상  
 호출된 관리되는 메서드 없이 실패 HRESULT가 COM에 반환됩니다.  
  
## 원인  
 이는 매개 변수 중 하나의 호환되지 않는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성 때문일 가능성이 큽니다.  
  
## 해결  
 매개 변수에서 유효한 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 지정합니다.  
  
## 런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않습니다.  
  
## 출력  
 멤버 이름, 형식 이름 및 오류 메시지를 포함하는 정보 메시지입니다.  
  
## 구성  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)
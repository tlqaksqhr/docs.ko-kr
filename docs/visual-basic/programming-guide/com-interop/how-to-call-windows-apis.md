---
title: "How to: Call Windows APIs (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "API calls"
  - "Windows API, calling"
  - "API calls, platform invoke"
  - "calls, stored procedures"
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Call Windows APIs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 user32.dll에서 `MessageBox` 함수를 정의하여 호출한 다음 문자열을 전달합니다.  
  
## 예제  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System> 네임스페이스에 대한 참조  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   메서드가 static이 아닌 abstract이거나 이전에 정의된 경우.  부모 형식이 인터페이스이거나 *name* 또는 *dllName*의 길이가 0인 경우  \(<xref:System.ArgumentException>\)  
  
-   *name* 또는 *dllName*이 `Nothing`인 경우  \(<xref:System.ArgumentNullException>\)  
  
-   포함하는 형식이 이전에 `CreateType`을 사용하여 이미 만들어진 경우  \(<xref:System.InvalidOperationException>\)  
  
## 참고 항목  
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ko-kr/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)   
 [관리되지 않는 DLL 함수 사용](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)   
 [Defining a Method with Reflection Emit](http://msdn.microsoft.com/ko-kr/84fd3bf6-628f-41aa-83d9-b990cf926e81)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)
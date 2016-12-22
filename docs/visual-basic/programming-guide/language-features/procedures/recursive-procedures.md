---
title: "Recursive Procedures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "procedures, that call themselves"
  - "procedures, recursive"
  - "procedures, calling"
  - "recursive procedures"
  - "functions [Visual Basic], calling recursively"
  - "recursion"
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Recursive Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*재귀* 프로시저는 자신을 호출하는 프로시저입니다.  일반적으로 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드를 작성하는 데 재귀 프로시저가 가장 효과적인 방법은 아닙니다.  
  
 다음 프로시저에서는 재귀를 사용하여 원래 인수의 계승을 구합니다.  
  
 [!code-vb[VbVbcnProcedures#51](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## 재귀 프로시저에 관한 고려 사항  
 **제한 조건**.  재귀를 종료할 수 있는 조건을 하나 이상 테스트하도록 재귀 프로시저를 디자인해야 하며, 적당한 횟수의 재귀 호출에도 그러한 조건이 만족되지 않는 경우도 처리해야 합니다.  오류 없이 만족될 수 있는 조건이 하나라도 없으면 프로시저가 무한 루프를 실행하게 될 위험이 많습니다.  
  
 **메모리 사용**.  응용 프로그램에는 지역 변수에 사용할 수 있는 공간이 한정되어 있습니다.  프로시저는 자신을 호출할 때마다 해당 지역 변수의 추가 복사본을 위해 해당 공간보다 많은 양의 공간을 사용합니다.  이 프로세스가 무한정 계속되면 결국 <xref:System.StackOverflowException> 오류가 발생합니다.  
  
 **효율성**.  거의 모든 경우에 재귀 대신 루프를 사용할 수 있습니다.  루프에는 인수를 전달하고, 추가 저장소를 초기화하고, 값을 반환해야 하는 등의 오버헤드가 없습니다.  재귀 호출을 사용하지 않을 경우 성능이 훨씬 더 좋을 수 있습니다.  
  
 **상호 재귀**.  두 프로시저가 서로를 호출하는 경우 성능이 매우 저하되거나 무한 루프가 되기도 합니다.  이러한 디자인은 단일 재귀 프로시저와 동일한 문제를 나타내지만 검색하고 디버그하기는 더 어려울 수 있습니다.  
  
 **괄호를 사용한 호출**.  `Function` 프로시저가 자신을 재귀적으로 호출하는 경우 인수 목록이 없더라도 프로시저 이름 다음에 괄호를 사용해야 합니다.  괄호가 없으면 함수 이름이 함수의 반환 값을 나타내는 것으로 간주됩니다.  
  
 **테스트**.  재귀 프로시저를 작성할 때는 항상 일정 제한 조건을 만족시키도록 매우 신중하게 테스트해야 합니다.  또한 재귀 호출이 너무 많아서 메모리가 부족해지지 않도록 해야 합니다.  
  
## 참고 항목  
 <xref:System.StackOverflowException>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [예외 문제 해결: System.StackOverflowException](../Topic/Troubleshooting%20Exceptions:%20System.StackOverflowException.md)
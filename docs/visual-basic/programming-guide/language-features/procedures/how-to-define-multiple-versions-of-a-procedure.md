---
title: "How to: Define Multiple Versions of a Procedure (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedures, overloading"
  - "procedures, multiple versions"
  - "procedure overloading, multiple versions"
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Define Multiple Versions of a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저를 *오버로딩*하여 각 버전에 대해 같은 이름을 사용하되 다른 매개 변수 목록을 사용하면 프로시저를 여러 버전으로 정의할 수 있습니다.  오버로딩은 이름을 다르게 지정하지 않고도 밀접하게 관련된 여러 버전의 프로시저를 정의하기 위해서 사용하며  
  
 자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)을 참조하십시오.  
  
### 여러 버전의 프로시저를 정의하려면  
  
1.  정의할 각 프로시저 버전에 대해 `Sub` 또는 `Function` 선언문을 작성합니다.  모든 선언에서 동일한 프로시저 이름을 사용합니다.  
  
2.  각 선언에서 `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용합니다.  선언에서 선택적으로 `Overloads`를 생략할 수 있지만 선언 중 하나에 포함할 경우에는 다른 모든 선언에도 포함해야 합니다.  
  
3.  각 선언문 뒤에 버전의 매개 변수 목록과 일치하는 인수를 호출 코드에서 제공하는 특별한 경우를 처리하기 위한 프로시저 코드를 작성합니다.  호출 코드에서 제공한 매개 변수를 테스트할 필요는 없습니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 프로시저의 일치하는 버전에 컨트롤을 전달합니다.  
  
4.  `End Sub` 또는 `End Function` 문을 적절하게 사용하여 프로시저의 각 버전을 종료합니다.  
  
## 예제  
 다음 예제에서는 고객의 잔액에 대해 트랜잭션을 게시하도록 `Sub` 프로시저를 정의합니다.  이 예제에서는 `Overloads` 키워드를 사용하여 두 버전의 프로시저를 정의합니다. 하나는 고객을 이름으로 수락하고 다른 하나는 계정 번호로 수락합니다.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 호출 코드는 고객 ID를 `String` 또는 `Integer`로 얻은 다음 어떠한 경우에든 동일한 호출 문을 사용할 수 있습니다.  
  
 이러한 버전의 `post` 프로시저를 호출하는 방법에 대한 자세한 내용은 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)을 참조하십시오.  
  
## 코드 컴파일  
 오버로드된 각 버전이 프로시저 이름은 동일하지만 매개 변수 목록이 다른지 확인합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
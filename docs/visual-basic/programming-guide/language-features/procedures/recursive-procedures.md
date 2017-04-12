---
title: "재귀 프로시저 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fc95cd5f7cfd5637f6282c6ef571eb81bac1816
ms.lasthandoff: 03/13/2017

---
# <a name="recursive-procedures-visual-basic"></a>재귀 프로시저(Visual Basic)
A *재귀* 절차는 자신을 호출 하는 하나입니다. 일반적으로 이것이 작성 하는 가장 효과적인 방법은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다.  
  
 다음 절차에서는 원래 인수의 계승 계산을 재귀를 사용 합니다.  
  
 [!code-vb[VbVbcnProcedures #&51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>재귀 프로시저에 대 한 고려 사항  
 **제한 조건**합니다. 재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 적절 한 횟수의 재귀 호출 내에서 없는 이러한 조건을 충족 하는 경우를도 처리 해야 합니다. 오류 없이 충족 될 수 있는 하나 이상의 조건 없이 프로시저는 무한 루프를 실행 한 높은 위험을 실행 합니다.  
  
 **메모리 사용량**합니다. 응용 프로그램에 제한 된 양의 지역 변수에 대 한 공간. 프로시저는 자신을 호출할 때마다 사용 하 여 그만큼의 공간이 더는 지역 변수의의 추가 복사본에 대 한 합니다. 이 프로세스는 무기한 계속 되 면 그로 인해는 <xref:System.StackOverflowException>오류.</xref:System.StackOverflowException>  
  
 **효율성**합니다. 거의 항상 재귀에 대 한 루프를 대체할 수 있습니다. 루프는 인수 전달 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드는 없습니다. 성능 재귀 호출 하지 않고 훨씬 향상 될 수 있습니다.  
  
 **상호 재귀**합니다. 두 절차 서로 호출 하는 경우 성능이 매우 저하 또는 심지어는 무한 루프를 확인할 수 있습니다. 이러한 디자인을 단일 재귀 프로시저와 같은 문제를 표시 하지만 검색 하 고 디버그 어려울 수 있습니다.  
  
 **괄호를 사용한 호출**합니다. 경우는 `Function` 재귀적으로 프로시저 호출, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다. 그렇지 않은 경우 함수 이름은 함수의 반환 값을 나타내는 것으로 합니다.  
  
 **테스트**합니다. 재귀 프로시저를 작성 하는 경우 항상 제한 일부 조건이 충족 되었는지 확인 하려면 신중 하 게 테스트 해야 있습니다. 또한 재귀 호출이 너무 많아서 인해 메모리가 부족 해지지 확인 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.StackOverflowException></xref:System.StackOverflowException>   
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [Function 프로시저](./function-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [문제 해결 절차](./troubleshooting-procedures.md)   
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [예외 문제 해결: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)

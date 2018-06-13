---
title: 재귀 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 8ea7741c943ea563fbd0c7649ac0ff85b2f9ebba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650217"
---
# <a name="recursive-procedures-visual-basic"></a>재귀 프로시저(Visual Basic)
A *재귀* 절차는 자신을 호출 하는 하나입니다. 일반적으로 Visual Basic 코드를 작성 하려면 가장 효과적인 방법은 아닙니다.  
  
 다음 절차 재귀를 사용 하 여 원래 인수의 계승값을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>재귀 프로시저에 대 한 고려 사항  
 **제한 조건**합니다. 재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 재귀적 호출 수를 적절 한 내 없는 이러한 조건이 충족 되는 위치 하는 경우도 처리 해야 합니다. 오류 없이 충족 될 수 있는 하나 이상의 조건 없는 프로시저 무한 루프로 실행의 위험 수준이 높은 실행 됩니다.  
  
 **메모리 사용량**. 응용 프로그램에 제한 된 양의 지역 변수에 대 한 공간. 프로시저가 자신을 호출할 때마다 사용 된 공간 중 지역 변수가의 추가 복사본에 대 한 합니다. 이 프로세스는 무기한 계속 됩니다, 결국 하면는 <xref:System.StackOverflowException> 오류입니다.  
  
 **효율성**합니다. 거의 항상 재귀에 대 한 루프를 대체할 수 있습니다. 루프에는 인수 전달 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드가 없습니다. 성능 재귀 호출 하지 않고 훨씬 향상 될 수 있습니다.  
  
 **상호 재귀**합니다. 두 절차 서로 호출 하는 경우 성능이 매우 저하 또는 심지어 무한 루프를 알 수 있습니다. 이러한 디자인 단일 재귀 절차와 동일한 문제가 되지만, 검색 하 고 디버그 어려울 수 있습니다.  
  
 **괄호를 사용한 호출**합니다. 경우는 `Function` 프로시저가 자신을 호출 재귀적으로, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다. 그렇지 않은 경우 함수 이름은 함수의 반환 값을 나타내는 것으로 합니다.  
  
 **테스트**합니다. 재귀 프로시저를 작성 하는 경우 항상 제한 일부 조건이 충족 되었는지 확인 하려면 매우 신중 하 게 테스트 해야 있습니다. 또한 재귀 호출이 너무 많이 메모리에서 실행할 수 없음을 확인 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.StackOverflowException>  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [예외 문제 해결: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)

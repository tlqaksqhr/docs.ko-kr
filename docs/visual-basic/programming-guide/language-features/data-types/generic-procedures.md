---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 686087e4520ea5e6e69e5906c628af3ad54749da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
A *제네릭 프로시저*라고도 하는 *제네릭 메서드*, 하나 이상의 형식 매개 변수를 사용 하 여 정의 하는 절차입니다. 따라서 호출 코드를를 프로시저를 호출할 때마다 데이터 형식을 요구 사항에 맞출 수 있습니다.  
  
 프로시저는 제네릭 클래스 또는 일반 구조체 내에 정의 되는 것 만으로 제네릭이 아닙니다. 제네릭일, 해당 프로시저는 일반 매개 변수를 걸릴 수 있습니다 하나 이상의 형식 매개 변수를 사용 해야 합니다. 제네릭이 아닌 프로시저 및 제네릭이 아닌 클래스, 구조, 제네릭 클래스 또는 구조체를 포함 하거나 모듈에서 제네릭 프로시저를 포함 될 수 있습니다.  
  
 제네릭 프로시저의 반환 형식이 있으며 자체 프로시저에서 코드를 설정한 경우에 일반 매개 변수 목록의 해당 형식 매개 변수를 사용할 수 있습니다.  
  
## <a name="type-inference"></a>형식 유추  
 제네릭 프로시저가 형식 인수를 전혀 제공 하지 않고 호출할 수 있습니다. 이러한 방식으로 호출을 하는 경우 컴파일러는 프로시저의 형식 인수에 전달 하는 적절 한 데이터 형식을 확인 하려고 합니다. 이 라고 *형식 유추*합니다. 다음 코드는 호출을 보여 줍니다. 컴파일러 유추 하 종류를 전달 해야 `String` 형식 매개 변수에 `t`합니다.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 컴파일러가 호출한 컨텍스트에서 형식 인수를 유추할 수 없습니다, 오류를 보고 합니다. 이러한 오류가 발생할 수는 배열의 차수가 일치 하지 않는 경우 예를 들어, 형식 매개 변수 배열로 서는 기본 매개 변수를 정의 합니다. 제네릭 프로시저를 호출 하는 경우 다른 차수 (차원 수)의 배열을 제공는 차수가 일치 하지 않으면 형식을 유추할 수 없습니다. 다음 코드는 호출을 보여 줍니다. 2 차원 배열은 1 차원 배열 예상 하는 프로시저에 전달 되는에 있습니다.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 모든 형식 인수를 생략 하는 것에 의해서만 형식 유추를 호출할 수 있습니다. 하나의 형식 인수를 제공 하는 경우 모두 제공 해야 합니다.  
  
 형식 유추가 제네릭 프로시저에만 지원 됩니다. 제네릭 클래스, 구조체, 인터페이스 또는 대리자에서 형식 유추를 호출할 수 없습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 제네릭 `Function` 프로시저 배열에서 특정 요소를 찾을 수 있습니다. 하나의 형식 매개 변수를 정의 하 고 하는 매개 변수 목록에 두 개의 매개 변수를 생성 하는 데 사용 합니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>설명  
 앞의 예제를 비교 하기 위해서는 `searchValue` 의 각 요소에 대해 `searchArray`합니다. 형식 매개 변수는이 기능을 보장 하기 위해 제한 `T` 구현 하는 <xref:System.IComparable%601> 인터페이스입니다. 코드를 사용 하 여는 <xref:System.IComparable%601.CompareTo%2A> 메서드 대신는 `=` 연산자에 대 한 형식 인수를 제공 하지 않을 수도 있기 때문에 `T` 지원는 `=` 연산자입니다.  
  
 테스트할 수 있습니다는 `findElement` 프로시저 다음 코드를 사용 합니다.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 에 대 한 호출이 이전 `MsgBox` "0", "1" 및 "-1"은 각각 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [방법: 제네릭 클래스 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [절차](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [프로시저 매개 변수 및 인수](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [형식 목록](../../../../visual-basic/language-reference/statements/type-list.md)  
 [매개 변수 목록](../../../../visual-basic/language-reference/statements/parameter-list.md)

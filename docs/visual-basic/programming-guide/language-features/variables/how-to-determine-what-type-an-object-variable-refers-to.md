---
title: '방법: 개체 변수가 참조하는 형식 확인(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 0dfd4ed87b65f536802ae71cbc3de41e1c4f83af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651316"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>방법: 개체 변수가 참조하는 형식 확인(Visual Basic)
개체 변수는 다른 위치에 저장 된 데이터에 대 한 포인터를 포함 합니다. 런타임 동안 해당 데이터의 형식은 변경할 수 있습니다. 언제 든 지 사용할 수 있습니다는 <xref:System.Type.GetTypeCode%2A> 현재 런타임 형식을 결정 하는 메서드 또는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 런타임 형식이 현재 했는지 확인 하 여 지정 된 형식의 호환 되는지 합니다.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>참조 형식을 결정 하려면 정확한 개체 변수에 현재  
  
1.  개체 변수를 호출 하는 <xref:System.Object.GetType%2A> 를 검색할 메서드는 <xref:System.Type?displayProperty=nameWithType> 개체입니다.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  에 <xref:System.Type?displayProperty=nameWithType> 클래스를 공유 하는 메서드를 호출 <xref:System.Type.GetTypeCode%2A> 검색 하는 <xref:System.TypeCode> 개체의 형식에 대 한 열거형 값입니다.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     테스트할 수 있습니다는 <xref:System.TypeCode> 같은 관심 있는 모든 열거형 멤버에 대 한 열거형 값 `Double`합니다.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>지정된 된 형식의와 호환 되 변수의 형식을 개체 여부를 확인 하려면  
  
-   사용 하 여는 `TypeOf` 연산자와 조합 하는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 사용 하 여 개체를 테스트 하는 `TypeOf`... `Is` 식입니다.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     `TypeOf`... `Is` 식 반환 `True` 개체의 런타임 형식이 호환 되는지 지정 된 형식을 사용 합니다.  
  
     호환성에 대 한 조건 클래스, 구조체 또는 인터페이스에 지정된 된 형식 인지에 따라 달라 집니다. 일반적으로 개체와 동일한 형식이에서 상속 하거나 지정 된 형식을 구현 하는 형식은 호환있지 않습니다. 자세한 내용은 참조 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 참고는 지정된 된 형식의 변수 또는 식이 될 수 없습니다. 클래스, 구조체 또는 인터페이스와 같은 정의 된 형식의 이름 이어야 합니다. 여기에 내장 형식이 같은 `Integer` 및 `String`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)

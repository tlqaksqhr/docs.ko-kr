---
title: "개체 변수 값 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: ff219571de9c76802d3f8d3046cf6b6f9d5be9d5
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-values-visual-basic"></a>개체 변수 값(Visual Basic)
변수는 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 모든 형식의 데이터를 참조할 수 있습니다. 에 저장 되는 값은 `Object` 변수는 특정 위치에 보관 메모리 변수 자체가 데이터에 대 한 포인터를 보유 합니다.  
  
## <a name="object-classifier-functions"></a>개체 분류자 함수  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 대 한 정보를 반환 하는 함수를 제공 하는 `Object` 변수가 참조 하는 다음 표에 나와 있는 것 처럼입니다.  
  
|함수|개체 변수가 참조 하는 경우 True를 반환 합니다.|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A>|단일 값이 아닌 값의 배열|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A>|A [Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md) 값 또는 날짜 및 시간 값으로 해석 될 수 있는 문자열|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|형식 <xref:System.DBNull>누락 되었거나 존재 하지 않는 데이터를 나타내는</xref:System.DBNull> 개체|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A>|파생 되는 예외 개체<xref:System.Exception></xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[아무 것도](../../../../visual-basic/language-reference/nothing.md), 개체가 변수에 현재 할당 되어, 즉|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|숫자 또는 문자열을 숫자로 해석 될 수 있는|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A>|참조 형식 (예: 문자열, 배열, 대리자 또는 클래스 형식)|  
  
 작업 또는 프로시저에 잘못 된 값을 제출 하지 않으려면 이러한 함수를 사용할 수 있습니다.  
  
## <a name="typeof-operator"></a>TypeOf 연산자  
 사용할 수도 있습니다는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 개체 변수는 특정 데이터 형식으로 현재 참조 하는지 여부를 확인 하려면. The `TypeOf`... `Is` 식이 `True` 피연산자의 런타임 형식에서 파생 되거나 지정 된 형식을 구현 하는 경우.  
  
 다음 예제에서는 `TypeOf` 값 및 참조 형식을 참조 하는 개체 변수입니다.  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 앞의 예제에는 다음 줄을 씁니다는 **디버그** 창:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 개체 변수 `num` 형식의 데이터를 가리키는 `Integer`, 및 `frm` <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form> 클래스의 개체 참조  
  
## <a name="object-arrays"></a>개체 배열  
 선언 하 고 배열을 사용 하 여 `Object` 변수입니다. 다양 한 데이터 형식 및 개체 클래스를 처리 해야 하는 경우에 유용 합니다. 배열의 모든 요소를 동일한 선언 된 데이터 형식이 있어야 합니다. 이 데이터 형식으로 선언 `Object` 클래스 배열에 다른 데이터 형식과 함께 인스턴스 및 개체를 저장할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [개체 변수 대입](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [방법: 개체의 현재 인스턴스 참조](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [방법: 개체 변수가 참조 하는 형식 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [방법: 두 개체가 관련이 있는지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [방법: 두 개체가 동일한 지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

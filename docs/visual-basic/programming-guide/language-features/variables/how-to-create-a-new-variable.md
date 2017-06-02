---
title: "방법: 새 변수 (Visual Basic) 만들기 | Microsoft 문서"
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
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2856fe19ddc48a14385aaae7b1c331fcb96c0554
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a>방법: 새 변수 만들기(Visual Basic)
사용 하 여 변수를 만들면는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
### <a name="to-create-a-new-variable"></a>새 변수를 만들려면  
  
1.  변수를 선언 하는 `Dim` 문입니다.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  와 같은 변수 특징에 대 한 사양이 포함 [개인](../../../../visual-basic/language-reference/modifiers/private.md), [정적](../../../../visual-basic/language-reference/modifiers/static.md), [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md), 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)합니다. 자세한 내용은 참조 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.  
  
    ```  
    Public Static newCustomer  
    ```  
  
     원하지 않는 `Dim` 키워드는 선언에 다른 키워드를 사용 하는 경우.  
  
3.  따라야 하는 변수 이름 사양에 따라 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 규칙 및 규칙을 따르십시오. 자세한 내용은 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  이름 뒤에 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 변수의 데이터 형식을 지정 하는 절.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     데이터 형식을 지정 하지 않으면 기본값 사용: `Object`합니다.  
  
5.  에 따라는 `As` 등호로 절 (`=`) 등호 변수의 초기 값을 따릅니다.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]실행 될 때마다 지정된 된 값은 변수에 할당 된 `Dim` 문. 초기 값을 지정 하지 않으면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수의 데이터 형식에 대 한 초기 기본값을 포함 하는 코드를 처음 실행 될 때 할당는 `Dim` 문입니다.  
  
     변수 참조 형식인 경우를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 의 키워드는 `As` 절. 사용 하지 않는 경우 `New`, 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [문](../../../../visual-basic/language-reference/statements/index.md)   
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)


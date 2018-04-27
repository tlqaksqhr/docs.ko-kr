---
title: '방법: 새 변수 만들기(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>방법: 새 변수 만들기(Visual Basic)
변수를 만들는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
### <a name="to-create-a-new-variable"></a>새 변수를 만들려면  
  
1.  변수를 선언 하는 `Dim` 문.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  같은 변수 특징에 대 한 사양이 포함 [개인](../../../../visual-basic/language-reference/modifiers/private.md), [정적](../../../../visual-basic/language-reference/modifiers/static.md), [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md), 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)합니다. 자세한 내용은 참조 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.  
  
    ```  
    Public Static newCustomer  
    ```  
  
     필요 하지 않습니다는 `Dim` 키워드는 선언에서 다른 키워드를 사용 하는 경우.  
  
3.  Visual Basic 규칙 및 규칙을 따라야 하는 변수 이름의 사양을 따릅니다. 자세한 내용은 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  이름 뒤에 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 절 변수의 데이터 형식을 지정 합니다.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     데이터 형식을 지정 하지 않으면 기본 사용: `Object`합니다.  
  
5.  에 따라는 `As` 등호로 절 (`=`) 등호 변수의 초기 값을 따릅니다.  
  
     Visual Basic 실행 될 때마다 변수에 지정된 된 값을 할당는 `Dim` 문. 초기 값을 지정 하지 않는 경우 Visual Basic 코드가 포함 된 처음 실행 하는 경우 변수의 데이터 형식에 대 한 기본 초기 값을 할당 하는 `Dim` 문.  
  
     변수 참조 형식인 경우를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드는 `As` 절. 사용 하지 않는 경우 `New`, 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [문](../../../../visual-basic/language-reference/statements/index.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)

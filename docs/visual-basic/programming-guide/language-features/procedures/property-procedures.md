---
title: "Property 프로시저 (Visual Basic) | Microsoft 문서"
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
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f21d4c7d9bd8f14bbe7284bc08399e7ba6b466c3
ms.lasthandoff: 03/13/2017

---
# <a name="property-procedures-visual-basic"></a>Property 프로시저(Visual Basic)
속성 프로시저는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 모듈, 클래스 또는 구조체에서 사용자 지정 속성을 조작 하는 문입니다. 속성 프로시저는 라고도 *속성 접근자*합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]다음 속성 프로시저를 제공합니다.  
  
-   A `Get` 프로시저 속성의 값을 반환 합니다. 식에서 속성에 액세스할 때 호출 됩니다.  
  
-   A `Set` 프로시저 개체 참조를 포함 하는 값으로 속성을 설정 합니다. 속성에 값을 할당할 때 호출 됩니다.  
  
 일반적으로 사용 하 여 쌍에 속성 프로시저를 정의 `Get` 및 `Set` 문, 있지만 속성이 읽기 전용 이면 두 프로시저 중 하나만 정의할 수 있습니다 ([Get 문을](../../../../visual-basic/language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([Set 문을](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 생략할 수는 `Get` 및 `Set` 프로시저는 자동 구현 속성을 사용 하는 경우. 자세한 내용은 참조 [자동으로 구현 된 속성](./auto-implemented-properties.md)합니다.  
  
 클래스, 구조체 및 모듈의 속성을 정의할 수 있습니다. 속성은 `Public` 어디에서 나 호출할 수 있습니다 즉 기본적으로 속성의 컨테이너에 액세스할 수 있는 응용 프로그램에 있습니다.  
  
 속성 및 변수는 비교를 참조 하십시오. [속성 간의 차이점 및 Visual Basic의 변수](./differences-between-properties-and-variables.md)합니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 속성 자체 내에 포함 하는 코드 블록을 정의한는 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문입니다. 이 블록 내의 각 속성 프로시저 선언 문 내에 포함 하는 내부 블록으로 나타납니다 (`Get` 또는 `Set`)와 일치 하는 `End` 선언 합니다.  
  
 속성 및 해당 프로시저를 선언 하기 위한 구문은 다음과 같습니다.  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 `Modifiers` 지정할 수 액세스 수준 및 오버 로드, 재정의 공유 및 숨김에 대 한 정보 뿐만 아니라 읽기 전용 또는 쓰기 전용 속성 인지 합니다. `AccessLevel` 에 `Get` 또는 `Set` 프로시저 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적으로 수준을 지정할 수 있습니다. 자세한 내용은 참조 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)합니다.  
  
### <a name="data-type"></a>데이터 형식  
 속성의 데이터 형식 및 보안 주체 액세스 수준에 정의 되어는 `Property` 속성 프로시저에 없는 문입니다. 속성에는 하나의 데이터 형식이 있을 수 있습니다. 저장 하는 속성을 정의할 수 없습니다 예를 들어 한 `Decimal` 하지만 검색는 `Double` 값입니다.  
  
### <a name="access-level"></a>액세스 수준  
 그러나 속성에 대 한 보안 주체 액세스 수준을 정의 하 고 속성 프로시저 중 하나에 대 한 액세스 수준을 더욱 제한할 수 있습니다. 예를 들어 정의할 수 있습니다는 `Public` 속성 다음 정의 `Private Set` 프로시저입니다. `Get` 프로시저 남아 `Public`합니다. 속성의 절차 중 하나에 액세스 수준을 변경할 수 및 보안 주체 액세스 수준 보다 더 제한적 으로만 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 액세스 수준이 혼합 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)합니다.  
  
## <a name="parameter-declaration"></a>매개 변수 선언  
 에 대 한와 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)는 전달 해야 한다는 점을 제외 하 고, `ByVal`합니다.  
  
 매개 변수 목록에서 각 매개 변수에 대 한 구문은 다음과 같습니다.  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 매개 변수는 선택 사항, 선언의 일부로 기본값을 제공 해야 합니다. 기본값을 지정 하기 위한 구문은 다음과 같습니다.  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>속성 값  
 에 `Get` 프로시저 반환 값 속성의 값으로 호출 식에 제공 됩니다.  
  
 에 `Set` 절차에서는 새 속성 값의 매개 변수로 전달 되는 `Set` 문. 매개 변수를 명시적으로 선언 하는 경우 동일한 데이터 형식의 속성으로 선언 해야 합니다. 매개 변수를 선언 하지 않으면 컴파일러는 암시적 매개 변수 사용 `Value` 속성에 할당할 새 값으로 나타내기.  
  
## <a name="calling-syntax"></a>호출 구문  
 속성을 참조 하 여 속성 프로시저를 암시적으로 호출 합니다. 사용 속성의 이름, 변수 이름을 사용 하는 동일한 방식으로 선택적 인수가 아닌 모든 인수에 대 한 값을 제공 해야 한다는 점을 제외 하면 하 고 인수 목록을 괄호로 묶어야 합니다. 없는 인수를 제공 하는 경우에 필요에 따라 괄호를 생략할 수 있습니다.  
  
 암시적으로 호출 하는 구문은 `Set` 절차는 다음과 같습니다.  
  
 `propertyname[(argumentlist)] = expression`  
  
 암시적으로 호출 하는 구문은 `Get` 절차는 다음과 같습니다.  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>선언 및 호출의 그림  
 다음과 같은 속성이 두 구성 요소 이름, 첫 번째 이름과 마지막 이름으로 전체 이름을 저장합니다. 호출 코드에서 읽을 때 `fullName`, `Get` 프로시저는 두 개의 구성 요소 이름을 결합을 전체 이름을 반환 합니다. 호출 코드에서 새 전체 이름을 할당 하는 경우는 `Set` 프로시저를 두 개의 구성 요소 이름으로 분해 하려고 합니다. 공간을 찾지 못하면, 모든 첫 번째 이름으로 저장 합니다.  
  
 [!code-vb[VbVbcnProcedures #&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 다음 예제에서는의 속성 프로시저를 호출 하는 일반적인 `fullName`합니다.  
  
 [!code-vb[VbVbcnProcedures #&9;](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Function 프로시저](./function-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)   
 [방법: 속성 만들기](./how-to-create-a-property.md)   
 [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)   
 [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md)   
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)   
 [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)

---
title: "Delegate 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 9ac9e28c82f8a6b5a9c1398961d831c956a649e0
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-statement"></a>Delegate 문
대리자를 선언 하는 데 사용 합니다. 대리자는 참조 형식을 참조 하는 `Shared` 형식 또는 개체의 인스턴스 메서드 메서드. 이 대리자 클래스의 인스턴스를 만드는 매개 변수 및 반환 형식을 일치 하는 모든 프로시저를 사용할 수 있습니다. 다음 대리자 인스턴스를 사용 하 여는 프로시저에 나중에 호출 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attrlist`|선택적 요소. 이 대리자에 적용 되는 특성의 목록입니다. 여러 특성은 쉼표로 구분합니다. 묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").|  
|`accessmodifier`|선택적 요소. 대리자에 액세스할 수 있는 코드를 지정 합니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [공용](../../../visual-basic/language-reference/modifiers/public.md)합니다. 대리자를 선언 하는 요소에 액세스할 수 있는 모든 코드를 액세스할 수 있습니다.<br />-   [보호 된](../../../visual-basic/language-reference/modifiers/protected.md)합니다. 대리자의 클래스 또는 파생된 클래스 내에서 코드에만 액세스할 수 있습니다.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)합니다. 동일한 어셈블리 내 코드만 대리자를 액세스할 수 있습니다.<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)합니다. 대리자를 선언 하는 요소 내의 코드에만 액세스할 수 있습니다.<br /><br /> 지정할 수 있습니다 `Protected Friend` 코드 대리자의 클래스나 파생된 클래스에서 동일한 어셈블리 내에서 액세스할 수 있도록 합니다.|  
|`Shadows`|선택적 요소. 이 대리자는 같은 이름의 프로그래밍 요소 또는 기본 클래스의 오버 로드 된 요소 집합을 다시 선언 하 고 숨기도록 나타냅니다. 모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다.<br /><br /> 섀도잉된 요소는 섀도잉 요소에 액세스할 수 없는 위치를 제외하고 해당 요소를 섀도잉하는 파생 클래스 내에서 사용할 수 없습니다. 예를 들어 하는 경우는 `Private` 요소 기본 클래스 요소를 액세스할 수 있는 권한이 없는 코드를 숨기면는 `Private` 요소 기본 클래스 요소에 대신 액세스 합니다.|  
|`Sub`|선택적 `Sub` 또는 `Function` 나타나야 합니다. 이 절차를 대리자로 선언 `Sub` 값을 반환 하지 않는 프로시저입니다.|  
|`Function`|선택적 `Sub` 또는 `Function` 나타나야 합니다. 이 절차를 대리자로 선언 `Function` 값을 반환 하는 절차입니다.|  
|`name`|필수 요소. 대리자 형식의 이름 표준 변수 명명 규칙을 따릅니다.|  
|`typeparamlist`|선택적 요소. 이 대리자에 대 한 형식 매개 변수 목록입니다. 여러 형식 매개 변수는 쉼표로 구분 됩니다. 필요에 따라 각 형식 매개 변수가 선언할 수 있습니다 variant를 사용 하 여 `In` 및 `Out` 제네릭 한정자입니다. 묶어야는 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md) 괄호 안에 사용 하 여 정의 하 고는 `Of` 키워드입니다.|  
|`parameterlist`|선택적 요소. 호출 될 때 프로시저에 전달 되는 매개 변수 목록입니다. 묶어야는 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md) 괄호 안에 있습니다.|  
|`type`|지정 하는 경우 필요한는 `Function` 프로시저입니다. 반환 값의 데이터 형식입니다.|  
  
## <a name="remarks"></a>주의  
 `Delegate` 문은 대리자 클래스의 매개 변수 및 반환 형식을 정의 합니다. 이 대리자 클래스의 인스턴스를 만드는 매개 변수 및 반환 형식에 일치 하는 모든 프로시저를 사용할 수 있습니다. 프로시저 수 나중에 호출 될 대리자 인스턴스를 통해 대리자의 호출 하 여 `Invoke` 메서드.  
  
 프로시저 내부가 아니라 네임 스페이스, 모듈, 클래스 또는 구조 수준에서 대리자를 선언할 수 있습니다.  
  
 각 대리자 클래스는 개체 메서드의 사양이 전달되는 생성자를 정의합니다. 대리자 생성자에 인수로 메서드 또는 람다 식에 대 한 참조 여야 합니다.  
  
 메서드에 대 한 참조를 지정 하려면 다음 구문을 사용 합니다.  
  
 `AddressOf` [`expression`.]`methodname`  
  
 컴파일 타임 형식은 `expression` 클래스 또는 서명이 대리자 클래스의 서명과 일치 하는 지정 된 이름의 메서드를 포함 하는 인터페이스의 이름 이어야 합니다. `methodname` 공유 메서드 또는 인스턴스 메서드 일 수 있습니다. `methodname` 은 반드시 기본 클래스의 메서드에 대 한 대리자를 만드는 경우에 합니다.  
  
 람다 식을 지정 하려면 다음 구문을 사용 합니다.  
  
 `Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`  
  
 함수의 서명이 대리자 형식의 일치 해야 합니다. 람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
 대리자에 대 한 자세한 내용은 참조 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Delegate` 두 숫자에 대해 작동 하 고 숫자를 반환 하는 것에 대 한 대리자를 선언 하는 문입니다. `DelegateTest` 메서드가 형식의 대리자의 인스턴스를 사용 하 고 사용 하 여 숫자의 쌍입니다.  
  
 [!code-vb[VbVbalrDelegates #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [공 분산과 반공 분산](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8)   
 [에서](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [아웃](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)

---
title: "Enum 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
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
ms.openlocfilehash: f9d3377300d30fd045c041367a528766fa9a8ed9
ms.lasthandoff: 03/13/2017

---
# <a name="enum-statement-visual-basic"></a>Enum 문(Visual Basic)
열거형을 선언하고 열거형의 멤버 값을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a>요소  
  
-   `attributelist`  
  
     선택적 요소. 이 열거형에 적용 되는 특성의 목록입니다. 묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
     <xref:System.FlagsAttribute>열거형의 인스턴스 값이 여러 열거형 멤버를 포함할 수 있으며 각 멤버는 열거형 값의 비트 필드를 나타내는 특성을 나타냅니다.</xref:System.FlagsAttribute>  
  
-   `accessmodifier`  
  
     선택적 요소. 이 열거형에 액세스할 수 있는 코드를 지정 합니다. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
     지정할 수 있습니다 `Protected``Friend` 열거형의 클래스나 파생된 클래스에서 동일한 어셈블리 내의 코드에서 액세스할 수 있도록 합니다.  
  
-   `Shadows`  
  
     선택적 요소. 이 열거형은 같은 이름의 프로그래밍 요소 또는 기본 클래스의 오버 로드 된 요소 집합 다시 선언 하 고 숨기도록 지정 합니다. 지정할 수 있습니다 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md) 열거형의 멤버 아니라 열거형 자체에 합니다.  
  
-   `enumerationname`  
  
     필수 요소. 열거형의 이름입니다. 유효한 이름에 대 한 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   `datatype`  
  
     선택적 요소. 열거형 및 모든 해당 멤버의 데이터 형식입니다.  
  
-   `memberlist`  
  
     필수 요소. 이 문에서 선언 되는 멤버 상수 목록입니다. 여러 멤버 개별 소스 코드 줄에 나타납니다.  
  
     각 `member` 다음 구문과 구성 요소는:`[<attribute list>] member name [ = initializer ]`  
  
    |파트|설명|  
    |---|---|  
    |`membername`|필수 요소. 이 멤버의 이름입니다.|  
    |`initializer`|선택적 요소. 컴파일 타임에 계산 되 고이 멤버에 할당 되는 식입니다.|  
  
-   `End` `Enum`  
  
     `Enum` 블록을 종료합니다.  
  
## <a name="remarks"></a>설명  
 논리적으로 서로 관련 된 변경 되지 않는 값의 집합에 있으면 정의할 수 있습니다 이러한 함께 열거형에서. 이 열거형과 해당 값 보다 쉽게 기억할 수 있는 해당 멤버에 대 한 의미 있는 이름을 제공 합니다. 다음 코드의 여러 위치에서 열거형 멤버를 사용할 수 있습니다.  
  
 열거형을 사용할 때의 이점은 다음과 같습니다.  
  
-   숫자를 잘못 입력 하 여 발생 하는 오류를 줄일 수 있습니다.  
  
-   나중에 값을 변경 하려면 쉽게 있습니다.  
  
-   에서는 거의 오류를 도입 될 것으로 코드를 쉽게 읽을 수 있습니다.  
  
-   다음 버전과 호환성을 확인합니다. 열거형을 사용 하는 경우이 코드는 나중에 멤버 이름에 해당 하는 값 변경 되 면 실패할 가능성이 적습니다.  
  
 열거형에는 이름, 내부 데이터 형식 및 멤버 집합을 합니다. 각 멤버는 상수를 나타냅니다.  
  
 클래스, 구조체, 모듈 또는 다른 프로시저 외부 인터페이스 수준에서 선언 하는 열거형은는 *멤버 열거형*합니다. 클래스, 구조체, 모듈 또는 변수를 선언 하는 인터페이스의 멤버 임  
  
 멤버 열거형 어디 액세스할 수에서 해당 클래스, 구조체, 모듈 또는 인터페이스 내에서. 코드는 클래스 외부 또는 모듈 멤버 열거형의 이름을 정해야 해당 클래스, 구조체, 모듈의 이름입니다. 정규화 된 이름을 추가 하 여 사용의 필요성을 방지할 수는 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 문을 소스 파일에 있습니다.  
  
 클래스, 구조체, 모듈 또는 인터페이스를 외부 네임 스페이스 수준에서 선언 되는 열거형은 표시 되는 네임 스페이스의 멤버입니다.  
  
 *선언 컨텍스트* 열거형 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 프로시저일 수는 없습니다. 자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)합니다.  
  
 특성 적용을 전체적으로 열거형에 있지만 해당 멤버에 개별적으로 합니다. 어셈블리의 메타 데이터에 정보를 적용 하는 특성입니다.  
  
## <a name="data-type"></a>데이터 형식  
 `Enum` 문은 데이터 형식의 열거형을 선언할 수 있습니다. 각 멤버에는 열거형의 데이터 형식을 사용 합니다. You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.  
  
 지정 하지 않으면 `datatype` 열거형에 대 한 각 멤버는 형식의 데이터는 해당 `initializer`합니다. 모두 지정 하면 `datatype` 및 `initializer`의 데이터 형식이 `initializer` 변환할 수 있어야 `datatype`합니다. 모두 `datatype` 나 `initializer` 가 있으면 데이터 형식의 기본값으로 `Integer`합니다.  
  
## <a name="initializing-members"></a>멤버 초기화  
 `Enum` 문을에서 선택한 멤버의 콘텐츠를 초기화할 수 `memberlist`합니다. 사용 하면 `initializer` 멤버에 할당 하는 식을 제공 합니다.  
  
 지정 하지 않으면 `initializer` 멤버에 대 한 Visual Basic 초기화을&0; (첫 번째 경우 `member` 에서 `memberlist`), 또는 바로 앞에 보다 하나 큰 값으로 `member`합니다.  
  
 각 지정 된 식은 `initializer` 리터럴, 이미 정의 되어 있는 다른 상수 이미 정의 되어 있는,이 열거형의 이전 멤버를 포함 하 여 열거형 멤버의 조합일 수 있습니다. 이러한 요소를 결합 하 여 산술 및 논리 연산자를 사용할 수 있습니다.  
  
 변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다. 그러나와 같은 변환 키워드를 사용할 수는 `CByte` 및 `CShort`합니다. 사용할 수도 있습니다 `AscW` 상수와 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 계산 될 수 있으므로 합니다.  
  
 열거형 부동 소수점 값을 가질 수 없습니다. 멤버는 부동 소수점 값에 할당 된 경우 및 `Option Strict` 컴파일러 오류가 발생 하는 on으로 설정 됩니다. 경우 `Option Strict` 가 해제를 자동으로 변환 된 값은 `Enum` 유형입니다.  
  
 기본 데이터 형식에 대 한 허용 범위를 초과 하는 멤버의 값 또는 멤버를 기본 데이터 형식에서 허용 되는 최대값을 초기화 하는 경우 컴파일러는 오류를 보고 합니다.  
  
## <a name="modifiers"></a>한정자  
 클래스, 구조체, 모듈 및 인터페이스 멤버 열거형은 기본적으로 공용 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다. Namespace 멤버 열거는 기본적으로 friend 액세스 합니다. 공용, 아니라 private 또는 protected 액세스 수준을 조정할 수 있습니다. 자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 모든 열거형 멤버는 공용 액세스 있고 등에 액세스 한정자를 사용할 수 없습니다. 그러나 경우 열거형 자체 보다 제한 된 액세스 수준이 지정 된 열거형의 액세스 수준이 우선 합니다.  
  
 기본적으로 모든 열거형 형식이 며 해당 필드는 상수입니다. 따라서는 `Shared`, `Static`, 및 `ReadOnly` 열거형 또는 해당 멤버를 선언 하는 경우에 키워드를 사용할 수 없습니다.  
  
## <a name="assigning-multiple-values"></a>여러 값을 할당합니다.  
 열거형은 일반적으로 상호 배타적인 값을 나타냅니다. 포함 하 여는 <xref:System.FlagsAttribute>특성에 `Enum` 선언 대신 값을 할당할 수 여러 열거형의 인스턴스로.</xref:System.FlagsAttribute> <xref:System.FlagsAttribute>특성 열거형 비트 필드 즉, 플래그 집합으로 처리 하도록 지정 합니다.</xref:System.FlagsAttribute> 이 라고 *비트* 열거형입니다.  
  
 사용 하 여 열거형을 선언할 때는 <xref:System.FlagsAttribute>특성 좋습니다 값에 있는 2, 1, 2, 4, 8, 16, 및 등의 거듭제곱이 사용 합니다.</xref:System.FlagsAttribute> 값이 0 인 멤버의 이름을 "None" 되도록 하는 것이 좋습니다. 추가 지침 <xref:System.FlagsAttribute>및 <xref:System.Enum>.</xref:System.Enum> </xref:System.FlagsAttribute> 를 참조 하십시오.  
  
## <a name="example"></a>예제  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `Enum` 문입니다. 멤버 라고는 `EggSizeEnum.Medium`, 아니라 `Medium`합니다.  
  
 [!code-vb[VbEnumsTask #&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서 메서드는 외부는 `Egg` 클래스입니다. 따라서 `EggSizeEnum` 으로 정규화 된 `Egg.EggSizeEnum`합니다.  
  
 [!code-vb[VbEnumsTask #&42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Enum` 명명 된 상수 값을 관련된 집합을 정의 합니다. 이 경우 값은 색 데이터베이스에 대 한 데이터 입력 폼을 설계할 수 있습니다.  
  
 [!code-vb[VbEnumsTask #&30;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예에서는 양수 및 음수를 포함 하는 값을 보여 줍니다.  
  
 [!code-vb[VbEnumsTask #&31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `As` 절 지정을 사용 하는 `datatype` 열거형의 합니다.  
  
 [!code-vb[VbEnumsTask #&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 열거형을 비트를 사용 하는 방법을 보여 줍니다. 여러 값의 비트 열거형 인스턴스에 할당할 수 있습니다. `Enum` 선언는 <xref:System.FlagsAttribute>열거형 플래그 집합으로 처리할 수 있음을 나타내는 특성입니다.</xref:System.FlagsAttribute>  
  
 [!code-vb[VbEnumsTask #&61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 열거형을 반복합니다. 사용 하 여는 <xref:System.Enum.GetNames%2A>열거형의 멤버 이름의 배열을 검색 하는 메서드 및 <xref:System.Enum.GetValues%2A>멤버 값의 배열을 검색 하.</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A>  
  
 [!code-vb[VbEnumsTask #&51;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Enum></xref:System.Enum>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)

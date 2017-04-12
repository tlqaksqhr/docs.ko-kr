---
title: "Dim 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Dim
- Dim
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, in Dim statement
- Dim statement
- fixed-length strings, declaring
- variables [Visual Basic], declaring
- WithEvents keyword, Dim statement
- dynamic arrays, Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields, as member variables
- declarations, dynamic arrays
- member variables
- default values
- data types [Visual Basic], assigning
- braces {}
- As keyword, in Dim statement
- arrays [Visual Basic], declaring
- New keyword, Dim statement
- To keyword, in Dim statement
- storage, allocating
- local variables
- declaration statements
- Dim statement, syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
caps.latest.revision: 72
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
ms.openlocfilehash: 00d5d0e83a88a0c7ac3ade92d09c584fce64fcd8
ms.lasthandoff: 03/13/2017

---
# <a name="dim-statement-visual-basic"></a>Dim 문(Visual Basic)
선언 하 고 하나 이상의 변수에 대 한 저장 공간을 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>요소  
  
-   `attributelist`  
  
     선택적 요소. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
-   `accessmodifier`  
  
     선택적 요소. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     참조 [액세스 수준 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
-   `Shared`  
  
     선택적 요소. 참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.  
  
-   `Shadows`  
  
     선택적 요소. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
-   `Static`  
  
     선택적 요소. 참조 [정적](../../../visual-basic/language-reference/modifiers/static.md)합니다.  
  
-   `ReadOnly`  
  
     선택적 요소. 참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
-   `WithEvents`  
  
     선택적 요소. 이 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하는 개체 변수를 지정 합니다. 참조 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)합니다.  
  
-   `variablelist`  
  
     필수 요소. 이 문에서 선언 되는 변수의 목록입니다.  
  
     `variable [ , variable ... ]`  
  
     각 `variable`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |파트|설명|  
    |---|---|  
    |`variablename`|필수 요소. 변수의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
    |`boundslist`|선택적 요소. 배열 변수의 각 차원 범위 목록입니다.|  
    |`New`|선택적 요소. 클래스의 새 인스턴스를 만듭니다 때는 `Dim` 문 실행 합니다.|  
    |`datatype`|선택적 요소. 변수의 데이터 형식입니다.|  
    |`With`|선택적 요소. 개체 이니셜라이저 목록을 소개합니다.|  
    |`propertyname`|선택적 요소. 클래스에서 속성의 이름의 인스턴스로 설정 됩니다.|  
    |`propinitializer`|후 필요한 `propertyname` =. 계산 되 고 속성 이름에 할당 하는 식입니다.|  
    |`initializer`|선택적 if `New` 지정 되지 않았습니다. 계산 되 고 만들어질 때 변수에 할당 되는 식입니다.|  
  
## <a name="remarks"></a>설명  
 Visual Basic 컴파일러를 사용 하는 `Dim` 문에를 변수의 데이터 형식 및 변수를 액세스할 수 있는 코드 등의 기타 정보를 확인 합니다. 다음 예제에서는 선언 보유 하는 변수는 `Integer` 값입니다.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 사용 된 참조 형식에 대 한는 `New` 데이터 형식에 따라 클래스의 새 인스턴스를 만들거나 구조체 키워드를 지정 합니다. 사용 하는 경우 `New`, 이니셜라이저 식 사용 하지 마십시오. 대신, 변수 만들 클래스의 생성자에 필요한 경우 인수를 제공 합니다.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 프로시저, 블록, 클래스, 구조체 또는 모듈에서 변수를 선언할 수 있습니다. 소스 파일, 네임 스페이스 또는 인터페이스에서 변수를 선언할 수 없습니다. 자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)합니다.  
  
 모든 프로시저 외부의 모듈 수준에서 선언 된 변수는 한 *멤버 변수* 또는 *필드*합니다. 멤버 변수가 클래스, 구조체 또는 모듈의 전체 범위에 있습니다. 프로시저 수준에서 선언 된 변수는 한 *지역 변수*합니다. 해당 프로시저 또는 블록 내 에서만 범위에는 지역 변수가 있습니다.  
  
 다음과 같은 액세스 한정자는 프로시저 외부 변수를 선언 하는 데 사용 됩니다: `Public`, `Protected`, `Friend`, `Protected Friend`, 및 `Private`합니다. 자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `Dim` 키워드는 선택 사항 및 다음 한정자를 지정 하는 경우 일반적으로 생략: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, 또는 `WithEvents`합니다.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 경우 `Option Explicit` 는 컴파일러를 사용 하 여 모든 변수에 대 한 선언이 필요 on (기본값). 자세한 내용은 참조 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)합니다.  
  
## <a name="specifying-an-initial-value"></a>초기 값을 지정  
 생성 될 때 값을 변수에 할당할 수 있습니다. 값 형식에 대해 사용 하는 *이니셜라이저* 변수에 할당 하는 식을 제공 합니다. 컴파일 타임에 계산 될 수 있는 상수 식은 되어야 합니다.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 이니셜라이저를 지정 하 고 데이터 형식에 지정 하지 않은 경우는 `As` 절 *형식 유추* 이니셜라이저의 데이터 형식을 유추 하는 데 사용 됩니다. 다음 예제에서 모두 `num1` 및 `num2` 는 정수로 강력한 형식입니다. 두 번째 선언에서 3 값에서 형식을 유추 하는 형식 유추 합니다.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 형식 유추는 프로시저 수준에서 적용 됩니다. 클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에 적용 되지 않습니다. 형식 유추 하는 방법에 대 한 자세한 내용은 참조 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [로컬 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.  
  
 데이터 형식 또는 이니셜라이저를 지정 하지 않으면 어떻게 하는 방법에 대 한 정보를 참조 하십시오. [기본 데이터 형식 및 값](../../../visual-basic/language-reference/statements/dim-statement.md#default) 이 항목의 뒷부분에 나오는 합니다.  
  
 사용할 수는 *개체 이니셜라이저* 를 명명 된 형식과 익명 형식의 인스턴스를 선언 합니다. 인스턴스를 만들고 다음 코드는 `Student` 클래스 및 개체 이니셜라이저를 사용 하 여 속성을 초기화 합니다.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 개체 이니셜라이저에 대 한 자세한 내용은 참조 [하는 방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), 및 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.  
  
## <a name="declaring-multiple-variables"></a>여러 변수를 선언합니다.  
 괄호를 사용 하 여 각각에 대 한, 각 배열 이름 다음에 변수 이름을 지정 하나의 선언문에서 여러 변수를 선언할 수 있습니다. 여러 변수는 쉼표로 구분됩니다.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 하나 이상의 변수를 선언 하는 경우 `As` 절 변수의 해당 그룹에 대 한 이니셜라이저를 제공할 수 없습니다.  
  
 별도 사용 하 여 다른 데이터 형식을 다른 변수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대 한 절. 각 변수는 첫 번째 지정 된 데이터 형식과 `As` 절 다음에 오는 해당 `variablename` 부분입니다.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>배열  
 보유 하는 변수를 선언할 수는 *배열*, 여러 값을 보유할 수 있는 합니다. 배열을 포함 하는 변수를 지정 하려면에 따라 해당 `variablename` 괄호와 함께 즉시 합니다. 배열에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
 하 한과 상한을 배열에 있는 각 차원의 지정할 수 있습니다. 이렇게 하려면 다음을 포함 한 `boundslist` 괄호 안에 있습니다. 각 차원에 대해는 `boundslist` 상한 및 하 한 필요에 따라 지정 합니다. 하 한은 항상&0; 있는지 여부를 지정 합니다. 각 인덱스는&0;의 상한 값 사이 달라질 수 있습니다.  
  
 다음 두 문은 동일합니다. 각 문은 21 배열을 `Integer` 요소입니다. 배열에 액세스할 때 인덱스는 0부터 20 까지의 달라질 수 있습니다.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 다음 문은 선언 형식의&2; 차원 배열을 `Double`합니다. 배열에 각각 6 열 (5 + 1)의 4 행 (3 + 1). 참고 상한을 차원의 길이가 아닌 인덱스에 대 한 가능한 가장 큰 값을 나타냅니다. 차원 길이가&1;을 더한 상한을 지정 합니다.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 배열 32 차원 1에서 할 수 있습니다.  
  
 모든 범위를 배열 선언에서 비워 둘 수 있습니다. 이 작업을 수행 하는 경우 배열에을 지정 하면 차원의 수 있지만 초기화 되지 않았습니다. 값을가지고 `Nothing` 초기화 하기 전까지 배열 요소의 일부입니다. `Dim` 문에 차원이 없습니다. 또는 모든 차원에 대해 범위를 지정 합니다.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 배열에 둘 이상의 차원, 차원 수를 나타내는 괄호 사이 쉼표를 포함 해야 합니다.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 선언할 수는 *길이가&0; 인 배열을* -1로 배열의 차원 중 하나를 선언 합니다. 길이가&0; 인 배열을 포함 하는 변수는 값이 없는 `Nothing`합니다. 길이가&0; 인 배열이 특정 공용 언어 런타임 함수에 필요 합니다. 이러한 배열에 액세스 하려고 하면 런타임 예외가 발생 합니다. 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
 배열 리터럴을 사용 하 여 배열의 값을 초기화할 수 있습니다. 이 위해 초기화 값을 중괄호를 묶습니다 (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 다차원 배열에 대 한 별도 각 차원에 대 한 초기화는 중괄호로 외부 차원에 있습니다. 요소는 행 중심 순서로 지정 됩니다.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 배열 리터럴에 대 한 자세한 내용은 참조 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
##  <a name="default"></a>기본 데이터 형식 및 값  
 다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.  
  
|데이터 형식 지정 여부|이니셜라이저 지정 여부|예제|결과|  
|---|---|---|---|  
|아니요|아니요|`Dim qty`|경우 [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) 는 설정 된 변수 off (기본값), `Nothing`합니다.<br /><br /> `Option Strict`가 on이면 컴파일 타임 오류가 발생합니다.|  
|아니요|예|`Dim qty = 5`|경우 [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) 가 on (기본값)는 변수 데이터 형식을 이니셜라이저의 합니다. 참조 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.<br /><br /> `Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 타임 오류가 발생합니다.|  
|예|아니요|`Dim qty As Integer`|변수는 데이터 형식의 기본값으로 초기화됩니다. 이 섹션 뒷부분에 나오는 표를 참조 하십시오.|  
|예|예|`Dim qty  As Integer = 5`|이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.|  
  
 데이터 형식을 지정 하지만 이니셜라이저를 지정 하지 않는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수 데이터 형식에 대 한 기본 값으로 초기화 합니다. 다음 표에서 기본 초기화 값을 보여 줍니다.  
  
|데이터 형식|기본값|  
|---|---|  
|모든 숫자 형식 (포함 하 여 `Byte` 및 `SByte`)|0|  
|`Char`|이진 0|  
|모든 참조 형식 (포함 하 여 `Object`, `String`, 및 모든 배열)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|1 년 1 월 1의 오전 12시 (01/01/0001 12시: 00 AM)|  
  
 구조체의 각 요소는 마치는 별도 변수인 것 처럼 초기화 됩니다. 배열의 길이 선언 하지만 해당 요소를 초기화 하지 않는 경우 각 요소는 마치는 별도 변수인 것 처럼 초기화 됩니다.  
  
## <a name="static-local-variable-lifetime"></a>정적 지역 변수 수명  
 A `Static` 로컬 변수가 수명 선언 된 프로시저의 보다 깁니다. 변수의 수명은 인지와 프로시저 선언 된 위치에 따라 달라 집니다 `Shared`합니다.  
  
|프로시저 선언|변수 초기화|기존 변수 중지|  
|---|---|---|  
|모듈에서|처음에 프로시저 호출 될 때|프로그램 실행을 중지 하는 경우|  
|프로시저는 클래스 또는 구조체에는`Shared`|처음으로 프로시저를 호출할 특정 인스턴스 또는 클래스 또는 구조체 자체|프로그램 실행을 중지 하는 경우|  
|클래스 또는 구조체 프로시저 되지 않으므로`Shared`|특정 인스턴스에서 프로시저가 호출 된 처음으로|가비지 수집 (GC)에 인스턴스가 해제 되는 경우|  
  
## <a name="attributes-and-modifiers"></a>특성 및 한정자  
 지역 변수가 아닌 멤버 변수에만 특성을 적용할 수 있습니다. 특성은 어셈블리의 메타 데이터에 대 한 정보는 의미가 없습니다 지역 변수 같은 임시 저장소에 있습니다.  
  
 모듈 수준에서 사용할 수 없습니다는 `Static` 한정자를 멤버 변수를 선언 합니다. 프로시저 수준에서 사용할 수 없습니다 `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, 또는 액세스 한정자를 지역 변수를 선언 합니다.  
  
 변수를 제공 하 여 액세스할 수 있는 코드를 지정할 수는 `accessmodifier`합니다. 클래스 및 모듈 멤버 변수 (외부 프로시저)는 기본적으로 개인 액세스 및 구조 멤버 변수는 기본적으로 공용 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다. 프로시저의 경우) (내 지역 변수에 액세스 한정자를 사용할 수 없습니다.  
  
 지정할 수 있습니다 `WithEvents` 만 멤버 변수 아니라에 프로시저 내의 지역 변수입니다. 지정 하는 경우 `WithEvents`, 변수의 데이터 형식을 특정 클래스 형식에 해제 해야 `Object`합니다. 배열을 선언할 수 없습니다 `WithEvents`합니다. 이벤트에 대 한 자세한 내용은 참조 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)합니다.  
  
> [!NOTE]
>  코드 클래스 외부에서는 또는 모듈 멤버 변수의 이름을 정해야 해당 클래스, 구조체, 모듈의 이름입니다. 해당 프로시저 또는 블록 내에서 지역 변수를 참조할 수 없습니다 프로시저 또는 블록 외부에 있는 코드입니다.  
  
## <a name="releasing-managed-resources"></a>관리 되는 리소스를 해제합니다.  
 .NET Framework 가비지 수집기가 사용자의 추가 코딩 없이도 관리 되는 리소스를 삭제 합니다. 그러나 가비지 수집기가 대기 하는 대신 관리 되는 리소스의 처리를 강제로 수 있습니다.  
  
 클래스에는 특히 중요 하 고 부족 한 리소스 (예: 데이터베이스 연결 또는 파일 핸들)을 갖는 경우는 더 이상 사용에서 하는 클래스 인스턴스를 정리 하는 다음 가비지 수집 될 때까지 대기 하지 않을 수 없습니다. 클래스를 구현할 수는 <xref:System.IDisposable>가비지 수집을 하기 전에 리소스를 해제 하는 방법을 제공 하는 인터페이스입니다.</xref:System.IDisposable> 해당 인터페이스를 구현 하는 클래스를 노출 한 `Dispose` 강제로 즉시 출시 될 중요 한 리소스를 호출할 수 있는 메서드.  
  
 `Using` 리소스 확보, 문 집합을 실행 한 다음 리소스를 삭제 하는 프로세스를 자동화 하는 문입니다. 그러나 리소스를 구현 해야는 <xref:System.IDisposable>인터페이스.</xref:System.IDisposable> 자세한 내용은 참조 [문을 사용 하 여](../../../visual-basic/language-reference/statements/using-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 변수를 사용 하 여 선언 된 `Dim` 다양 한 옵션을 사용 하 여 문을 합니다.  
  
 [!code-vb[VbVbalrStatements #&141;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 1에서 30 사이의 소수를 나열 합니다. 지역 변수의 범위는 코드 주석에 설명 되어 있습니다.  
  
 [!code-vb[VbVbalrStatements #&142;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `speedValue` 변수는 클래스 수준에서 선언 됩니다. `Private` 키워드는 변수를 선언 하는 데 사용 됩니다. 모든 프로시저에서 변수를 액세스할 수는 `Car` 클래스입니다.  
  
 [!code-vb[VbVbalrStatements #&144;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements #&145;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)   
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [방법: 개체 이니셜라이저를 사용 하 여 개체 선언](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)   
 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

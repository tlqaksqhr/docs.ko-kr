---
title: Namespace 문
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 15d8d8185d895502df594bbd931443af604bef67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604871"
---
# <a name="namespace-statement"></a>Namespace 문
네임 스페이스의 이름을 선언 하 고 해당 네임 스페이스에서 컴파일되도록 선언 뒤에 오는 소스 코드.  
  
## <a name="syntax"></a>구문  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>요소  
 Global  
 선택 사항입니다. 프로젝트의 루트 네임 스페이스에서 네임 스페이스를 정의할 수 있습니다. 참조 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.  
  
 `name`  
 필수. 네임 스페이스를 식별 하는 고유 이름입니다. 유효한 Visual Basic 식별자 여야 합니다. 자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 `componenttypes`  
 선택 사항입니다. 네임 스페이스를 구성 하는 요소입니다. 이러한 포함 되지만 열거형, 구조체, 인터페이스, 클래스, 모듈, 대리자 및 다른 네임 스페이스에 제한 되지 않습니다.  
  
 `End Namespace`  
 종료는 `Namespace` 블록입니다.  
  
## <a name="remarks"></a>설명  
 네임 스페이스는 조직 시스템으로 사용 됩니다. 분류 및 다른 프로그램 및 응용 프로그램에 노출 되는 프로그래밍 요소를 표시 하는 방법을 제공 합니다. 네임 스페이스 하지 않습니다는 *형식* 의미는 클래스 또는 구조체에서-네임 스페이스의 데이터 형식을 갖도록 프로그래밍 요소를 선언할 수 없습니다.  
  
 다음에 선언 된 모든 프로그래밍 요소는 `Namespace` 문을 해당 네임 스페이스에 속합니다. Visual Basic를 컴파일하여 요소 마지막 선언 된 네임 스페이스 중 하나에 도달할 때까지 계속는 `End Namespace` 문 또는 다른 `Namespace` 문.  
  
 네임 스페이스는 이미 정의 된 경우, 프로젝트 외부도 프로그래밍 요소를 추가할 수 있습니다. 이 위해 사용 하는 `Namespace` 문을 해당 네임 스페이스에 요소를 컴파일하는 데 Visual basic입니다.  
  
 사용할 수는 `Namespace` 파일이 나 네임 스페이스 수준 에서만 문입니다. 즉,는 *선언 컨텍스트* 네임 스페이스는 소스 파일 또는 다른 네임 스페이스 이어야 하며 클래스, 구조체, 모듈, 인터페이스 또는 프로시저 일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 내에서 다른 한 네임 스페이스를 선언할 수 있습니다. 를 선언할 수 있지만 기억 하는 다른 코드에서 가장 안쪽의 네임 스페이스에서 선언 된 요소에 액세스 하는 경우 사용 해야 중첩 계층의 모든 네임 스페이스 이름을 포함 하는 한정 문자열의 중첩 수준에는 엄격한 제한은 없습니다.  
  
## <a name="access-level"></a>액세스 수준  
 네임 스페이스는 것 처럼 처리 되는 `Public` 액세스 수준입니다. 네임 스페이스는 같은 프로젝트의 코드, 프로젝트를 참조 하는 다른 프로젝트 및 프로젝트에서 빌드된 어셈블리에서에 액세스할 수 있습니다.  
  
 네임 스페이스에 있지만 다른 요소에 포함 되지 않은 의미 하는 네임 스페이스 수준에서 선언 된 프로그래밍 요소 점이 `Public` 또는 `Friend` 액세스 합니다. 지정 하지 않으면 이러한 액세스 수준을 요소가 사용 하 여 `Friend` 기본적으로 합니다. 클래스, 구조체, 모듈, 인터페이스, 열거형 및 대리자를 포함 하는 요소 네임 스페이스 수준에서 선언할 수 있습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
## <a name="root-namespace"></a>루트 Namespace  
 프로젝트에서 모든 네임 스페이스 이름을 기반으로 한 *루트 네임 스페이스*합니다. Visual Studio는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다. 예를 들어 프로젝트 이름이 `Payroll`이면 해당 프로그래밍 요소는 해당 네임스페이스 `Payroll`에 속합니다. 선언 하는 경우 `Namespace funding`, 해당 네임 스페이스의 전체 이름은 `Payroll.funding`합니다.  
  
 기존 네임 스페이스를 지정 하려는 경우는 `Namespace` 문, 예: 제네릭 목록 클래스 예제에서 루트 네임 스페이스는 null 값으로 설정할 수 있습니다. 이 작업을 수행 하려면 **프로젝트 속성** 에서 **프로젝트** 메뉴와 선택을 취소 합니다는 **루트 네임 스페이스** 항목 상자가 비어 있도록 합니다. 이 제네릭 목록 클래스 예제에서 수행 하지 않은 경우 Visual Basic 컴파일러가 수행 `System.Collections.Generic` 프로젝트 내에서 새 네임 스페이스로 `Payroll`를의 전체 이름으로 `Payroll.System.Collections.Generic`합니다.  
  
 사용할 수 있습니다는 `Global` 프로젝트 외부에 정의 된 네임 스페이스의 요소를 참조 하는 키워드입니다. 이렇게 하면 프로젝트 이름을 루트 네임 스페이스도 유지할 수 있습니다. 이렇게 하면 실수로 기존 네임 스페이스와 함께 프로그래밍 요소를 병합 합니다. 자세한 내용은에서 "전역 키워드에 정규화 된 이름" 섹션을 참조 하십시오. [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.  
  
 `Global` 키워드 Namespace 문에서 사용할 수 있습니다. 이렇게 하면 프로젝트의 루트 네임스페이스에서 네임스페이스를 정의할 수 있습니다. 자세한 내용은의 "Namespace 문을에서 글로벌 키워드" 섹션을 참조 하십시오. [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.  
  
 **문제를 해결 합니다.** 예기치 않은 네임 스페이스 이름 연결할 루트 네임 스페이스 발생할 수 있습니다. 프로젝트 외부에 정의 된 네임 스페이스 참조를 만드는 경우 Visual Basic 컴파일러는 해당 루트 네임 스페이스에 중첩 된 네임 스페이스도 해석할 수 있습니다. 이 경우 컴파일러는 외부 네임 스페이스에 이미 정의 되어 있는 형식이 인식 하지 못합니다. 이 방지 하려면 루트 네임 스페이스 "루트 Namespace"에 설명 된 대로 null 값으로 설정 하거나 사용 된 `Global` 요소 외부 네임 스페이스에 액세스 하는 키워드입니다.  
  
## <a name="attributes-and-modifiers"></a>특성 및 한정자  
 네임 스페이스에 특성을 적용할 수 없습니다. 특성은 네임 스페이스와 같은 소스 분류자에 의미가 없습니다 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.  
  
 네임 스페이스에 대 한 액세스 또는 프로시저 한정자 또는 다른 한정자를 적용할 수 없습니다. 형식이 없기 때문에 이러한 한정자는 의미가 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 다른 중첩 된 두 개의 네임 스페이스를 선언 합니다.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 줄에 여러 개의 중첩 된 네임 스페이스를 선언 하 고 앞의 예와 동일 합니다.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 앞의 예제에 정의 된 클래스에 액세스 합니다.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 제네릭 목록 클래스의 기본 구조를 정의 하 고에 추가 된 <xref:System.Collections.Generic?displayProperty=nameWithType> 네임 스페이스입니다.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>참고 항목  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)

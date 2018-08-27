---
title: Imports 문-.NET Namespace 및 형식 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 0211438e8b4c02fead910dd7a32e0df9ed73ddc5
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925600"
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports 문(.NET 네임스페이스 및 형식)
사용 하도록 설정에는 네임 스페이스 한정자 없이 참조 되는 이름을 입력 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`aliasname`|선택 사항입니다. *가져오기 별칭* 코드를 참조할 수 있는 이름 또는 `namespace` 정규화 문자열 대신 합니다. 참조 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`namespace`|필수. 가져올 네임 스페이스의 정규화 된 이름입니다. 중첩 될 수 있습니다 문자열 네임 스페이스의 모든 수준에 있습니다.|  
|`element`|선택 사항입니다. 네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다. 모든 컨테이너 요소를 수 있습니다.|  
  
## <a name="remarks"></a>설명  
 `Imports` 문을 직접 참조할 수 지정된 된 네임 스페이스에 포함 된 형식을 사용 하도록 설정 합니다.  
  
 단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다. 각 중첩 된 네임 스페이스는 마침표로 다음 더 높은 수준의 네임 스페이스에서 (`.`) 다음 예제와 같이, 합니다.  
  
 `Imports System.Collections.Generic`  
  
 각 소스 파일에는 개수에 관계 없이 포함 될 수 있습니다 `Imports` 문입니다. 이러한 옵션 선언 같은 따라야 합니다 `Option Strict` 문 및 이러한 앞에 야 프로그래밍 요소 선언에 같은 `Module` 또는 `Class` 문입니다.  
  
 사용할 수 있습니다 `Imports` 파일 수준 에서만. 즉, 가져오기 선언 컨텍스트 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다.  
  
 `Imports` 문을 해도 다른 프로젝트와 어셈블리의 요소를 프로젝트에 사용할 수 있습니다. 가져오기 대 한 참조를 설정 하는 위치를 차지 하지 않습니다. 만 이미 프로젝트에 사용할 수 있는 이름을 한정할 필요가 없습니다. 자세한 내용은 "를 포함 하는 요소 가져오기"를 참조 하세요 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
> [!NOTE]
>  암시적 정의할 수 있습니다 `Imports` 문에서 사용 하 여 합니다 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다. 자세한 내용은 참조 하세요. [방법: 가져온 네임 스페이스 (Visual Basic)를 제거 또는 추가](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)합니다.  
  
## <a name="import-aliases"></a>Import 별칭  
 *가져오기 별칭* 네임 스페이스 또는 형식에 대 한 별칭을 정의 합니다. Import 별칭은 하나 이상의 네임 스페이스에 선언 되어 있는 동일한 이름의 항목을 사용 하는 경우에 유용 합니다. 자세한 내용 및 예제에 나오는 "요소 이름 한정" [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
 동일한 이름의 모듈 수준에서 멤버를 선언 하지 해야 `aliasname`합니다. Visual Basic 컴파일러를 사용 하는 경우 `aliasname` 선언 된 멤버에 대해서만 하 고 더 이상 가져오기 별칭으로 인식 합니다.  
  
 XML 네임 스페이스 접두사를 가져오기 위한 가져오기 별칭 선언에 대 한 구문과 같은, 있지만 결과 다릅니다. 가져오기 별칭은 XML 네임 스페이스 접두사를 사용할 수 XML 리터럴 또는 XML 축 속성에만 접두사로 정규화 된 요소 또는 특성 이름에 대 한 반면 코드 식으로 사용할 수 있습니다.  
  
### <a name="element-names"></a>요소 이름  
 제공 하는 경우 `element`를 나타내야 합니다는 *컨테이너 요소*, 다른 요소를 포함할 수 있는 프로그래밍 요소입니다. 클래스, 구조체, 모듈, 인터페이스 및 열거형을 포함 하는 컨테이너 요소입니다.  
  
 사용할 수 있는 요소의 범위를 `Imports` 를 지정 했는지 여부에 문이 종속 `element`합니다. 만 지정한 경우 `namespace`해당 네임 스페이스의 멤버와 해당 네임 스페이스 내에서 컨테이너 요소의 멤버 이름이 고유 하 게 모든, 한정자 없이 사용할 수 있습니다. 둘 다 지정 하는 경우 `namespace` 고 `element`, 해당 요소의 멤버 한정자 없이 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 C:\ 디렉터리에 있는 폴더를 모두 사용 하 여 반환 된 <xref:System.IO.DirectoryInfo> 클래스입니다.  
  
 코드에 없는 `Imports` 파일의 맨 위에 있는 문. 따라서 합니다 `DirectoryInfo`, <xref:System.Text.StringBuilder>, 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 참조는 네임 스페이스를 사용 하 여 정규화 합니다.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>예  
 다음 예제를 포함 `Imports` 참조 된 네임 스페이스에 대 한 문입니다. 따라서 형식 네임 스페이스를 사용 하 여 완벽 하 게 정규화 할 필요가 없습니다.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>예  
 다음 예제를 포함 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 사용 하는 문입니다. 형식은 별칭으로 정규화 됩니다.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>예  
 다음 예제를 포함 `Imports` 참조 된 형식에 대 한 별칭을 사용 하는 문입니다. 별칭은 형식을 지정 하는 데 사용 됩니다.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Imports 문(XML 네임스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

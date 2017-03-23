---
title: "Imports 문 (.NET Namespace 및 형식) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
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
caps.latest.revision: 40
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
ms.openlocfilehash: 393f3e9a264817d8658585267c954d973290530a
ms.lasthandoff: 03/13/2017

---
# <a name="imports-statement-net-namespace-and-type"></a>Imports 문(.NET 네임스페이스 및 형식)
형식 이름을 네임 스페이스 한정자 없이 참조할 수를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`aliasname`|선택적 요소. *가져오기 별칭* 또는 코드를 참조할 수 있는 이름을 `namespace` 정규화 문자열 대신 합니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`namespace`|필수 요소. 가져오고 있는 네임 스페이스의 정규화 된 이름입니다. 중첩 될 수 있습니다 문자열로 네임 스페이스의 모든 수준에 있습니다.|  
|`element`|선택적 요소. 네임 스페이스에 선언 된 프로그래밍 요소의 이름입니다. 모든 컨테이너 요소를 수 있습니다.|  
  
## <a name="remarks"></a>주의  
 `Imports` 문이 지정된 된 네임 스페이스를 직접 참조할 수에 포함 된 형식을 사용 하도록 설정 합니다.  
  
 단일 네임 스페이스 이름 또는 중첩 된 네임 스페이스의 문자열을 제공할 수 있습니다. 각 중첩 된 네임 스페이스는 마침표로 다음 수준의 네임 스페이스에서 (`.`) 다음 예제와 같이 합니다.  
  
 `Imports System.Collections.Generic`  
  
 각 소스 파일에는 개수에 제한 없이 포함 될 수 있습니다 `Imports` 문입니다. 이러한 옵션 선언 같은 따라야는 `Option Strict` 않으며 문 앞에 야 프로그래밍 요소 선언와 같은 `Module` 또는 `Class` 문입니다.  
  
 사용할 수 있습니다 `Imports` 파일 수준에만 있습니다. 즉, 가져오기에 대 한 선언 컨텍스트는 소스 파일 이어야 하며 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 차단 될 수 없습니다.  
  
 `Imports` 문을 해도 다른 프로젝트 및 어셈블리에서 요소를 프로젝트에서 사용할 수 있습니다. 가져오기 참조 설정 대신을 가지 지 않습니다. 만 이미 프로젝트에 사용할 수 있는 이름을 정규화 할 필요가 없습니다. 자세한 내용은 "포함 된 요소를 가져오는"의 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
> [!NOTE]
>  암시적으로 정의할 수 `Imports` 문에서 사용 하 여는 [프로젝트 디자이너 (Visual Basic), 참조 페이지](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)합니다. 자세한 내용은 참조 [하는 방법: 추가 또는 제거 가져온 네임 스페이스 (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e)합니다.  
  
## <a name="import-aliases"></a>Import 별칭  
 *가져오기 별칭* 형식 또는 네임 스페이스에 대 한 별칭을 정의 합니다. Import 별칭은 하나 이상의 네임 스페이스에 선언 되어 있는 동일한 이름의 항목을 사용 해야 할 때 유용 합니다. 자세한 내용 및 예에 "요소 이름 한정" 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
 동일한 이름의 모듈 수준에서 멤버 선언 하면 안 `aliasname`합니다. Visual Basic 컴파일러를 사용 하면 `aliasname` 선언 된 멤버에 대해서만 하 고 더 이상 가져오기 별칭으로 인식 합니다.  
  
 XML 네임 스페이스 접두사를 가져오기 위한 가져오기 별칭을 선언 하는 데 사용 되는 구문은 사용 그렇게, 되지만 결과가 서로 다릅니다. 반면 XML 네임 스페이스 접두사는 사용할 수 XML 리터럴 또는 XML 축 속성에만 접두사로 정규화 된 요소 또는 특성 이름에 대 한 코드에서 식으로 가져오기 별칭을 사용할 수 있습니다.  
  
### <a name="element-names"></a>요소 이름  
 제공 하는 경우 `element`, 나타내야는 *컨테이너 요소*, 다른 요소를 포함할 수 있는 프로그래밍 요소입니다. 컨테이너 요소는 클래스, 구조체, 모듈, 인터페이스 및 열거형에 포함 됩니다.  
  
 사용할 수 있도록 하는 요소의 범위는 `Imports` 문을 지정 하는지 여부에 따라 달라 집니다 `element`합니다. 만 지정한 경우 `namespace`, 모든 고유 하 게 명명 된 해당 네임 스페이스의 멤버 및 해당 네임 스페이스 내에서 컨테이너 요소의 멤버, 한정자 없이 사용할 수 있습니다. 모두 지정 하면 `namespace` 및 `element`만 해당 요소의 멤버를 한정자 없이 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.IO.DirectoryInfo>클래스</xref:System.IO.DirectoryInfo> 를 사용 하 여 C:\ 디렉터리에 있는 모든 폴더를 반환  
  
 코드에 없는 `Imports` 파일 맨 위에 있는 문. 따라서는 `DirectoryInfo`, <xref:System.Text.StringBuilder>, 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf>네임 스페이스를 사용 하 여 정규화 되지 않은 참조는.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder>  
  
 [!code-vb[VbVbalrStatements #&152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 문입니다. 따라서 형식 네임 스페이스를 사용 하 여 정규화 될 필요가 없습니다.  
  
 [!code-vb[VbVbalrStatements #&153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements #&154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함 `Imports` 참조 된 네임 스페이스에 대 한 별칭을 사용 하는 문입니다. 형식은 별칭으로 한정 됩니다.  
  
 [!code-vb[VbVbalrStatements #&155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements #&156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함 `Imports` 참조 된 형식에 대 한 별칭을 사용 하는 문입니다. 별칭은 형식을 지정 하는 데 사용 됩니다.  
  
 [!code-vb[VbVbalrStatements #&157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements #&158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

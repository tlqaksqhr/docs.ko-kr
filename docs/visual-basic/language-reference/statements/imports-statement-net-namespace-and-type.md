---
title: "Imports Statement (.NET Namespace and Type) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Imports"
  - "imports"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declared element names [Visual Basic], qualification"
  - "imports [Visual Basic]"
  - "Imports statement [Visual Basic]"
  - "aliases [Visual Basic], Imports statement"
  - "container elements [Visual Basic]"
  - "namespaces [Visual Basic], importing"
  - "Imports statement [Visual Basic], syntax"
  - "import aliases [Visual Basic]"
  - "aliases [Visual Basic], import"
  - "declared elements [Visual Basic], container elements"
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 40
---
# Imports Statement (.NET Namespace and Type)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

네임스페이스 정규화 없이도 형식 이름을 참조하도록 설정합니다.  
  
## 구문  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`aliasname`|선택적 요소.  코드에서 전체 한정 문자열 대신 `namespace`를 참조할 수 있는 이름 또는 *가져오기 별칭*입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`namespace`|필수 요소.  가져올 네임스페이스의 정규화된 이름입니다.  모든 수준에 중첩된 네임스페이스의 문자열일 수 있습니다.|  
|`element`|선택적 요소.  네임스페이스에 선언된 프로그래밍 요소의 이름입니다.  임의의 컨테이너 요소일 수 있습니다.|  
  
## 설명  
 `Imports`  문을 사용하면 지정된 네임스페이스에 포함된 형식을 직접 참조할 수 있습니다.  
  
 단일 네임스페이스 이름 또는 중첩된 네임스페이스의 문자열을 제공할 수 있습니다.  중첩된 각 네임스페이스는 다음 예제와 같이 다음 수준의 네임스페이스에서 마침표\(`.`\)를 사용하여 구분됩니다.  
  
 `Imports System.Collections.Generic`  
  
 각 소스 파일에 여러 개의 `Imports` 문을 포함할 수 있습니다.  이 문을 사용하려면 `Option Strict` 문과 같은 옵션 선언 규칙을 따라야 하며 `Module` 또는 `Class` 문과 같은 프로그래밍 요소 선언 앞에 와야 합니다.  
  
 `Imports`는 파일 수준에서만 사용할 수 있습니다.  즉, 가져오기에 대한 선언 컨텍스트는 소스 파일이어야 하며 네임스페이스, 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록이 될 수 없습니다.  
  
 `Imports` 문을 사용하여 사용자의 프로젝트에서 다른 프로젝트 및 어셈블리의 요소를 사용 가능하게 만들 수 없습니다.  이 문으로 참조 설정을 대신할 수는 없습니다.  프로젝트에 이미 사용 가능한 이름을 한정할 때만 제거됩니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)의 "포함하는 요소 가져오기"를 참조하십시오.  
  
> [!NOTE]
>  [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)를 사용하여 암시적 `Imports` 문을 정의할 수 있습니다.  자세한 내용은 [방법: 가져온 네임스페이스 추가 또는 제거\(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md)를 참조하십시오.  
  
## 별칭 가져오기  
 *가져오기 별칭*은 네임스페이스 또는 형식의 별칭을 정의합니다.  가져오기 별칭은 하나 이상의 네임스페이스에서 선언된 같은 이름의 항목을 사용해야 하는 경우에 유용합니다.  자세한 내용 및 예제는 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)에서 "요소 이름 한정" 항목을 참조하십시오.  
  
 `aliasname`과 같은 이름으로 멤버를 모듈 수준에서 선언하면 안 됩니다.  이렇게 하면 Visual Basic 컴파일러는 선언된 멤버에 대해서만 `aliasname`을 사용하며 이 멤버를 더 이상 가져오기 별칭으로 인식하지 않습니다.  
  
 가져오기 별칭의 선언에 사용되는 구문은 XML 네임스페이스 접두사 가져오기에 사용되는 구문과 비슷하지만 결과는 서로 다릅니다.  가져오기 별칭은 코드에서 식으로 사용할 수 있는 반면, XML 네임스페이스 접두사는 XML 리터럴 또는 XML 축 속성에서 정규화된 요소 또는 특성 이름의 접두사로만 사용할 수 있습니다.  
  
### 요소 이름  
 `element`를 제공하는 경우 다른 요소를 포함할 수 있는 프로그래밍 요소인 *컨테이너 요소*를 나타내야 합니다.  컨테이너 요소에는 클래스, 구조체, 모듈, 인터페이스 및 열거형이 포함됩니다.  
  
 `Imports` 문에 의해 사용 가능하게 된 요소의 범위는 `element`를 지정했는지 여부에 따라 다릅니다.  `namespace`만 지정한 경우 해당 네임스페이스에 있는 고유한 이름의 모든 멤버와 해당 네임스페이스 내에 있는 컨테이너 요소의 멤버를 한정자 없이도 사용할 수 있습니다.  `namespace` 및 `element`를 모두 지정한 경우에는 해당 요소의 멤버만 한정자 없이 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IO.DirectoryInfo> 클래스를 사용하여 C:\\ 디렉터리에 있는 모든 폴더를 반환합니다.  
  
 이 코드는 파일 맨 위에 `Imports` 문이 없습니다.  따라서 `DirectoryInfo`, <xref:System.Text.StringBuilder> 및 <xref:Microsoft.VisualBasic.ControlChars.CrLf> 참조는 네임스페이스를 사용하여 정규화되었습니다.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## 예제  
 다음 예제에는 참조된 네임스페이스에 대한 `Imports` 문이 포함되어 있습니다.  따라서 형식은 네임스페이스를 사용하여 정규화하지 않아도 됩니다.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## 예제  
 다음 예제에는 참조된 네임스페이스에 대한 별칭을 생성하는 `Imports` 문이 포함되어 있습니다.  형식이 별칭으로 정규화되었습니다.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## 예제  
 다음 예제에는 참조된 형식에 대한 별칭을 만드는 `Imports` 문이 포함되어 있습니다.  형식을 지정하는 데 별칭이 사용되었습니다.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## 참고 항목  
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
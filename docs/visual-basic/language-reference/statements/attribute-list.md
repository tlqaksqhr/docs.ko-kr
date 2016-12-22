---
title: "Attribute List (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "attribute list"
  - "attributes [Visual Basic], applying"
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Attribute List (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

선언된 프로그래밍 요소에 적용할 특성을 지정합니다.  특성이 여러 개 있으면 쉼표로 구분됩니다.  다음은 단일 특성 구문입니다.  
  
## 구문  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## 요소  
 `attributemodifier`  
 소스 파일의 시작 부분에 적용된 특성에 필수적인 요소이며  [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) 또는 [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) 형식일 수 있습니다.  
  
 `attributename`  
 필수 요소.  특성의 이름으로입니다.  
  
 `attributearguments`  
 선택적 요소.  이 특성에 대한 위치 인수의 목록으로,  인수가 여러 개 있으면 쉼표로 구분됩니다.  
  
 `attributeinitializer`  
 선택적 요소.  이 특성에 대한 변수나 속성 이니셜라이저의 목록입니다.  이니셜라이저가 여러 개 있으면 쉼표로 구분됩니다.  
  
## 설명  
 형식, 프로시저, 속성 등 거의 모든 프로그래밍 요소에 하나 이상의 특성을 적용할 수 있습니다.  특성은 어셈블리의 메타데이터에 표시되며 코드 주석을 지정하거나 특정 프로그래밍 요소의 사용 방법을 지정하는 데 도움이 됩니다.  Visual Basic 및 .NET Framework에 정의된 특성을 적용하거나 사용자 특성을 정의할 수 있습니다.  
  
 특성 사용 시기에 대한 자세한 내용은 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  특성 이름에 대한 자세한 내용은 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하십시오.  
  
## 규칙  
  
-   **배치.** 대부분의 선언된 프로그래밍 요소에 특성을 적용할 수 있습니다.  하나 이상의 특성을 적용하려면 요소 선언의 시작 부분에 *특성 블록*을 배치합니다.  특성 목록의 각 항목은 적용할 특성과 이 특성 호출에 사용할 한정자와 인수를 지정합니다.  
  
-   **꺾쇠괄호.** 특성 목록을 사용하는 경우 꺾쇠 괄호\("`<`" 및 "`>`"\)로 묶어야 합니다.  
  
-   **선언의 일부.** 특성은 별도의 문이 아니라 요소 선언의 일부여야 합니다.  줄 연속 시퀀스\(" `_`"\)를 사용하여 선언문을 여러 소스 코드 줄로 확장할 수 있습니다.  
  
-   **한정자.** 특성 한정자\(`Assembly` 또는 `Module`\)는 소스 파일의 시작 부분에 있는 프로그래밍 요소에 적용된 모든 특성에 필요합니다.  소스 파일의 시작 부분에 위치하지 않은 요소에 적용된 특성에는 특성 한정자를 사용할 수 없습니다.  
  
-   **인수.** 특성에 대한 모든 위치 인수는 변수 또는 속성 이니셜라이저 앞에 와야 합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 `Function` 프로시저의 기본 정의에 적용합니다.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>는 특성 사용 프로시저가 관리되지 않는 DLL\(동적 연결 라이브러리\)의 진입점을 표시함을 나타냅니다.  이 특성은 DLL 이름을 위치 인수로, 다른 정보를 변수 이니셜라이저로 제공합니다.  
  
## 참고 항목  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Module \<keyword\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 코드에서 문 분리 및 결합](../Topic/How%20to:%20Break%20and%20Combine%20Statements%20in%20Code%20\(Visual%20Basic\).md)
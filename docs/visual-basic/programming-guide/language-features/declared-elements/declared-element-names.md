---
title: "Declared Element Names (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "declared elements, case sensitivity"
  - "names, Visual Basic rules"
  - "naming conventions"
  - "element names"
  - "declared elements, identifiers"
  - "declarations, elements"
  - "declared elements, valid names"
  - "[] escape characters [Visual Basic]"
  - "names, elements"
  - "declaration statements, declared elements"
  - "declaring elements"
  - "identifiers, declared elements"
  - "case sensitivity, declared element names"
  - "escape characters"
  - "names, declared elements"
  - "declared elements, about declared elements"
  - "escaped names"
  - "declared elements, names"
  - "names, naming conventions"
  - "identifiers, elements"
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Declared Element Names (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

모든 선언 요소는 *식별자*라고도 하는 이름을 가지며 이 이름은 코드에서 선언 요소를 참조하는 데 사용됩니다.  
  
## 규칙  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 요소 이름은 다음 규칙을 준수해야 합니다.  
  
-   영문자 또는 밑줄\(`_`\)로 시작해야 합니다.  
  
-   영문자, 10진수 및 밑줄만으로 이루어져야 합니다.  
  
-   밑줄로 시작할 경우에는 반드시 하나 이상의 영문자나 10진수를 포함해야 합니다.  
  
-   1023자를 넘을 수 없습니다.  
  
 1023자의 길이 제한은 `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`와 같이 정규화된 이름의 전체 문자열에도 적용됩니다.  
  
 다음 예제에서는 올바른 요소 이름을 보여 줍니다.  
  
 `aB123__45`  
  
 `_567`  
  
 다음 예제에서는 잘못된 요소 이름을 보여 줍니다.  첫 번째 요소에는 밑줄만 포함되어 있고, 두 번째 요소는 10진수로 시작되고, 세 번째 요소에는 잘못된 문자\($\)가 포함되어 있습니다.  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  밑줄\(`_`\)로 시작되는 요소 이름은 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\(CLS\)의 일부가 아니므로 CLS 규격 코드에서 해당 이름을 정의하는 구성 요소를 사용할 수 없습니다.  그러나 요소 이름의 다른 위치에 있는 밑줄은 CLS 규격입니다.  
  
### 이름 길이 지침  
 이름은 요소의 특성을 명확히 나타내면서 가능한 간결하게 지정해야  코드를 읽기가 쉬워지고 줄의 길이와 소스 파일 크기가 줄어듭니다.  
  
 그러나 요소가 나타내는 내용과 코드에서 해당 요소를 사용하는 방법을 충분히 설명하지 못할 정도로 이름이 짧아서는 안 됩니다.  이름의 길이는 코드의 가독성에 중요한 영향을 미칩니다.  다른 사용자가 이름을 이해하려는 경우 또는 사용자 자신이 이름을 작성하고 나서 한참 뒤에 해당 이름을 보는 경우 적합한 이름을 사용한다면 상당한 시간을 절약할 수 있습니다.  
  
## 이스케이프 이름  
 일반적으로, 요소 이름에는 `Case`나 `Friend`와 같이 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 예약한 키워드를 사용할 수 없습니다.  그러나 대괄호\(`[ ]`\)로 묶은 *이스케이프 이름*은 정의할 수 있습니다.  대괄호로 묶으면 확실히 구분할 수 있기 때문에 이스케이프된 이름과 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 키워드를 함께 사용할 수 있습니다.  나중에 코드에서 이름을 참조할 때도 대괄호를 사용합니다.  
  
 일반적으로 이스케이프 이름은 다음과 같은 경우에만 사용됩니다.  
  
-   이름으로 사용할 키워드를 예약하지 않은 이전 버전의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 코드를 마이그레이션한 경우  
  
-   지정한 키워드를 예약하지 않은 다른 언어에서 작성한 코드로 작업하는 경우  
  
 그렇지 않은 경우 이름과 키워드가 충돌하면 해당 요소의 이름을 바꿔야 합니다.  IDE\(통합 개발 환경\)를 사용하여 이 작업을 쉽게 수행할 수 있습니다.  자세한 내용은 [리팩터링 및 이름 바꾸기 대화 상자](../../../../visual-basic/developing-apps/using-ide/refactoring-and-rename-dialog-box.md)를 참조하십시오.  
  
## 이름의 대\/소문자 구분  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 요소 이름은 대\/소문자를 구분하지 않습니다.  즉, 알파벳은 같고 대\/소문자가 다른 두 이름이 있으면 컴파일러에서 이 두 이름을 동일한 것으로 해석합니다.  예를 들어, `ABC`와 `abc`는 동일한 선언 요소를 참조하는 것으로 간주합니다.  
  
 그러나, CLR\(공용 언어 런타임\)에서는 대\/소문자를 구분하는 바인딩을 사용합니다.  그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대\/소문자가 구분됩니다.  예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다.  클래스를 다시 컴파일하고 요소 이름을 `abc`로 변경하면 이 클래스를 사용하는 다른 어셈블리가 더 이상 이 요소에 액세스할 수 없습니다.  따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대\/소문자를 변경하지 않아야 합니다.  
  
## 이름 및 로캘  
 이름을 비교하는 것은 로캘과 무관합니다.  한 로캘에서 두 이름이 일치하면 다른 모든 로캘에서도 일치합니다.  
  
## 참고 항목  
 [Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)
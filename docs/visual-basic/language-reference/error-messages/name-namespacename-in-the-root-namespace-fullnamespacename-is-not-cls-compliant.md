---
title: "Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40039"
  - "bc40039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40039"
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Name &lt;namespacename&gt; in the root namespace &lt;fullnamespacename&gt; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

어셈블리가 `<CLSCompliant(True)>`로 표시되지만 루트 네임스페이스 이름 요소가 밑줄\(`_`\)로 시작합니다.  
  
 프로그래밍 요소는 하나 이상의 밑줄을 포함할 수 있지만 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격이어야 하므로 밑줄로 시작하지 않아야 합니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40039  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요한 경우 밑줄로 시작하는 요소가 없도록 루트 네임스페이스 이름을 변경합니다.  
  
-   네임스페이스 이름을 변경하지 않아야 하는 경우 <xref:System.CLSCompliantAttribute>를 어셈블리에서 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [\/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
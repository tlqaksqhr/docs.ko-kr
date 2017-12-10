---
title: "이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36de8b6a27c47e9e7192aed10e6b561bb0c07acc
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닙니다
로 어셈블리 표시 되어 `<CLSCompliant(True)>`, 루트 네임 스페이스 이름의 요소가 밑줄로 시작 하지만 (`_`).  
  
 프로그래밍 요소를 준수 해야 하지만 하나 이상의 밑줄을 포함할 수 있습니다는 [언어 독립성 및 언어 독립적 구성 요소](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS) 시작 하지 않아야 밑줄로 합니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 <xref:System.CLSCompliantAttribute> 를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40039  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격이 필요 하면 밑줄로 시작 하는 해당 요소 중 루트 네임 스페이스 이름을 변경 합니다.  
  
-   네임 스페이스 이름은 변경 되지 않고 유지, 필요한 경우 제거 합니다는 <xref:System.CLSCompliantAttribute> 어셈블리에서로 표시 하거나 `<CLSCompliant(False)>`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

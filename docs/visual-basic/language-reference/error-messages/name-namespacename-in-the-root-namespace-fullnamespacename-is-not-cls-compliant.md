---
title: "이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닌 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
dev_langs:
- VB
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
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
ms.openlocfilehash: 344a0ca098160a8d9f5bc8281a941311f82000c4
ms.lasthandoff: 03/13/2017

---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>이름 &lt;namespacename&gt; 루트 네임 스페이스에 &lt;fullnamespacename&gt; CLS 규격이 아닙니다
어셈블리로 표시 되어 `<CLSCompliant(True)>`, 루트 네임 스페이스 이름의 요소가 밑줄로 시작 하지만 (`_`).  
  
 프로그래밍 요소를 준수 하 게 하지만 하나 이상의 밑줄이 포함 될 수 있습니다는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 그 해야 하지 밑줄로 시작 합니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute> 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute>  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40039  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   CLS 규격, 필요한 경우 해당 요소 중 밑줄로 시작 될 수 있도록 루트 네임 스페이스 이름을 변경 합니다.  
  
-   다음 제거 해야 합니다. 네임 스페이스 이름을 그대로 유지 하는 경우는 <xref:System.CLSCompliantAttribute>어셈블리에서로 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)   
 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [선언된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)

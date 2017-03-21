---
title: "&quot;Extension&quot; 특성 &quot;Module&quot;, &quot;Sub&quot; 또는 &quot;Function&quot; 선언에만 적용할 수 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
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
ms.openlocfilehash: 3eee008f737bf625023b6e4d58e1df7d282148d3
ms.lasthandoff: 03/13/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>'Extension' 특성 'Module', 'Sub' 또는 'Function' 선언에만 적용할 수 있습니다.
Visual Basic의 데이터 형식을 확장 하 여 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는 것입니다. 확장 메서드는 `Sub` 프로시저 또는 `Function` 프로시저입니다. 모든 확장 메서드는 확장 특성으로 표시 해야 `<Extension()>`에서 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스.</xref:System.Runtime.CompilerServices?displayProperty=fullName> 필요에 따라 확장 메서드를 포함 하는 모듈은 동일한 방식으로 표시할 수 있습니다. 확장 특성을 사용 하지 않는 유효합니다.  
  
 **오류 ID:** BC36550  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   확장 특성을 제거 합니다.  
  
-   바깥쪽 모듈에 정의 하는 방법으로 확장 프로그램을 다시 디자인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `Print` 에 대 한 메서드는 `String` 데이터 형식입니다.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)

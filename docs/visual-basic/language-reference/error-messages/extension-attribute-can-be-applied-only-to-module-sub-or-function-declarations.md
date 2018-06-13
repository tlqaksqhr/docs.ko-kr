---
title: '&#39;확장&#39; 특성에만 적용할 수 있습니다 &#39;모듈&#39;, &#39;Sub&#39;, 또는 &#39;함수&#39; 선언'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: d7f8829cb879d612711ac6bcc6bf4aa065fbe323
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587321"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;확장&#39; 특성에만 적용할 수 있습니다 &#39;모듈&#39;, &#39;Sub&#39;, 또는 &#39;함수&#39; 선언
Visual Basic의 데이터 형식을 확장 하는 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는입니다. 사용할 수 있는 확장 메서드에 `Sub` 프로시저 또는 `Function` 프로시저입니다. 모든 확장 메서드가 확장 특성으로 표시 해야 `<Extension()>`에서 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임 스페이스입니다. 필요에 따라 확장 메서드를 포함 하는 모듈은 같은 방식으로 표시할 수 있습니다. 확장 특성의 사용 하지 않는 유효합니다.  
  
 **오류 ID:** BC36550  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   확장 특성을 제거 합니다.  
  
-   바깥쪽 모듈에 정의 된 메서드와, 확장 프로그램을 다시 디자인 합니다.  
  
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
 [확장명 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)

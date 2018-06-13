---
title: '&#39;&lt;membername&gt; &#39; 모호 합니다. 상속 된 인터페이스를 통해 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;interfacename2&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 23d1a11bcee2a4faae40f2683d109d5820ee5f9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585303"
---
# <a name="39ltmembernamegt39-is-ambiguous-across-the-inherited-interfaces-39ltinterfacename1gt39-and-39ltinterfacename2gt39"></a>&#39;&lt;membername&gt; &#39; 모호 합니다. 상속 된 인터페이스를 통해 &#39; &lt;interfacename1&gt; &#39; 및 &#39; &lt;interfacename2&gt;&#39;
동일한 이름 가진 둘 이상의 멤버가 여러 인터페이스에서 상속 합니다.  
  
 **오류 ID:** BC30685  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   기본 인터페이스에 사용할; 값 캐스팅 예를 들어:  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

---
title: '&lt;type1&gt;&#39;&lt;typename&gt; &#39; 구현 해야 &#39; &lt;membername&gt; &#39; 인터페이스에 대 한 &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 0f93bd137bdc21268cbca139ae739843561350ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596748"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39; 구현 해야 &#39; &lt;membername&gt; &#39; 인터페이스에 대 한 &#39; &lt;interfacename&gt;&#39;
'\<형식 이름 >'를 구현 해야 '\<membername >' 인터페이스에 대 한 '\<interfacename >'입니다. 속성을 구현 일치 해야 합니다 'ReadOnly '/' WriteOnly' 지정 자가 있습니다.  
  
 클래스 또는 구조체 인터페이스를 구현 하지만 프로시저, 속성 또는 인터페이스에 의해 정의 된 이벤트를 구현 하지 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.  
  
 **오류 ID:** BC30154  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  동일한 이름 및 인터페이스에 정의 된 대로 서명을 가진 멤버를 선언 합니다. 포함 해야 적어도 `End Function`, `End Sub`, 또는 `End Property` 문.  
  
2.  추가 `Implements` 의 끝에 절은 `Function`, `Sub`, `Property`, 또는 `Event` 문. 예를 들어:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  속성을 구현할 때는 다음 사항을 확인 `ReadOnly` 또는 `WriteOnly` 인터페이스 정의와 같은 방법으로 사용 됩니다.  
  
4.  속성을 구현할 때는 선언 `Get` 및 `Set` 프로시저 적절 하 게 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

---
title: '&lt;type1&gt;&#39;&lt; typename&gt;&#39; 해야 구현 &#39;&lt; methodname&gt;&#39; 인터페이스 &#39;에 대 한&lt; interfacename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt; typename&gt;&#39; 해야 구현 &#39;&lt; methodname&gt;&#39; 인터페이스 &#39;에 대 한&lt; interfacename&gt;&#39;
클래스 또는 구조체 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지 않습니다. 인터페이스의 모든 멤버를 구현 해야 합니다.  
  
 **오류 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  동일한 이름 및 인터페이스에 정의 된 대로 서명이 있는 프로시저를 선언 합니다. 포함 해야 적어도 `End Function` 또는 `End Sub` 문.  
  
2.  추가 `Implements` 의 끝에 절은 `Function` 또는 `Sub` 문. 예:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

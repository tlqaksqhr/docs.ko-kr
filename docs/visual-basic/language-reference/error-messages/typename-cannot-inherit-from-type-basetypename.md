---
title: '&#39; &lt;typename&gt;&#39;에서 상속할 수 없습니다. &lt;형식&gt; &#39;&lt; basetypename&gt;&#39; 기준의 액세스를 확장 하기 때문에 &lt;형식&gt; 어셈블리 외부에서'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39; &lt;typename&gt;&#39;에서 상속할 수 없습니다. &lt;형식&gt; &#39;&lt; basetypename&gt;&#39; 기준의 액세스를 확장 하기 때문에 &lt;형식&gt; 어셈블리 외부에서
기본 클래스에서 상속 하는 클래스 또는 인터페이스 또는 인터페이스 하지만 덜 제한적인 액세스 수준이 있는 포함 합니다.  
  
 예를 들어는 `Public` 인터페이스에서 상속 되는 `Friend` 인터페이스 또는 `Protected` 클래스에서 상속는 `Private` 클래스입니다. 기본 클래스 또는 의도 된 수준 보다 액세스 하기 인터페이스를 노출 합니다.  
  
 **오류 ID:** BC30910  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   파생된 클래스 또는 인터페이스를 제한적으로 기본 클래스 또는 인터페이스의 설정의 액세스 수준을 변경 합니다.  
  
     또는  
  
-   덜 제한적인 액세스 수준이 필요한 경우 제거 된 `Inherits` 문. 좀 더 제한 된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)

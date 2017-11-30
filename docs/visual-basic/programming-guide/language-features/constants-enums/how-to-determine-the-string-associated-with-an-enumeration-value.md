---
title: "방법: 열거형 값과 연결된 문자열 확인(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01e2b0cfa6b1e426b38198581c7d493c8907b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>방법: 열거형 값과 연결된 문자열 확인(Visual Basic)
<xref:System.Enum.GetValues%2A> 및 <xref:System.Enum.GetNames%2A> 메서드를 사용 하는 문자열 및 열거형 멤버와 관련 된 값을 확인할 수 있습니다.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>열거형과 연결 된 문자열을 확인 하려면  
  
-   사용 된 <xref:System.Enum.GetNames%2A> 열거형 멤버와 연결 된 문자열을 검색 하는 메서드입니다. 이 예제에서는 열거형을 선언 `flavorEnum`를 사용 하 여는 <xref:System.Enum.GetNames%2A> 메서드 각 멤버와 연결 된 문자열을 표시 합니다.  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Enum 문](../../../../visual-basic/language-reference/statements/enum-statement.md)

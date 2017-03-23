---
title: "이름 &quot;&lt;이름&gt;&quot; 선언 되지 않은 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 81b6862a7f8ceb7998b2ea53336ed3af46b1db5f
ms.lasthandoff: 03/13/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a>이름 '&lt;이름&gt;' 선언 되지 않았습니다
문에서 프로그래밍 요소를 참조 하지만 컴파일러에서 똑같은 이름 가진 요소를 찾을 수 없습니다.  
  
 **오류 ID:** BC30451  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  참조하는 문에서 이름의 철자를 검사합니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]대/소문자가 있지만 맞춤법 다르면 전혀 다른 이름으로 간주 됩니다. 밑줄(`_`)은 이름의 일부이므로 철자의 일부입니다.  
  
2.  멤버 액세스 연산자 있는지 확인 합니다 (`.`) 개체와 그 멤버 사이입니다. 예를 들어 한 <xref:System.Windows.Forms.TextBox>라는 컨트롤 `TextBox1`, 액세스 하는 <xref:System.Windows.Forms.TextBoxBase.Text%2A>입력 해야 하는 속성 `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox> `TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.  
  
3.  철자가 정확 하 고 개체 멤버 액세스의 구문이 올바른지, 요소가 선언 된 확인 합니다. 자세한 내용은 참조 [요소 선언](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)합니다.  
  
4.  프로그래밍 요소 선언 된 경우 범위에 있는지 확인 합니다. 참조 하는 문에 프로그래밍 요소를 선언 하는 영역을 벗어날 경우에 요소 이름을 정규화 할 수 있습니다. 자세한 내용은 참조 [Visual Basic의 범위](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 상수 요약](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [선언된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

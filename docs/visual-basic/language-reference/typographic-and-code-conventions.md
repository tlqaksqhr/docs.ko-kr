---
title: 글꼴 표시 및 코드 규칙(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: eb7a33ef21bf6beda730dffa8eb7ff9cabe599fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604499"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>글꼴 표시 및 코드 규칙(Visual Basic)
Visual Basic 설명서는 다음과 같은 인쇄 및 코드 규칙을 사용합니다.  
  
## <a name="typographic-conventions"></a>인쇄 규칙  
  
|예제|설명|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|특정 언어 키워드 및 런타임 멤버 첫 문자가 대문자 있고이 예제와 같이 서식이 지정 됩니다.|  
|**SmallProject**, **ButtonCollection**|단어 및 구를 입력 하 라는 메시지가 표시이 예제와 같이 서식이 지정 됩니다.|  
|[Module 문](../../visual-basic/language-reference/statements/module-statement.md)|링크를 클릭 하 여 다른 도움말 페이지로 이동할 수 있습니다이 예제에 표시 된 대로 형식이 지정 됩니다.|  
|*개체*, *variableName*, `argumentList`|사용자가 제공한 정보에 대 한 자리 표시자에는이 예제에 표시 된 대로 형식이 지정 됩니다.|  
|[전체]를 [ *expressionList* ]|구문에서 선택 항목은 대괄호로 묶여 있습니다.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|구문에서 두 개 이상의 항목 간에 항목을 선택 해야 하는 경우는 중괄호로 묶여 항목과 세로 막대로 구분 합니다.<br /><br /> 항목 하나를 한 개만 선택 해야 합니다.|  
|[ `Protected` &#124; `Friend` ]|구문에서 두 개 이상의 항목을 선택 하는 옵션이 있는 경우는 대괄호로 묶인 항목과 세로 막대로 구분 합니다.<br /><br /> 항목의 조합 또는 항목을 선택할 수 있습니다.|  
|[{ `ByVal` &#124; `ByRef` }]|구문에서 둘 이상의 항목을 선택할 수 있지만 항목을 완전히 생략할 수도 있습니다 항목은 대괄호로 묶여 중괄호로 묶여 세로 막대로 구분 합니다.|  
|*memberName*1, *memberName*2, *memberName*3|이 예제에 나와 있는 것 처럼 첨자, 같은 자리 표시자의 여러 인스턴스 구분 됩니다.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|줄임표 (...)는 구문에서 불특정 개수의 줄임표 앞에 즉시 종류의 항목을 나타내는 데 사용 됩니다.<br /><br /> 코드에서 줄임표 명확 하 게 설명 생략 하는 코드를 의미 합니다.|  
|ESC 키를 입력|키 이름 및 키보드의 키 시퀀스 모두 대문자로 표시 됩니다.|  
|ALT + F1|더하기 기호 (+) 키 이름 사이 표시 되 면 다른를 누른 채 한 키를 누른 해야 있습니다. 예를 들어 ALT + f 1 ALT 키를 누른 채 F1 키를 누르는 것을 의미 합니다.|  
  
## <a name="code-conventions"></a>코드 규칙  
  
|예제|설명|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|코드 샘플 고정 폭 글꼴에 나타나고이 예제와 같이 서식이 지정 됩니다.|  
|값을 설정 하는 이전 문을 `sampleString` 에 "Hello, world!"|이 예제에 나와 있는 것 처럼 설명 텍스트의 코드 요소에 고정 폭 글꼴을에 나타납니다.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|코드 주석 아포스트로피 (') 또는 REM 키워드에 의해 도입 됩니다.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|공백과 밑줄 (_) 줄의 끝에 다음 줄에서 계속 해 서 문을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 언어 참조](../../visual-basic/language-reference/index.md)  
 [키워드](../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic 런타임 라이브러리 멤버](../../visual-basic/language-reference/runtime-library-members.md)  
 [Visual Basic 명명 규칙](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [방법: 코드에서 문 분리 및 결합](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [코드 주석](../../visual-basic/programming-guide/program-structure/comments-in-code.md)

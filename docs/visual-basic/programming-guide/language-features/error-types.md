---
title: "오류 유형 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
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
ms.openlocfilehash: d48756b74baf757f043e68124d8b65c2f613e595
ms.lasthandoff: 03/13/2017

---
# <a name="error-types-visual-basic"></a>오류 형식(Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 오류 (라고도 *예외*) 세 가지 범주 중 하나에 속합니다: 구문 오류, 런타임 오류 및 논리 오류입니다.  
  
## <a name="syntax-errors"></a>구문 오류  
 *구문 오류* 코드를 작성 하는 동안 나타나는 것 들입니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]입력할 때 코드를 검사 하는 **코드 편집기** 창 철자 부적절 하 게 언어 요소를 사용 하 여 등의 실수 한 경우 사용자에 게 알려 합니다. 구문 오류는 오류의 가장 일반적인 유형입니다. 하면 쉽게 수정할 수 코딩 환경에서 발생 하는 즉시 합니다.  
  
> [!NOTE]
>  `Option Explicit` 문은 구문 오류를 방지 하는 한 가지 방법은입니다. 강제로 사전에 응용 프로그램에서 사용할 모든 변수를 선언할 수 있습니다. 따라서 이러한 변수는 코드에 사용 되는 경우 철자 오류가 발생할 즉시 발생 하며 수정 될 수 있습니다.  
  
## <a name="run-time-errors"></a>런타임 오류  
 *런타임 오류* 컴파일 및 코드를 실행 한 후에 나타나는 것 들입니다. 이러한 구문 오류가 없을 실행 되지 않는 한다는 점에서 올바른 것으로 나타날 수 있는 코드 작업이 포함 됩니다. 예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다. 파일이 손상 된 경우 응용 프로그램을 수행할 수 없습니다 하지만 `Open` 기능을 실행을 중지 합니다. 결함이 있는 코드를 다시 작성 한 다음 다시 컴파일하고 다시 실행 하 여 대부분의 런타임 오류를 해결할 수 있습니다.  
  
## <a name="logic-errors"></a>논리 오류  
 *논리 오류* 는 나타나는 응용 프로그램을 사용에서 합니다. 이들은 대부분 자주 예기치 않은 결과가 사용자 작업에 대 한 응답에서입니다. 예를 들어 키를 잘못 입력된 또는 다른 외부 영향을 주지 않이 예상된 매개 변수 내에서 작동을 중지 하는 응용 프로그램 또는 완전히 합니다. 논리 오류는 일반적으로 되지 않으므로 항상 지우기 시작 위치를 수정 하기 어려운 유형입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [디버거 기본 사항](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)

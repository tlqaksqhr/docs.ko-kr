---
title: "오류 형식(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a>오류 형식(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], 오류 (호출 또한 *예외*) 세 가지 범주 중 하나에 해당: 구문 오류, 런타임 오류 및 논리 오류입니다.  
  
## <a name="syntax-errors"></a>구문 오류  
 *구문 오류* 는 코드를 작성 하는 동안 발생 하 합니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]입력할 때 코드를 검사 하는 **코드 편집기** 창 철자 또는 부적절 하 게 언어 요소를 사용 하 여 등의 실수 한 경우 경고 합니다. 구문 오류는 오류의 가장 일반적인 형식입니다. 하면 쉽게 수정할 수 코딩 환경에서 발생 하는 즉시 합니다.  
  
> [!NOTE]
>  `Option Explicit` 문의 구문 오류를 방지 하는 한 가지 방법은 됩니다. 강제로 응용 프로그램에 사용할 모든 변수 사전에 선언할 수 있습니다. 따라서 이러한 변수는 코드에 사용 되는 경우 철자 오류가 발생할 즉시 발생 하며 수정 될 수 있습니다.  
  
## <a name="run-time-errors"></a>런타임 오류  
 *런타임 오류* 는 컴파일 및 코드를 실행 한 후에 발생 하 합니다. 이러한 문제가 되는 것에 구문 오류가 없으면 실행 되지 것입니다 한다는 점에서 올바른 것으로 표시 될 수 있는 코드입니다. 예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다. 하지만 파일이 손상 된 경우 응용 프로그램을 수행할 수 없습니다는 `Open` 기능을 실행을 중지 합니다. 잘못 된 코드를 다시 작성 한 후 다시 컴파일하지 마우스를 다시 실행 하 여 대부분의 런타임 오류를 해결할 수 있습니다.  
  
## <a name="logic-errors"></a>논리 오류  
 *논리 오류* 는 나타나는 응용 프로그램을 사용에서 합니다. 이들은 대부분 종종 예기치 않은 결과가 사용자의 작업에 대 한 응답 으로입니다. 예를 들어 잘못 입력 된 키 또는 등의 외부 요인 않을 응용 프로그램의 실행이 필요한 매개 변수 내에서 작업을 중지 또는 완전히 합니다. 논리 오류는 일반적으로 되지 않으므로 항상 지우기 시작 위치를 해결 하려면 가장 어려운 유형입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [디버거 기본 사항](/visualstudio/debugger/debugger-basics)

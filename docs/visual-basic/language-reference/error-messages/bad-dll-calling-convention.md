---
title: DLL 호출 규칙이 잘못되었습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a>DLL 호출 규칙이 잘못되었습니다.
동적 연결 라이브러리 (DLL)에 전달 된 인수는 루틴에서 예상 되 정확히 일치 해야 합니다. 호출 규칙 번호, 형식 인수의 순서와 함께 처리합니다. 프로그램 루틴 인수의 수 나 잘못 된 형식이 전달 되는 DLL에서 호출 하 고 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  모든 인수 형식이 호출 하는 루틴의 선언에 지정 된 인수와 일치 하는지 확인 합니다.  
  
2.  동일한 수의 호출 하는 루틴의 선언에 표시 된 인수를 전달 하는 있는지 확인 합니다.  
  
3.  DLL 루틴은 값으로 인수를 예상 하는 경우 해야 `ByVal` 루틴에 대 한 선언에서 이러한 인수에 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Call 문](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)

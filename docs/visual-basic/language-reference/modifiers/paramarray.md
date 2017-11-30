---
title: ParamArray(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a>ParamArray(Visual Basic)
프로시저 매개 변수가 지정 된 형식의 요소 선택적 배열 임을 지정 합니다. `ParamArray`매개 변수 목록의 마지막 매개 변수 에서만 사용할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `ParamArray`프로시저에 임의 개수의 인수를 전달할 수 있습니다. A `ParamArray` 매개 변수는 항상 사용 하 여 선언 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.  
  
 하나 이상의 인수를 제공할 수 있습니다는 `ParamArray` 적절 한 데이터의 배열을 전달 하 여 매개 변수를 쉼표로 구분 된 목록을 입력 값 또는 아무 것도 전혀 합니다. 자세한 내용은 "ParamArray 호출"의 참조 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.  
  
> [!IMPORTANT]
>  무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다. 호출 코드에서 매개 변수 배열에 동의 하면 해당 길이 테스트 하 고 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.  
  
 `ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)

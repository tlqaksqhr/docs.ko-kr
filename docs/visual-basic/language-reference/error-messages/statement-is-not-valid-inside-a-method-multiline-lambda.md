---
title: "문은은 메서드를 여러 줄 람다 내부 유효 하지 않습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords: BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>메서드 내부에는 문을 사용할 수 없습니다./multiline lambda
문이에서 유효 하지 않음을 `Sub`, `Function`, 속성 `Get`, 속성 또는 `Set` 프로시저입니다. 일부 문이 모듈 또는 클래스 수준에 배치할 수 있습니다. 다른 사용자와 같은 `Option Strict`, 네임 스페이스 수준 이어야 하며 다른 모든 선언 앞에 야 합니다.  
  
 **오류 ID:** BC30024  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   문을 프로시저에서 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)

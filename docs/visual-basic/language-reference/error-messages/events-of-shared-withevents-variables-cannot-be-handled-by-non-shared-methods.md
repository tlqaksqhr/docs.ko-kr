---
title: 비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f61f4cd17b1bb3088117e0a0d91b186fd40db3b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>비공유 메서드에서는 공유 WithEvents 변수의 이벤트를 처리할 수 없습니다.
선언 된 변수는 `Shared` 한정자는 공유 변수입니다. 공유 변수는 정확히 하나의 저장 위치를 식별합니다. 선언 된 변수는 `WithEvents` 변수 속해 있는 형식 변수 발생 하는 이벤트 집합을 처리 하는 한정자 어설션 합니다. 속성에서 만든 값이 변수에 할당 되는 경우는 `WithEvents` 기존 이벤트 처리기를 언 후크합니다 선언과 연결 하는 통해 새 이벤트 처리기는 `Add` 메서드.  
  
 **오류 ID:** BC30594  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이벤트 처리기 선언 `Shared`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)

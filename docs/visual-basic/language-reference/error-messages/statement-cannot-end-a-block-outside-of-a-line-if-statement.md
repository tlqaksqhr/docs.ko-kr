---
title: 문 줄 외부의 블록에서 끝날 수 없으며 &#39;경우&#39; 문
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>문 줄 외부의 블록에서 끝날 수 없으며 &#39;경우&#39; 문
한 줄 `If` 문 중 하나는 콜론 (:)으로 구분 된 여러 문을 포함 한 `End` 문을 한 줄의 외부 제어 블록에 대 한 `If`합니다. 한 줄 `If` 문을 사용 하지 않는 `End If` 문.  
  
 **오류 ID:** BC32005  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   단일 줄 이동 `If` 문을 포함 하는 제어 블록 밖의 `End If` 문.  
  
## <a name="see-also"></a>참고 항목  
 [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

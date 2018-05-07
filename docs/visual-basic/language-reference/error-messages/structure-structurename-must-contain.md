---
title: 구조 &#39; &lt;structurename&gt; &#39; 인스턴스 멤버 변수 또는 표시 되지 않은 하나 이상의 이벤트 선언이 하나 이상 포함 해야 &#39;사용자 지정&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>구조 &#39; &lt;structurename&gt; &#39; 인스턴스 멤버 변수 또는 표시 되지 않은 하나 이상의 이벤트 선언이 하나 이상 포함 해야 &#39;사용자 지정&#39;
구조 정의 비공유 변수 또는 비공유 사용자 이벤트가 포함 되지 않습니다.  
  
 모든 구조는 변수 또는 비공유 대신 각 특정 인스턴스마다 모든 인스턴스에 전체적으로 적용 되는 이벤트 중 하나에 있어야 합니다 ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). 비공유 상수, 속성 및 프로시저가 요구이 사항을 충족 하지 않습니다. 또한 비공유 변수가 및 비공유 이벤트가 하나만 있는 경우 해당 이벤트 일 수 없습니다는 `Custom` 이벤트입니다.  
  
 **오류 ID:** BC30941  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   하나 이상의 변수나 없는 이벤트를 정의 `Shared`합니다. 하나의 이벤트를 정의 하는 경우 사용자와 공유 되지 않는 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [방법: 구조체 선언](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)

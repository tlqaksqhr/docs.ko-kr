---
title: '&#39;#Region&#39; 및 &#39;#End 지역&#39; 문은 메서드 본문 여러 줄 람다 식 내에서 유효 하지 않습니다.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; 및 &#39;#End 지역&#39; 문은 메서드 본문/여러 줄 람다 식 내에서 유효 하지 않습니다.
`#Region` 블록 클래스, 모듈 또는 네임 스페이스 수준에서 선언 해야 합니다. 축소 가능한 영역에는 하나 이상의 프로시저 포함할 수 있지만 시작 되거나 프로시저 내부에서 완료 된 것입니다.  
  
 **오류 ID:** BC32025  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  앞의 절차와 올바르게 종료 되었는지 확인 하십시오는 `End Function` 또는 `End Sub` 문.  
  
2.  확인 하는 `#Region` 및 `#End Region` 지시문은 같은 코드 블록에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)

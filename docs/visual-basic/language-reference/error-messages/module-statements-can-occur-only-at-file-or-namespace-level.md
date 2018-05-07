---
title: '&#39;모듈&#39; 문은 파일이 나 네임 스페이스 수준 에서만 사용할 수 있습니다'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;모듈&#39; 문은 파일이 나 네임 스페이스 수준 에서만 사용할 수 있습니다
`Module` 문이 소스 파일의 맨 위쪽에 표시 해야 직후 `Option` 및 `Imports` 문, 전역 특성 및 네임 스페이스 선언을 다른 모든 선언 앞입니다.  
  
 **오류 ID:** BC30617  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이동 된 `Module` 문을 네임 스페이스 선언 또는 소스 파일의 맨 위에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)

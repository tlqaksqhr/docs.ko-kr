---
title: '&#39;AddressOf&#39; 피연산자 괄호 없이 메서드 이름 이어야 합니다.'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 701d86e03d9b14236eec8436d99ec40cebbbcd44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583814"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39;AddressOf&#39; 피연산자 괄호 없이 메서드 이름 이어야 합니다.
`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다. 구문은 다음과 같습니다.  
  
 `AddressOf` `procedurename`  
  
 괄호 뒤의 인수를 삽입 `AddressOf`에 불필요 합니다.  
  
 **오류 ID:** BC30577  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  뒤의 인수 주위에 괄호를 제거 `AddressOf`합니다.  
  
2.  인수는 메서드 이름 인지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)

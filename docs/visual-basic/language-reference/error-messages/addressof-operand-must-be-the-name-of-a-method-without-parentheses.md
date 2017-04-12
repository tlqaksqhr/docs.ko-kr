---
title: "&quot;AddressOf&quot; 피연산자에 괄호 없이 사용 되는 메서드의 이름 이어야 합니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 04103fe23ee55bb751d9604ef74614edeead8886
ms.lasthandoff: 03/13/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>'AddressOf' 피연산자에 괄호 없이 사용 되는 메서드의 이름 이어야 합니다.
`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다. 구문은 다음과 같습니다.  
  
 `AddressOf` `procedurename`  
  
 괄호 뒤의 인수를 삽입 `AddressOf`에 불필요 합니다.  
  
 **오류 ID:** BC30577  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  뒤의 인수를 괄호로 제거 `AddressOf`합니다.  
  
2.  인수는 메서드 이름 인지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)

---
title: "대리자 클래스&lt;classname&gt;&quot;에 Invoke 메서드가 있으므로 이러한 종류의 식을 메서드 호출의 대상일 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: ddc5ef0f0b3e9baa58f17dafb727e250c0fba9fd
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>대리자 클래스&lt;classname&gt;'에 Invoke 메서드가 있으므로 이러한 종류의 식을 메서드 호출의 대상일 수 없습니다
에 대 한 호출 `Invoke` 때문에 실패 했습니다 대리자를 통해 `Invoke` 대리자 클래스에서 구현 되지 않았습니다.  
  
 **오류 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  대리자 클래스의 인스턴스는으로 만들어졌는지 확인 한 `Dim` 문과 사용 하 여 대리자 인스턴스에 프로시저를 할당 되어 있는지는 `AddressOf` 연산자입니다.  
  
2.  대리자 클래스를 구현 하는 코드를 찾아 구현 하는지 확인은 `Invoke` 프로시저입니다.  
  
## <a name="see-also"></a>참고 항목  
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)

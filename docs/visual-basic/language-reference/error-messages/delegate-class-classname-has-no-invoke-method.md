---
title: "대리자 클래스 &#39; &lt;classname&gt;&#39;에 Invoke 메서드가 없으므로 이러한 형식의 식은 메서드 호출의 대상일 수 없습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords: BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>대리자 클래스 &#39; &lt;classname&gt;&#39;에 Invoke 메서드가 없으므로 이러한 형식의 식은 메서드 호출의 대상일 수 없습니다
에 대 한 호출 `Invoke` 때문에 실패 했습니다 대리자를 통해 `Invoke` 대리자 클래스에서 구현 되지 않았습니다.  
  
 **오류 ID:** BC30220  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  대리자 클래스의 인스턴스도 만들어졌는지 확인 한 `Dim` 문과 프로시저에 할당을 사용 하 여 대리자 인스턴스는 `AddressOf` 연산자입니다.  
  
2.  구현 합니다를 대리자 클래스를 구현 하는 코드는 `Invoke` 프로시저입니다.  
  
## <a name="see-also"></a>참고 항목  
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)

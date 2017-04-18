---
title: "(Visual Basic) 데이터 형식의 효율적 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
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
ms.openlocfilehash: b81a1c81d970beee32925c3f2fe6ca3bcad79151
ms.lasthandoff: 03/13/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a>데이터 형식의 효율적 사용(Visual Basic)
선언 되지 않은 변수 및 데이터 형식 없이 선언 된 변수에 할당 되는 `Object` 데이터 형식입니다. 이렇게 하면 쉽게 프로그램을 신속 하 게 작성할 수 있지만 더 느리게 실행 될 수 있습니다.  
  
## <a name="strong-typing"></a>강력한 형식  
 모든 변수에 대해 데이터 형식 지정 이라고 *강력한 형식 지정*합니다. 강력한 형식화를 사용 하 여 몇 가지 장점이 있습니다.  
  
-   변수에 대 한 IntelliSense 지원을 수 있습니다. 이렇게 하면 코드를 입력 하면 해당 속성 및 기타 멤버를 볼 수 있습니다.  
  
-   컴파일러에서 형식 검사의 장점은 걸립니다. 이 런타임에 오버플로와 같은 오류로 인해 실패할 수 있는 문을 파악할 수 있습니다. 또한 지원 하지 않는 개체에 메서드 호출을 찾아냅니다.  
  
-   그 결과, 코드의 실행이 빨라집니다.  
  
## <a name="most-efficient-data-types"></a>가장 효율적인 데이터 형식  
 분수를 포함 하지 않은 변수의 정수 계열 데이터 형식은 비정 수 형식 보다 더 효율적입니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` 및 `UInteger` 는 가장 효율적인 숫자 형식입니다.  
  
 소수에 `Double` 은 가장 효율적인 데이터 형식이 고, 현재 플랫폼의 프로세서 배정밀도의 부동 소수점 작업을 수행 합니다. 그러나 작업과 `Double` 과 같은 정수 계열 형식에서와 마찬가지로 빠르지 않습니다 `Integer`합니다.  
  
## <a name="specifying-data-type"></a>데이터 형식 지정  
 사용 하 여는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) 특정 형식의 변수를 선언 합니다. 액세스 수준을 사용 하 여 동시에 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [친구](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 다음 예제에서와 같이 키워드입니다.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>문자 변환  
 `AscW` 및 `ChrW` 함수는 유니코드에서 작동 합니다. 항상 사용 해야 `Asc` 및 `Chr`, 변환이 필요로 하는 내부 및 외부로 유니코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [IntelliSense 사용](https://docs.microsoft.com/visualstudio/ide/using-intellisense)

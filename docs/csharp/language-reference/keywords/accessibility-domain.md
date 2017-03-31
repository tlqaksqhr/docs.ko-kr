---
title: "액세스 가능 도메인(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c7f575aa65680ccc886ac0246c589a8cac1302d7
ms.lasthandoff: 03/13/2017

---
# <a name="accessibility-domain-c-reference"></a>액세스 가능 도메인(C# 참조)
멤버의 액세스 가능 도메인은 멤버가 참조될 수 있는 프로그램 섹션을 지정합니다. 멤버가 다른 형식 내에 중첩되면 해당 액세스 가능 도메인은 멤버의 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 한 수준 위 형식의 액세스 가능 도메인에 의해 결정됩니다.  
  
 최상위 형식의 액세스 가능 도메인은 최소한 최상위 형식이 선언된 프로젝트의 프로그램 텍스트입니다. 즉, 도메인에는 이 프로젝트의 모든 소스 파일이 포함됩니다. 중첩 형식의 액세스 가능 도메인은 최소한 중첩 형식이 선언된 프로젝트의 프로그램 텍스트입니다. 즉, 도메인은 모든 중첩 형식이 포함된 형식 본문입니다. 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 초과하지 않습니다. 다음 예제에서는 이러한 개념을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에는 최상위 형식 `T1`과 두 개의 중첩 클래스 `M1` 및 `M2`가 포함됩니다. 클래스에는 여러 가지 선언된 액세스 가능성을 가진 필드가 포함됩니다. `Main` 메서드에서 각 문 뒤에는 각 멤버의 액세스 가능성 도메인을 나타내는 주석이 있습니다. 액세스할 수 없는 멤버를 참조하려고 하는 문은 주석으로 처리됩니다. 액세스할 수 없는 멤버를 참조함으로써 발생한 컴파일러 오류를 확인하려면 한 번에 하나씩 주석을 제거합니다.  
  
 [!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [액세스 가능성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

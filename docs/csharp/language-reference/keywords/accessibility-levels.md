---
title: "액세스 가능성 수준(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 796802a407c486c1df5332d5b4920467f3a1171b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-levels-c-reference"></a>액세스 가능성 수준(C# 참조)
액세스 한정자 [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 [private](../../../csharp/language-reference/keywords/private.md)을 사용하여 멤버에 대한 다음 선언된 액세스 가능성 수준 중 하나를 지정합니다.  
  
|선언된 액세스 가능성|의미|  
|----------------------------|-------------|  
|`public`|액세스가 제한되지 않습니다.|  
|`protected`|액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.|  
|`internal`|액세스가 현재 어셈블리로 제한됩니다.|  
|`protected internal`|액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.|  
|`private`|액세스가 포함하는 형식으로 제한됩니다.|  
  
 `protected internal` 조합을 사용할 경우를 제외하고 멤버 또는 형식에는 액세스 한정자가 하나만 허용됩니다.  
  
 네임스페이스에는 액세스 한정자가 허용되지 않습니다. 네임스페이스에는 액세스 제한이 없습니다.  
  
 멤버 선언이 발생한 컨텍스트에 따라 특정 선언된 액세스 가능성만 허용됩니다. 액세스 한정자가 멤버 선언에서 지정되지 않으면 기본 액세스 가능성이 사용됩니다.  
  
 다른 형식에 중첩되지 않은 최상위 형식에는 `internal` 또는 `public` 액세스 가능성만 포함될 수 있습니다. 이러한 형식에 대한 기본 액세스 가능성은 `internal`입니다.  
  
 다음 표에 나와 있는 대로 다른 형식의 멤버인 중첩 형식에는 선언된 액세스 가능성이 포함될 수 있습니다.  
  
|소속 그룹|기본 멤버 액세스 가능성|멤버의 허용된 선언된 액세스 가능성|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|없음|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal`|  
|`interface`|`public`|없음|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 중첩된 형식의 액세스 가능성은 액세스 가능 도메인에 따라 다릅니다. [액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)은 멤버에 대해 선언된 액세스 가능성 및 한 수준 위 형식의 액세스 가능성 도메인에 의해 결정됩니다. 그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md)   
 [액세스 가능성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)


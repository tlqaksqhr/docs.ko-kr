---
title: "public(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e2d6350b6c7c2490d42d08ebd169a35b40d20900
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="public-c-reference"></a>public(C# 참조)
`public` 키워드는 형식 및 형식 멤버에 대한 액세스 한정자입니다. 공용 액세스는 허용 범위가 가장 큰 액세스 수준입니다. 다음 예제와 같이, 공용 멤버 액세스에 대한 제한은 없습니다.  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) 및 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 클래스, `PointTest` 및 `MainClass`를 선언합니다. `PointTest`의 공용 멤버 `x` 및 `y`는 `MainClass`에서 직접 액세스합니다.  
  
 [!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 `public` 액세스 수준을 [private](../../../csharp/language-reference/keywords/private.md) 또는 [protected](../../../csharp/language-reference/keywords/protected.md)로 변경하면 오류 메시지가 표시됩니다.  
  
 보호 수준 때문에 'PointTest.y'에 액세스할 수 없습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

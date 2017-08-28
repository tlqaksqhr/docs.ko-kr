---
title: "제네릭 코드의 default 키워드(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
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
ms.openlocfilehash: b5f5995b720d377717a5fff8a5e7e6e2196c612c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="default-keyword-in-generic-code-c-programming-guide"></a>제네릭 코드의 default 키워드(C# 프로그래밍 가이드)
제네릭 클래스 및 메서드에서 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수가 있는 형식 T에 기본값을 할당하는 방법에 대한 문제가 발생합니다.  
  
-   T가 참조 형식인지 값 형식인지 여부  
  
-   T가 값 형식인 경우 숫자 값인지 구조체인지 여부  
  
 매개 변수가 있는 형식 T의 변수 t를 고려할 때, t = null 문은 T가 참조 형식인 경우에만 유효하고 t = 0은 구조체가 아닌 숫자 값 형식에만 사용할 수 있습니다. 참조 형식에 대해서는 null을 반환하고 숫자 값 형식에는 0을 반환하는 `default` 키워드를 사용하면 이 문제를 해결할 수 있습니다. 구조체에 대해서는 멤버가 값 형식인지 참조 형식인지 여부에 따라 0 또는 null로 초기화된 구조체의 각 멤버가 반환됩니다. Nullable 값 형식의 경우, 기본값은 <xref:System.Nullable%601?displayProperty=fullName>을 반환하며 이는 여느 구조체와 마찬가지로 초기화됩니다.  
  
 `GenericList<T>` 클래스에 있는 다음 예제에서는 `default` 키워드를 사용하는 방법을 보여 줍니다. 자세한 내용은 [제네릭 개요](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하세요.  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../csharp/programming-guide/generics/index.md)   
 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)   
 [제네릭](~/docs/standard/generics/index.md)


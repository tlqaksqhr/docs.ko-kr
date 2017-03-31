---
title: "get(C# 참조) | Microsoft 문서"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
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
ms.openlocfilehash: cdd3107a9e23e2f41a412390c8a723d4366e3952
ms.lasthandoff: 03/13/2017

---
# <a name="get-c-reference"></a>get(C# 참조)

`get` 키워드는 속성 값 또는 인덱서 요소를 반환하는 속성 또는 인덱서의 *accessor* 메서드를 정의합니다. 자세한 내용은 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md), [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [인덱서](../../../csharp/programming-guide/indexers/indexmd)를 참조하세요.  
  
다음 예제에서는 `Seconds`라는 속성의 `get` 및 `set` 접근자를 둘 다 정의합니다. `_seconds`라는 private 필드를 사용하여 속성 값을 지원합니다.  
 
 [!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
대체로 `get` 접근자는 앞의 예제와 마찬가지로 값을 반환하는 단일 문으로 구성됩니다. C# 7부터 `get` 접근자를 식 본문 멤버로 구현할 수 있습니다. 다음 예제에서는 `get` 및 `set` 접근자 둘 다를 식 본문 멤버로 구현합니다.

 [!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
속성의 `get` 및 `set` 접근자가 private 지원 필드의 값 설정 또는 검색 이외의 다른 작업을 수행하지 않는 간단한 사례의 경우 자동 구현 속성에 대한 C# 컴파일러의 지원을 활용할 수 있습니다. 다음 예제에서는 `Hours`를 자동 구현 속성으로 구현합니다. 
  
 [!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양

 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)


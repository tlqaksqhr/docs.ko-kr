---
title: "value(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: value_CSharpKeyword
helpviewer_keywords: value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2501bc8964ed76534dba6c7cc519e095c57cb898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-c-reference"></a>value(C# 참조)
상황별 키워드 `value`는 일반 속성 선언의 set 접근자에 사용됩니다. 메서드의 입력 매개 변수와 비슷합니다. `value` 단어는 클라이언트 코드가 속성에 할당하려고 시도하는 값을 참조합니다. 다음 예에서 `MyDerivedClass`에는 `Name`이라는 속성이 있습니다. 이 속성은 `value` 매개 변수를 사용하여 지원 필드 `name`에 새 문자열을 할당합니다. 클라이언트 코드의 관점에서 이 작업은 단순한 할당으로 기록됩니다.  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 `value` 사용에 대한 자세한 내용은 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)을 참조하세요.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)

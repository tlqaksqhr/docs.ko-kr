---
title: do(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do(C# 참조)
`do` 문은 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행합니다. 루프의 본문이 단일 문으로 구성되지 않은 경우 중괄호(`{}`)로 묶어야 합니다. 이 경우 중괄호는 선택 사항입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `x` 변수가 5보다 작은 한 `do-while` 루프 문이 실행됩니다.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 [while](../../../csharp/language-reference/keywords/while.md) 문과 달리 `do-while` 루프는 조건식이 계산되기 전에 한 번 실행됩니다.  
  
 `do-while` 블록의 어느 지점에서나 [break](../../../csharp/language-reference/keywords/break.md) 문을 사용하여 루프를 중단할 수 있습니다. [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용하여 `while` 식 계산 문을 직접 실행할 수 있습니다. `while` 식이 true로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다. 식이 false로 계산될 경우 `do-while` 루프 다음의 첫 번째 문에서 계속 실행됩니다.  
  
 또한 `do-while` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 종료할 수 있습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [do-while 문(C++)](/cpp/cpp/do-while-statement-cpp)  
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)

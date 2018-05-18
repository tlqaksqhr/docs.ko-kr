---
title: while(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a>while(C# 참조)
`while` 문은 지정된 식이 `false`로 평가될 때까지 문 또는 문의 블록을 실행합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>예  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>예  
 루프의 각 실행 전에 `while` 식의 테스트가 수행되므로 `while` 루프는 0번 이상 실행됩니다. 이는 한 번 이상 실행되는 [do](../../../csharp/language-reference/keywords/do.md) 루프와 다릅니다.  
  
 `while` 루프는 [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문이 루프 외부로 제어를 전송할 때 종료될 수 있습니다. 루프를 종료하지 않고 다음 반복으로 제어를 전달하려면 [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용합니다. `int n`의 증가에 따라 이전의 세 예제에서 출력이 달라지는 것을 확인하세요. 아래의 예제에서는 출력이 생성되지 않습니다.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [while 문(C++)](/cpp/cpp/while-statement-cpp)  
 [반복 문](../../../csharp/language-reference/keywords/iteration-statements.md)

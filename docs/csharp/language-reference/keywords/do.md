---
title: do(C# 참조)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 89c13f5b547c13052e229ff6eb3a39ae5babce41
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932389"
---
# <a name="do-c-reference"></a>do(C# 참조)

`do` 문은 지정된 부울 식이 `true`로 평가되는 동안 명령문 또는 명령문 블록을 실행합니다. 이 식은 각 루프 실행 후 평가되기 때문에 `do-while` 루프가 한 번 이상 실행됩니다. 이는 0번 이상 실행되는 [while](while.md) 루프와 다릅니다.

`do` 문 블록 내의 어느 지점에서나 [break](break.md) 문을 사용하여 루프를 중단할 수 있습니다.

[continue](continue.md) 문을 사용하여 `while` 식의 계산을 직접 실행할 수 있습니다. 식이 `true`로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다. 그렇지 않으면 실행은 루프 뒤에 나오는 첫 번째 문에서 계속됩니다.

[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `do-while` 루프를 종료할 수도 있습니다.

## <a name="example"></a>예

다음 예제에서는 `do` 문의 사용법을 보여 줍니다. **Run**을 선택하여 예제 코드를 실행합니다. 그런 다음, 코드를 수정하고 다시 실행할 수 있습니다.

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a>C# 언어 사양

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)  
- [C# 프로그래밍 가이드](../../programming-guide/index.md)  
- [C# 키워드](index.md)  
- [do-while 문(C++)](/cpp/cpp/do-while-statement-cpp)  
- [반복 문](iteration-statements.md)  
- [while 문](while.md)  

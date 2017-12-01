---
title: "foreach, in(C# 참조)"
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a>foreach, in(C# 참조)
`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 배열 또는 개체 컬렉션의 각 요소에 대해 포함 문의 그룹을 반복합니다. `foreach` 문을 컬렉션을 반복하여 원하는 정보를 가져오는 데 사용되지만 예측할 수 없는 결과를 방지하지 위해 소스 컬렉션에서 항목을 추가하거나 제거하는 데 사용할 수는 없습니다. 소스 컬렉션에서 항목을 추가하거나 제거해야 하는 경우 [for](for.md) 루프를 사용하세요.
  
 포함된 문은 배열이나 컬렉션의 각 요소에 대해 계속 실행됩니다. 컬렉션의 모든 요소에 대해 반복이 완료되면 제어가 `foreach` 블록 다음 문으로 전달됩니다.
  
 `foreach` 블록 내 원하는 지점에서 [break](break.md) 키워드를 사용하여 루프를 중단하거나 [continue](continue.md) 키워드를 사용하여 루프의 다음 반복을 단계 실행할 수 있습니다.

 또한 `foreach` 루프는 [goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 종료할 수 있습니다.

 `foreach` 키워드 및 코드 샘플에 대한 자세한 내용은 다음 항목을 참조하세요.  

 [배열에 foreach 사용](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [방법: foreach를 사용하여 컬렉션 클래스 액세스](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>예제
 다음 코드는 세 가지 예제를 보여줍니다.

> [!TIP]
> 구문을 사용 하 여 실험 및 사용 사례에 비슷한 다른 용도로 시도 하기 위해 예제를 수정할 수 있습니다. "코드를 실행 하려면" 실행 키를 누릅니다. 다음 편집 하며 키를 눌러 ""을 다시 실행 합니다.

-   정수 배열의 내용을 표시하는 일반적인 `foreach` 루프

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   동일한 작업을 수행하는 [for](../../../csharp/language-reference/keywords/for.md) 루프

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   배열의 요소 수를 유지 관리하는 `foreach` 루프

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>C# 언어 사양
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목  

[C# 참조](../index.md)

[C# 프로그래밍 가이드](../../programming-guide/index.md)

[C# 키워드](index.md)

[반복 문](iteration-statements.md)

[for](for.md)

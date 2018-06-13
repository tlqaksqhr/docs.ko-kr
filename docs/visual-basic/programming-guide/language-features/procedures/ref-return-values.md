---
title: Ref 반환 값 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2979359f0ffafe46a62696485bbb87b211c1704
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651243"
---
# <a name="support-for-reference-return-values-visual-basic"></a>참조 반환 값 (Visual Basic)에 대 한 지원

C# 언어에서 지 원하는 C# 7.0 부터는 *반환 값을 참조*합니다. 참조 반환 값을 이해 하는 한 가지 방법은 이들이 반대 메서드에 참조로 전달 되는 인수입니다. 참조로 전달 되는 인수를 수정한 경우 변경 내용은 호출자에 변수 값에 반영 됩니다. 메서드를 호출자에 게 참조 반환 값을 제공 하는 경우 수정 내용 참조 반환 값에는 호출자가 호출된 된 메서드의 데이터에 반영 됩니다.

Visual Basic 참조를 사용 하 여 만든 메서드 수 값을 반환 하지만 참조 반환 값을 사용할 수 있습니다 수를 허용 하지 않습니다. 즉, 참조 반환 값을 사용 하 여 메서드를 호출 하 고 해당 반환 값을 수정할 수 있습니다 및 참조 반환 값을 변경 하는 호출된 된 메서드의 데이터에 반영 됩니다.

## <a name="modifying-the-ref-return-value-directly"></a>Ref 반환 값을 직접 수정

항상 실패 하 고 없는 있는 메서드에 대 한 `ByRef` 매개 변수를 직접 참조 반환 값을 수정할 수 있습니다. 참조 반환 값을 반환 하는 식에 새 값을 할당 하 여이 작업을 수행 합니다. 

다음 C# 예제에서는 정의 `NumericValue.IncrementValue` 메서드 내부 값이 증가 하 고 참조로 반환 하는 값을 반환 합니다. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

참조 값이 다음 Visual Basic 예에서 호출자에 의해 수정 다음 반환 합니다. 한 줄으로는 `NumericValue.IncrementValue` 메서드 호출 메서드에 값을 할당 하지 않습니다. 대신, 메서드에 의해 반환 되는 참조 반환 값에 값을 할당 합니다.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>도우미 메서드를 사용 하 여

다른 경우에는 메서드 호출의 참조 반환 값을 직접 수정 항상 않을 것이 좋습니다. 예를 들어 문자열을 반환 하는 검색 방법 찾을 수 없습니다 항상 일치 합니다. 이 경우 검색은 성공 하는 경우에 참조 반환 값을 수정 하려면.

다음 C# 예제에서는이 시나리오를 보여 줍니다. 정의 `Sentence` C#으로 작성 된 클래스를 포함 한 `FindNext` 메서드를 지정된 된 부분 문자열으로 시작 하는 문장 내에서 다음 단어를 찾습니다. 문자열은 참조 반환 값으로 반환되며, 메서드에 참조로 전달된 `Boolean` 변수는 검색에 성공했는지 여부를 나타냅니다. 참조 반환 값은 호출자에 게 없습니다 읽을 수만 있는지; 반환된 된 값을 나타냅니다. 자신이 수도 수정 하 고 수정 내용이 내부적으로 포함 된 데이터에 반영 되는 `Sentence` 클래스입니다.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

참조를 직접 수정 반환 값이 예제의 하지 않으므로 신뢰할 수 있는 일치 하는 것을 문장에 있는 첫 번째 단어를 반환 합니다. 메서드 호출이 실패할 수 있습니다. 이 경우 호출자는 실수로 문장의 첫 번째 단어를 수정 합니다. 이 문제를 방지할 수를 반환 하는 호출자가는 `null` (또는 `Nothing` Visual basic에서). 이 경우 값이 인 문자열을 수정 하려고 하지만 `Nothing` throw 한 <xref:System.NullReferenceException>합니다. 호출자에 게 반환 하 여 문제를 방지할 수 또한 경우 <xref:System.String.Empty?displayProperty=nameWithType>, 그러나이 경우 호출자에 게 해당 값이 문자열 변수를 정의 하는 <xref:System.String.Empty?displayProperty=nameWithType>합니다. 호출자에 게 해당 문자열을 수정할 수, 하는 동안 자체 수정 어떠한 기능도 수행, 이후 수정된 된 문자열에에서 관계가 없는 단어를 저장 하 여 문장을 `Sentence` 클래스입니다.

이 시나리오를 처리 하는 가장 좋은 방법은 참조 도우미 메서드를 통해 참조 반환 값을 전달 하는 합니다. 그런 다음 도우미 메서드는 지 확인 하는 메서드 호출에 성공, 팩트 테이블 수정 참조 값을 반환 하는 논리를 포함 합니다. 다음 예제에서는 가능한 구현을 제공합니다.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>참고자료

[값 및 참조로 인수 전달](passing-arguments-by-value-and-by-reference.md)   
[Visual Basic의 프로시저](index.md)   



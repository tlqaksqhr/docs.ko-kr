---
title: "Yield 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bc2f5c2dca1fbd6039f10ddd6204673f60a679d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="yield-statement-visual-basic"></a>Yield 문(Visual Basic)
컬렉션의 다음 요소로 보냅니다는 `For Each...Next` 문.  
  
## <a name="syntax"></a>구문  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|용어|정의|  
|---|---|  
|`expression`|필수. 반복기 함수 형식으로 암시적으로 변환 될 수 있는 식 또는 `Get` 접근자를 포함 하는 `Yield` 문.|  
  
## <a name="remarks"></a>설명  
 `Yield` 문을 한 번에 컬렉션의 요소를 하나를 반환 합니다. `Yield` 문이 반복기 함수에 포함 되는지 또는 `Get` 컬렉션에 대해 사용자 지정 반복을 수행 하는 접근자입니다.  
  
 반복기 함수를 사용 하 여 소비는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 또는 LINQ 쿼리입니다. 각 반복에서 `For Each` 루프 반복기 함수를 호출 합니다. 경우는 `Yield` 문이 반복기 함수에 도달 하면 `expression` 반환 되 고 코드에서 현재 위치는 유지 됩니다. 다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 형식에서 암시적 변환이 있어야 합니다. `expression` 에 `Yield` 문을 반복기의 반환 형식에 있습니다.  
  
 사용할 수는 `Exit Function` 또는 `Return` 문을 반복을 끝내 세요.  
  
 "생성"는 예약어 아니며에 사용 되는 경우에 특별 한 의미가 있는 `Iterator` 함수 또는 `Get` 접근자입니다.  
  
 반복기 함수에 대 한 자세한 내용은 및 `Get` 접근자 참조 [반복기](../../programming-guide/concepts/iterators.md)합니다.  
  
## <a name="iterator-functions-and-get-accessors"></a>반복기 함수 및 Get 접근자  
 반복기 함수 선언 또는 `Get` 접근자에는 다음 요구 사항을 충족 해야 합니다.  
  
-   여기에 포함 해야 합니다는 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자입니다.  
  
-   반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>여야 합니다.  
  
-   포함할 수 없다는 것 `ByRef` 매개 변수입니다.  
  
 반복기 함수는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.  
  
 반복기 함수는 익명 함수를 수 있습니다. 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.  
  
## <a name="exception-handling"></a>예외 처리  
 A `Yield` 문 내에 있을 수는 `Try` 블록는 [시도 중... Catch 하는 중... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다. A `Try` 블록은 `Yield` 문의 `Catch` 을 차단 하 고 있을 수 있습니다는 `Finally` 블록입니다.  
  
 A `Yield` 문 내에 있을 수 없습니다는 `Catch` 블록 또는 `Finally` 블록입니다.  
  
 경우는 `For Each` 본문 (반복기 함수) 외부 예외를 throw 하지는 `Catch` 블록에 반복기 함수가 실행 되지 않으며 하지만 `Finally` 반복기 함수에는 블록이 실행 됩니다. A `Catch` 반복기 함수 내의 블록 반복기 함수 내에서 발생 하는 예외만을 catch 합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 다음에는 반환 코드는 `IEnumerable (Of String)` 반복기 함수에서 다음의 요소 반복는 `IEnumerable (Of String)`합니다.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 에 대 한 호출 `MyIteratorFunction` 함수 본문을 실행 하지 않습니다. 대신에 `IEnumerable(Of String)` 변수에 `elements`을 반환합니다.  
  
 `For Each` 루프 반복에서 <xref:System.Collections.IEnumerator.MoveNext%2A>에 대한 `elements` 메서드가 호출됩니다. 이 호출은 다음 `MyIteratorFunction` 문에 도달할 때까지 `Yield` 본문을 실행합니다. `Yield` 뿐만 아니라의 값을 결정 하는 식을 반환 하는 명령문은 `element` 루프 본문에서 소비 하기 위한 변수 뿐만 아니라는 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 요소, 즉는 `IEnumerable (Of String)`합니다.  
  
 이후에 `For Each` 루프가 반복될 때마다 중지되었던 위치에서 반복기 본문 실행이 계속되고 `Yield` 문에 도달하면 다시 중지됩니다. `For Each` 루프를 완료 하는 경우 반복기 함수의 끝 또는 `Return` 또는 `Exit Function` 문에 도달 하면 합니다.  
  
## <a name="example"></a>예  
 다음 예제에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다. 각 반복에서 [각각에 대해](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 문 본문에서 `Main` 에 대 한 호출을 만듭니다는 `Power` 반복기 함수입니다. 반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.  
  
 반복기 메서드의 반환 형식이 <xref:System.Collections.Generic.IEnumerable%601>, 반복기 인터페이스 형식이 있습니다. 반복기 메서드가 호출되면 숫자의 거듭제곱이 들어 있는 열거형 개체를 반환합니다.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a>예  
 다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다. 속성 선언에 포함 되어는 `Iterator` 한정자입니다.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 추가 예제를 참조 하십시오. [반복기](../../programming-guide/concepts/iterators.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문](../../../visual-basic/language-reference/statements/index.md)

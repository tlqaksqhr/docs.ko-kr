---
title: Null 조건부 연산자(C# 및 Visual Basic)
ms.date: 04/03/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 28cf2633d74f047a751ffdad11f1e1db8328cd6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457802"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. 및 ?[] Null 조건부 연산자(C# 및 Visual Basic)
멤버 액세스(`?.`) 또는 인덱스(`?[]`) 작업을 수행하기 전에 Null에서 왼쪽 피연산자의 값을 테스트합니다. 왼쪽 피연산자가 `null`로 계산하는 경우 `null`을 반환합니다. 

이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Null 조건부 연산자는 단락 연산자입니다.  조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 null을 반환하면 체인 실행의 나머지 부분이 중지됩니다.  다음 예제에서 `E`는 `A`, `B` 또는 `C`가 Null로 평가되는 경우 실행되지 않습니다.
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 또한 Null 조건부 멤버 액세스는 훨씬 더 적은 코드를 사용하여 스레드로부터 안전한 방식으로 대리자를 호출하는 데 사용됩니다.  이전 방식에서는 다음과 같은 코드가 필요합니다.  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 새로운 방식은 훨씬 더 간단합니다.  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

```vb
PropertyChanged?.Invoke(…)
```  
  
 새로운 방식은 컴파일러가 `PropertyChanged`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다. null 조건부 대리자 호출 구문 `PropertyChanged?(e)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.  
  
## <a name="language-specifications"></a>언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 자세한 내용은 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [??(Null 병합 연산자)](null-coalescing-operator.md)  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)

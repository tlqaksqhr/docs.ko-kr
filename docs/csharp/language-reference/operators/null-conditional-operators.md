---
title: "Null 조건부 연산자(C# 및 Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95b4079cf4e71c0ef9cd436ec230337f512229a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="null-conditional-operators-c-and-visual-basic"></a>Null 조건부 연산자(C# 및 Visual Basic)
멤버 액세스(`?.`) 또는 인덱스(`?[`) 작업을 수행하기 전에 null을 테스트하는 데 사용됩니다.  이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.  
  
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
  
 마지막 예제에서는 null 조건 연산자가 단락임을 보여 줍니다.  조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 null을 반환하면 체인 실행의 나머지 부분이 중지됩니다.  식에서 우선 순위가 낮은 다른 작업은 계속됩니다.  예를 들어 다음 식에서 `E`는 두 번째 줄에서 실행되고 `??` 및 `==` 작업이 실행됩니다.  첫 번째 줄에서 `??`는 주기를 단축하고 `E`는 왼쪽이 null이 아닌 값으로 평가되면 실행되지 않습니다.
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 또한 null 조건 멤버 액세스는 훨씬 더 적은 코드를 사용하여 스레드로부터 안전한 방식으로 대리자를 호출하는 데 사용됩니다.  이전 방식에서는 다음과 같은 코드가 필요합니다.  
  
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
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 새로운 방식은 컴파일러가 `PropertyChanged`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.  
  
 null 조건부 대리자 호출 구문 `PropertyChanged?(e)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.  허용하는 모호한 구문 분석 상황이 너무 많습니다.  
  
## <a name="language-specifications"></a>언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 자세한 내용은 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [?? (null 병합 연산자)](null-conditional-operator.md)  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)  
 [Visual Basic 프로그래밍 가이드](../../../visual-basic/programming-guide/index.md)

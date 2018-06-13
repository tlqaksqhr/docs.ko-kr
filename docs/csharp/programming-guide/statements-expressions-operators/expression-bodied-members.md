---
title: 식 본문 멤버(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 800280ed9ceaf69b825bb2a3c2c3d0d5f829922d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332756"
---
# <a name="expression-bodied-members-c-programming-guide"></a>식 본문 멤버(C# 프로그래밍 가이드)
식 본문 정의를 사용하면 간결하고 읽을 수 있는 형식으로 멤버 구현을 제공할 수 있습니다. 메서드 또는 속성과 같은 지원되는 멤버에 대한 논리가 단일 식으로 구성된 경우 식 본문 정의를 사용할 수 있습니다. 식 본문 정의의 일반 구문은 다음과 같습니다.

```csharp
member => expression;
```

여기서 *expression*은 유효한 식입니다. 

C# 6에서는 메서드 및 속성 가져오기 접근자에 대해 식 본문 정의 지원이 도입되었으며 C# 7.0에서는 지원이 확장되었습니다. 다음 표에 나열된 형식 멤버와 함께 식 본문 정의를 사용할 수 있습니다. 

|멤버  |지원 버전 |
|---------|---------|
|[메서드](#methods)  |C# 6 |
|[생성자](#constructors)   |C# 7.0 |
|[종료자](#finalizers)     |C# 7.0 |
|[속성 가져오기](#property-get-statements)  |C# 6 |
|[속성 설정](#property-set-statements)  |C# 7.0 |
|[인덱서](#indexers)       |C# 7.0 |

## <a name="methods"></a>메서드

식 본문 메서드는 형식이 메서드의 반환 형식과 일치하는 값을 반환하거나 `void`를 반환하는 메서드의 경우 일부 작업을 수행하는 단일 식으로 구성됩니다. 예를 들어 <xref:System.Object.ToString%2A> 메서드를 재정의하는 형식에는 일반적으로 현재 개체의 문자열 표현을 반환하는 단일 식이 포함되어 있습니다. 

다음 예제에<xref:System.Object.ToString%2A> 메서드를 식 본문 정의로 재정의하는 `Person` 클래스를 정의합니다. 또한 이름을 콘솔에 표시하는 `Show` 메서드를 정의합니다. `return` 키워드는 `ToString` 식 본문 정의에 사용되지 않습니다.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

자세한 내용은 [메서드(C# 프로그래밍 가이드)](../classes-and-structs/methods.md)를 참조하세요.
 
## <a name="constructors"></a>생성자

생성자에 대한 식 본문 정의는 일반적으로 생성자의 인수를 처리하거나 인스턴스 상태를 초기화하는 단일 할당 식 또는 메서드 호출로 구성됩니다. 

다음 예제에서는 생성자에 *name*이라는 단일 문자열 매개 변수가 있는 `Location` 클래스를 정의합니다. 식 본문 정의에서 `Name` 속성에 인수를 할당합니다.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

자세한 내용은 [생성자(C# 프로그래밍 가이드)](../classes-and-structs/constructors.md)를 참조하세요.

## <a name="finalizers"></a>종료자

종료자에 대한 식 본문 정의에는 일반적으로 관리되지 않는 리소스를 해제하는 문 등의 정리 문이 포함되어 있습니다.

다음 예제에서는 식 본문 정의를 사용하여 종료자가 호출되었음을 나타내는 종료자를 정의합니다.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

자세한 내용은 [종료자(C# 프로그래밍 가이드)](../classes-and-structs/destructors.md)를 참조하세요.

## <a name="property-get-statements"></a>속성 가져오기 문

속성 가져오기 접근자를 직접 구현하려는 경우 단순히 속성 값을 반환하는 단일 식에 대해 식 본문 정의를 사용할 수 있습니다. `return` 문은 사용되지 않습니다.

다음 예제에서는 `Location.Name` 속성을 정의합니다. 이 속성의 속성 가져오기 접근자는 해당 속성을 지원하는 private `locationName` 필드의 값을 반환합니다. 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

식 본문 정의를 사용하는 읽기 전용 속성은 명시적 `set` 문 없이 구현할 수 있습니다. 사용되는 구문은 다음과 같습니다.

```csharp
PropertyName => returnValue;
```

다음 예제에서는 `Location` 클래스를 정의합니다. 이 클래스의 읽기 전용 `Name` 속성은 private `locationName` 필드의 값을 반환하는 식 본문 정의로 구현됩니다.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.

## <a name="property-set-statements"></a>속성 설정 문

속성 설정 접근자를 직접 구현하려는 경우 속성을 지원하는 필드에 값을 할당하는 한 줄 식에 대해 식 본문 정의를 사용할 수 있습니다.

다음 예제에서는 `Location.Name` 속성을 정의합니다. 이 속성의 속성 설정 문은 해당 속성을 지원하는 private `locationName` 필드에 입력 인수를 할당합니다.

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

자세한 내용은 [속성(C# 프로그래밍 가이드)](../classes-and-structs/properties.md)을 참조하세요.

## <a name="indexers"></a>인덱서

속성과 마찬가지로, get 접근자가 값을 반환하는 단일 문으로 구성되거나 set 접근자가 단순 할당을 수행하는 경우 인덱서의 get 및 set 접근자는 식 본문 정의로 구성됩니다.

다음 예제에서는 다양한 스포츠의 이름이 포함된 내부 <xref:System.String> 배열을 포함하는 `Sports`라는 클래스를 정의합니다. 인덱서의 get 및 set 접근자는 둘 다 식 본문 정의로 구현됩니다.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

자세한 내용은 [인덱서(C# 프로그래밍 가이드)](../indexers/index.md)를 참조하세요.


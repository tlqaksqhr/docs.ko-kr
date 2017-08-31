---
title: "참조 반환 값 및 참조 로컬(C# 가이드)"
description: "참조 반환 및 참조 로컬 값을 정의하고 사용하는 방법을 알아봅니다."
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.translationtype: HT
ms.sourcegitcommit: 4582cb0ee091526423cce3fc1d8243029f34f59c
ms.openlocfilehash: 3f2ee35db5b77efcce629b6315060a723429b19c
ms.contentlocale: ko-kr
ms.lasthandoff: 08/16/2017

---
# <a name="ref-returns-and-ref-locals"></a>참조 반환 및 참조 로컬

C# 7부터 C#에서 참조 반환 값(ref return)을 지원합니다. 참조 반환 값을 사용하면 메서드가 값이 아니라 개체 참조를 호출자에게 다시 반환할 수 있습니다. 그러면 호출자가 값이나 참조로 반환된 것처럼 반환된 개체를 처리하도록 선택할 수 있습니다. 호출자가 값이 아니라 참조로 처리하는 참조로 반환된 값은 참조 로컬입니다.

## <a name="what-is-a-reference-return-value"></a>참조 반환 값이란?

대부분의 개발자는 호출된 메서드에 인수를 *참조로* 전달하는 데 익숙합니다. 호출된 메서드의 인수 목록에는 참조로 전달된 값이 포함되며, 호출된 메서드가 해당 값을 변경할 경우 변경 내용이 호출자에게 반환됩니다. *참조 반환 값*은 그 반대입니다.

- 전달된 인수가 아니라 호출된 메서드의 반환 값이 참조입니다.

- 호출된 메서드가 아니라 호출자가 메서드에 의해 반환된 값을 수정할 수 있습니다.

- 호출자의 개체 상태에 반영되는 인수 수정 대신, 호출자의 메서드 반환 값 수정은 해당 메서드가 호출된 개체 상태에 반영됩니다.

참조 반환 값은 더욱 간단한 코드를 생성할 수 있을 뿐만 아니라 개체가 호출자에게 중요한 배열 요소 등의 개별 데이터 항목만 공개하도록 할 수 있습니다. 이렇게 하면 호출자가 개체 상태를 실수로 수정할 가능성이 줄어듭니다.

메서드가 참조 반환 값으로 반환할 수 있는 값에는 몇 가지 제한 사항이 있습니다. 여기에는 다음이 포함됩니다.

- 반환 값은 `void`일 수 없습니다. `void` 참조 반환 값으로 메서드를 정의하려고 하면 컴파일러 오류 CS1547, “이 컨텍스트에는 ‘void’ 키워드를 사용할 수 없습니다.”가 생성됩니다.
 
- 반환 값은 반환하는 메서드의 지역 변수일 수 없습니다. 범위가 반환하는 메서드를 벗어나야 합니다. 클래스의 인스턴스 또는 정적 필드이거나 메서드에 전달된 인수일 수 있습니다. 지역 변수를 반환하려고 하면 컴파일러 오류 CS8168, “’obj’ 로컬은 참조 로컬이 아니므로 참조로 반환할 수 없습니다.”가 생성됩니다.

- 반환 값은 `null`일 수 없습니다. `null`을 반환하려고 하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.

   참조 반환을 사용한 메서드에서 null 값을 반환해야 하는 경우 참조 형식에 대해 null(인스턴스화되지 않은) 값을 반환하거나 값 형식에 대해 [nullable 형식](../nullable-types/index.md)을 반환할 수 있습니다.
 
- 반환 값은 상수, 열거형 멤버, `class` 또는 `struct`의 속성일 수 없습니다. 이러한 값을 반환하려고 하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.

또한 비동기 메서드는 실행을 마치기 전에 반환할 수 있으므로, 해당 반환 값을 여전히 알 수 없는 동안 비동기 메서드에서는 참조 반환 값이 허용되지 않습니다.
 
## <a name="defining-a-ref-return-value"></a>참조 반환 값 정의

메서드 시그니처의 반환 형식에 [ref](../../language-reference/keywords/ref.md) 키워드를 추가하여 참조 반환 값을 정의합니다. 예를 들어 다음 시그니처는 `GetContactInformation` 속성이 `Person` 개체에 대한 참조를 호출자에게 반환함을 나타냅니다.

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

또한 메서드 본문의 각 [return](../../language-reference/keywords/return.md) 문에서 반환되는 개체의 이름 앞에는 [ref](../../language-reference/keywords/ref.md) 키워드가 와야 합니다. 예를 들어 다음 `return` 문은 `p`라는 `Person` 개체를 참조로 반환합니다.

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>참조 반환 값 사용

호출자는 다음 두 가지 방법 중 하나로 참조 반환 값을 처리할 수 있습니다.

- 메서드에서 값으로 반환된 일반 값. 호출자는 반환 값이 참조 반환 값임을 무시하도록 선택할 수 있습니다. 이 경우 메서드 호출에서 반환된 값을 변경해도 호출된 형식의 상태에 변경 내용이 반영되지 않습니다. 반환된 값이 값 형식인 경우 메서드 호출에서 반환된 값을 변경해도 호출된 형식의 상태에 변경 내용이 반영되지 않습니다.

- 참조 반환 값. 호출자가 참조 반환 값이 할당되는 변수를 [참조 로컬](#ref-local)로 정의해야 하며, 메서드 호출에서 반환된 값을 변경하면 호출된 형식의 상태에 변경 내용이 반영됩니다. 

## <a name="ref-locals"></a>참조 로컬

참조 반환 값을 참조로 처리하려면 호출자가 `ref` 키워드를 사용하여 값을 *참조 로컬*로 선언해야 합니다. 예를 들어 `Person.GetContactInfomation` 메서드에서 반환된 값을 값이 아니라 참조로 사용해야 하는 경우 메서드 호출이 다음과 같이 나타납니다.

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

`ref` 키워드는 지역 변수 선언 앞, *그리고* 메서드 호출 앞에 사용됩니다. 변수 선언과 할당에 `ref` 키워드를 둘 다 포함하지 않으면 컴파일러 오류 CS8172, “값을 사용하여 참조 형식 변수를 초기화할 수 없습니다.”가 생성됩니다. 
 
메서드에서 반환된 `Person` 개체에 대한 후속 변경 내용은 `contacts` 개체에 반영됩니다.

`ref` 키워드를 사용하여 `p`가 참조 로컬로 정의되지 않은 경우 `p`에 대한 호출자의 변경 내용이 `contacts` 개체에 반영되지 않습니다.
 
## <a name="ref-returns-and-ref-locals-an-example"></a>참조 반환 및 참조 로컬: 예제

다음 예제에서는 정수 값의 배열을 저장하는 `NumberStore` 클래스를 정의합니다. `FindNumber` 메서드는 인수로 전달된 숫자보다 크거나 같은 첫 번째 숫자를 참조로 반환합니다. 인수보다 크거나 같은 숫자가 없으면 메서드는 인덱스 0의 숫자를 반환합니다. 

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

다음 예제에서는 `NumberStore.FindNumber` 메서드를 호출하여 16보다 크거나 같은 첫 번째 값을 검색합니다. 그런 다음 호출자가 메서드에서 반환된 값을 두 배로 만듭니다. 예제의 출력에서 볼 수 있듯이 이 변경 내용은 `NumberStore` 인스턴스의 배열 요소 값에 반영됩니다.

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

참조 반환 값이 지원되지 않을 경우 이러한 작업은 일반적으로 해당 값과 함께 배열 요소의 인덱스를 반환하여 수행됩니다. 그런 다음 호출자는 이 인덱스를 사용하여 별도 메서드 호출에서 값을 수정할 수 있습니다. 그러나 호출자가 인덱스를 수정하여 다른 배열 값에 액세스하고 수정할 수도 있습니다.  
 
## <a name="see-also"></a>참고 항목

[ref 키워드](../../language-reference/keywords/ref.md)


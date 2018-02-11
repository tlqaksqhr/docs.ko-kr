---
title: "Visual Basic의 튜플"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a>튜플 (Visual Basic)

Visual Basic 2017 부터는 Visual Basic 언어는 기본 제공 하는 튜플 지원 튜플 만들고 튜플 쉽게 요소에 액세스 합니다. 튜플은 특정 수 및 값의 시퀀스를 포함 하는 간단한 데이터 구조입니다. 튜플의 인스턴스화할 때 수 및 각 값 (또는 요소)의 데이터 형식을 정의 합니다. 예를 들어 2-튜플 (또는 쌍)에 두 개의 요소가 있습니다. 첫 번째 수는 `Boolean` 값을 고 두 번째는는 `String`합니다. 튜플 쉽게 단일 개체에 여러 값을 저장할 수 있도록, 때문에 종종 메서드에서 여러 값을 반환 하는 간단한 방법으로 사용 됩니다.

> [!IMPORTANT]
> 튜플 지원 하려면는 <xref:System.ValueTuple> 유형입니다. NuGet 패키지를 추가 해야.NET Framework 4.7 설치 되어 있지 않으면 `System.ValueTuple`은 NuGet 갤러리에서 사용할 수 있습니다. 이 패키지 없이 오류가 발생할 수 있습니다는 컴파일, "미리 정의 된 형식과 비슷한 'ValueTuple(Of,,,)'가 정의 하지 않았거나 가져오지 하지 않습니다."

## <a name="instantiating-and-using-a-tuple"></a>인스턴스화 및 튜플을 사용

쉼표로 구분 된 값 im 괄호를 포함 하 여 튜플을 인스턴스화합니다. 각 값 튜플의 필드가 다음 됩니다. 다음 코드를 세 번 (또는 3-튜플)을 정의 예를 들어 한 `Date` 해당 첫 번째 값으로는 `String` 를 두 번째 및 `Boolean` 세 번째도 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

기본적으로 문자열의 튜플의 각 필드의 이름이 구성 `Item` 튜플의 필드의 1-시작 위치와 함께 합니다. 이 3-튜플에 대 한는 `Date` 필드는 `Item1`, `String` 필드는 `Item2`, 및 `Boolean` 필드는 `Item3`합니다. 다음 예제에서는 코드의 이전 줄에서 인스턴스화된 튜플의 필드의 값 표시

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Visual Basic 튜플의 필드는 읽기 / 쓰기; 튜플을 인스턴스화한 한 후 해당 값을 수정할 수 있습니다. 다음 예제에서는 두 개의 이전 예제에서 만든 튜플의 세 개의 필드를 수정 하 고 결과 표시 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>인스턴스화 및 명명 된 튜플을 사용

튜플의 필드에 대 한 기본 이름을 사용 하는 대신 인스턴스화할 수 있습니다는 *라는 튜플* 튜플의 요소에 고유한 이름을 지정 하 여 합니다. 튜플의 필드에 할당 된 이름으로 액세스할 수 있습니다 *또는* 기본 이름으로 합니다. 다음 예제에서는 첫 번째 필드 이름을 명시적으로 지정 한다는 점을 제외 하면 앞에서 동일한 3-튜플 인스턴스화합니다 `EventDate`, 두 번째 `Name`, 세 번째 `IsHoliday`합니다. 필드 값을 표시,를 수정 하 고 다시 필드 값이 표시 됩니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>유추 된 튜플 요소 이름

Visual Basic 15.3 부터는 Visual Basic 유추할 수; 여 튜플 요소 이름 명시적으로 할당 필요가 없습니다. 유추 된 튜플 이름은 변수 집합에서 튜플을 초기화 하 고 변수 이름으로 동일 하 게 튜플 요소 이름을 사용 하려는 경우에 유용 합니다. 

다음 예제에서는 한 `stateInfo` 명명 된 요소를 명시적으로 3 개 포함 된 튜플을 `state`, `stateName`, 및 `capital`합니다. 유의 요소 이름 지정 시에, 튜플 초기화 문 지정 명명 된 요소는 동일 하 게 명명 된 변수의 값입니다.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
요소 및 변수의 이름이 동일 하기 때문에 Visual Basic 컴파일러는 다음 예제와 같이 필드의 이름이 추론할 수 있습니다.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Visual Basic 프로젝트에서 사용 하는 Visual Basic 컴파일러의 버전을 정의 해야 수감 되어 튜플 요소 이름을 사용 하려면 (\*.vbproj) 파일: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>메서드 반환 값으로의 튜플

메서드는 단일 값만 반환할 수 있습니다. 대부분의 경우 하지만 원하는 여러 값을 반환 하는 메서드 호출 합니다. 여러 가지 방법을 사용 하 여이 제한을 해결할 수 있습니다.

- 사용자 지정 클래스 또는 구조체 속성을 가진 만들거나 필드 메서드에 의해 반환 되는 값을 나타냅니다. 따라서는 중량 솔루션입니다. 유일한 목적인 메서드 호출에서 값을 검색 하는 사용자 지정 형식을 정의 하는 필요 합니다.

- 단일 값은 메서드에서 돌아오기 있고 메서드에 대 한 참조를 전달 하 여 나머지 값을 반환 합니다. 변수 및 참조로 전달 하는 변수의 값을 덮어쓰는 위험을 인스턴스화하는 오버 헤드 포함 됩니다.

- 여러 개의 반환 값을 검색 하는 간단한 솔루션을 제공 하는 튜플을 사용할 수 있습니다.

예를 들어는 **TryParse** .NET 리턴으로 메서드는 `Boolean` 구문 분석 작업이 성공 했는지 여부를 나타내는 값입니다. 구문 분석 작업의 결과 메서드에 참조로 전달 되는 변수에 반환 됩니다. 에 대 한 호출 일반적으로와 같은 구문 분석 방법을 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 은 다음과 같습니다.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

문자열을 반환할 수 튜플을 구문 분석 작업에서 호출을 래핑할 하는 경우는 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 고유한 메서드에서 메서드. 다음 예에서 `NumericLibrary.ParseInteger` 호출은 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드 및 두 개의 요소가 있는 명명 된 튜플을 반환 합니다. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

다음과 같은 코드를 사용 하 여 메서드를 호출할 수 있습니다.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic 튜플 및.NET Framework의 튜플

Visual Basic 튜플은 중 하나의 인스턴스는 **System.ValueTuple** 제네릭 형식.NET Framework 4.7에 도입 되었습니다. .NET Framework 제네릭 집합이 포함 되어 **System.Tuple** 클래스입니다. 그러나 Visual Basic 튜플에서와 다 이러한 클래스와 **System.ValueTuple** 다양 한 방법으로의 제네릭 형식:

- 요소는 **튜플** 클래스는 명명 된 속성 `Item1`, `Item2`등입니다. Visual Basic 튜플에 및 **ValueTuple** 형식, 튜플 요소는 필드입니다.

- 요소에 의미 있는 이름을 할당할 수 없습니다는 **튜플** 인스턴스 또는 **ValueTuple** 인스턴스. Visual Basic을 사용 하는 필드의 의미를 전달 하는 이름을 지정할 수 있습니다.

- 속성은 **튜플** 인스턴스는 읽기 전용; 튜플을 변경할 수 없습니다. Visual Basic 튜플에 및 **ValueTuple** 형식, 튜플 필드는 읽기 / 쓰기; 튜플에 변경할 수 있습니다.

- 제네릭 **튜플** 형식은 참조 형식입니다. 이 사용 하 여 **튜플** 개체 할당 의미를 입력 합니다. 실행 부하 과다 경로에서는 이로 인해 응용 프로그램 성능이 크게 영향을 받을 수 있습니다. Visual Basic 튜플 및 **ValueTuple** 유형은 값 형식입니다.

확장 메서드는 <xref:System.TupleExtensions> 클래스 쉽게 튜플 Visual Basic 및.NET 사이 변환할 **튜플** 개체입니다. **ToTuple** 메서드는.NET Visual Basic 튜플 변환 **튜플** 개체 및 **ToValueTuple** 메서드 변환.NET **튜플** Visual Basic 튜플 개체입니다.

다음 예제는 튜플을 만듭니다을 하는.NET 변환 **튜플** 개체 및 Visual Basic 튜플에 다시 변환 합니다. 그런 다음 원래 같은지 확인에 있는이 튜플을 비교 합니다.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>참고 항목

[Visual Basic 언어 참조](index.md)  

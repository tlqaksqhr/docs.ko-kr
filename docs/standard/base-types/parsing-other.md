---
title: ".NET에서 기타 문자열 구문 분석"
description: ".NET에서 기타 문자열 구문 분석"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: db80cc5f37e814f224ff76b14a906bb4d41064fb
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="6d1bf-104">.NET에서 기타 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="6d1bf-104">Parsing other strings in .NET</span></span>

<span data-ttu-id="6d1bf-105">숫자 및 [DateTime](xref:System.DateTime) 문자열 외에도 [Char](xref:System.Char), [부울](xref:System.Boolean), 및 [Enum](xref:System.Enum) 형식을 나타내는 문자열을 데이터 형식으로 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-105">In addition to numeric and [DateTime](xref:System.DateTime) strings, you can also parse strings that represent the types [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) into data types.</span></span>

## <a name="char"></a><span data-ttu-id="6d1bf-106">Char</span><span class="sxs-lookup"><span data-stu-id="6d1bf-106">Char</span></span>

<span data-ttu-id="6d1bf-107">[Char](xref:System.Char) 데이터 형식과 연결된 고정 구문 분석 메서드는 단일 문자를 포함하는 문자열을 해당 유니코드 값으로 변환하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-107">The static parse method associated with the [Char](xref:System.Char) data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="6d1bf-108">다음 코드 예제에서는 문자열을 유니코드 문자로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-108">The following code example parses a string into a Unicode character.</span></span>

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a><span data-ttu-id="6d1bf-109">부울</span><span class="sxs-lookup"><span data-stu-id="6d1bf-109">Boolean</span></span>

<span data-ttu-id="6d1bf-110">[부울](xref:System.Boolean) 데이터 형식은 `Boolean` 값을 나타내는 문자열을 실제 `Boolean` 유형으로 변환하는 데 사용할 수 있는 [Parse](xref:System.Boolean.Parse(System.String)) 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-110">The [Boolean](xref:System.Boolean) data type contains a [Parse](xref:System.Boolean.Parse(System.String)) method that you can use to convert a string that represents a `Boolean` value into an actual `Boolean` type.</span></span> <span data-ttu-id="6d1bf-111">이 메서드는 대/소문자를 구분하지 않으며 "True" 또는 "False"를 포함하는 문자열을 성공적으로 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-111">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="6d1bf-112">`Boolean` 형식과 연결된 `Parse` 메서드는 공백으로 둘러싸인 문자열을 구문 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-112">The `Parse` method associated with the `Boolean` type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="6d1bf-113">다른 문자열을 전달하면 [FormatException](xref:System.FormatException)이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-113">If any other string is passed, a [FormatException](xref:System.FormatException) is thrown.</span></span>

<span data-ttu-id="6d1bf-114">다음 코드 예제에서는 문자열을 `Boolean` 값으로 변환하는 `Parse` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-114">The following code example uses the `Parse` method to convert a string into a `Boolean` value.</span></span>

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a><span data-ttu-id="6d1bf-115">열거형</span><span class="sxs-lookup"><span data-stu-id="6d1bf-115">Enumeration</span></span>

<span data-ttu-id="6d1bf-116">고정 [Parse](xref:System.Enum.Parse(System.Type,System.String)) 메서드를 사용하여 문자열 값에 대한 열거형 형식을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-116">You can use the static [Parse](xref:System.Enum.Parse(System.Type,System.String)) method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="6d1bf-117">이 메서드는 구문 분석하는 열거형 형식, 구문 분석할 문자열 및 구문 분석이 대/소문자를 구분하는지를 나타내는 선택적 `Boolean` 플래그를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-117">This method accepts the enumeration type you are parsing, the string to parse, and an optional `Boolean` flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="6d1bf-118">구문 분석하는 문자열은 쉼표로 구분된 여러 값을 포함할 수 있으며 앞이나 뒤에는 하나 이상의 빈 공간(공백이라고도 함)이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-118">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="6d1bf-119">문자열에 여러 값이 포함된 경우 반환된 개체의 값은 비트 OR 연산과 함께 결합된 모든 지정된 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-119">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>

<span data-ttu-id="6d1bf-120">다음 예제에서는 문자열 표현을 열거형 값으로 변환하는 `Parse` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-120">The following example uses the `Parse` method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="6d1bf-121">[DayOfWeek](xref:System.DayOfWeek) 열거형은 문자열에서 목요일로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d1bf-121">The [DayOfWeek](xref:System.DayOfWeek) enumeration is initialized to Thursday from a string.</span></span>

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a><span data-ttu-id="6d1bf-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d1bf-122">See Also</span></span>

[<span data-ttu-id="6d1bf-123">.NET에서 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="6d1bf-123">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="6d1bf-124">.NET의 서식 지정 형식</span><span class="sxs-lookup"><span data-stu-id="6d1bf-124">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="6d1bf-125">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="6d1bf-125">Type conversion in .NET</span></span>](type-conversion.md)



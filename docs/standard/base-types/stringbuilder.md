---
title: "StringBuilder 클래스 사용"
description: "StringBuilder 클래스 사용"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a><span data-ttu-id="a5da1-104">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="a5da1-104">Using the StringBuilder class</span></span>

<span data-ttu-id="a5da1-105">[String](xref:System.String) 개체는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-105">The [String](xref:System.String) object is immutable.</span></span> <span data-ttu-id="a5da1-106">[System.String](xref:System.String) 클래스에서 메서드 중 하나를 사용할 때마다 메모리에서 새 문자열 개체가 만들어지므로, 해당 새 개체에 대한 공간이 새로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-106">Every time you use one of the methods in the [System.String](xref:System.String) class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="a5da1-107">문자열을 반복적으로 수정해야 하는 경우 새 [String](xref:System.String) 개체 만들기와 연결된 오버헤드로 인해 비용이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new [String](xref:System.String) object can be costly.</span></span> <span data-ttu-id="a5da1-108">새 개체를 만들지 않고 문자열을 수정하려는 경우 [System.Text.StringBuilder](xref:System.Text.StringBuilder) 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-108">The [System.Text.StringBuilder](xref:System.Text.StringBuilder) class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="a5da1-109">예를 들어 [StringBuilder](xref:System.Text.StringBuilder) 클래스를 사용하면 루프에서 많은 문자열을 연결할 때 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-109">For example, using the [StringBuilder](xref:System.Text.StringBuilder) class can boost performance when concatenating many strings together in a loop.</span></span>

## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="a5da1-110">System.Text 네임스페이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="a5da1-110">Importing the System.Text Namespace</span></span>

<span data-ttu-id="a5da1-111">[StringBuilder](xref:System.Text.StringBuilder) 클래스는 [System.Text](xref:System.Text) 네임스페이스에서 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-111">The [StringBuilder](xref:System.Text.StringBuilder) class is found in the [System.Text](xref:System.Text) namespace.</span></span> <span data-ttu-id="a5da1-112">코드에서 정규화된 형식 이름을 제공할 필요가 없도록 하려면 [System.Text](xref:System.Text) 네임스페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-112">To avoid having to provide a fully qualified type name in your code, you can import the [System.Text](xref:System.Text) namespace:</span></span> 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="a5da1-113">StringBuilder 개체 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="a5da1-113">Instantiating a StringBuilder Object</span></span>

<span data-ttu-id="a5da1-114">다음 예제와 같이 오버로드된 생성자 메서드 중 하나로 변수를 초기화하여 [StringBuilder](xref:System.Text.StringBuilder) 클래스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-114">You can create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="a5da1-115">용량 및 길이 설정</span><span class="sxs-lookup"><span data-stu-id="a5da1-115">Setting the Capacity and Length</span></span>

<span data-ttu-id="a5da1-116">[StringBuilder](xref:System.Text.StringBuilder)는 캡슐화되는 문자열에서 문자 수를 확장할 수 있는 동적 개체이지만, 보관할 수 있는 최대 문자 수 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-116">Although the [StringBuilder](xref:System.Text.StringBuilder) is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="a5da1-117">이 값을 개체의 용량이라고 하며, 현재 [StringBuilder](xref:System.Text.StringBuilder)에 보관된 문자열의 길이와 혼동하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a5da1-117">This value is called the capacity of the object and should not be confused with the length of the string that the current [StringBuilder](xref:System.Text.StringBuilder) holds.</span></span> <span data-ttu-id="a5da1-118">예를 들어 길이가 5인 "Hello" 문자열을 사용하여 [StringBuilder](xref:System.Text.StringBuilder) 클래스의 새 인스턴스를 만들고 개체의 최대 용량을 25로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-118">For example, you might create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="a5da1-119">[StringBuilder](xref:System.Text.StringBuilder)를 수정할 경우 용량에 도달할 때까지 자체 크기를 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-119">When you modify the [StringBuilder](xref:System.Text.StringBuilder), it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="a5da1-120">이 경우 새 공간이 자동으로 할당되고 용량이 두 배로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="a5da1-121">오버로드된 생성자 중 하나를 사용하여 [StringBuilder](xref:System.Text.StringBuilder) 클래스의 용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-121">You can specify the capacity of the [StringBuilder](xref:System.Text.StringBuilder) class using one of the overloaded constructors.</span></span> <span data-ttu-id="a5da1-122">다음 예에서는 `MyStringBuilder` 개체를 최대 25개 공간으로 확장할 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-122">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

<span data-ttu-id="a5da1-123">또한 읽기/쓰기 [Capacity](xref:System.Text.StringBuilder.Capacity) 속성을 사용하여 개체의 최대 길이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-123">Additionally, you can use the read/write [Capacity](xref:System.Text.StringBuilder.Capacity) property to set the maximum length of your object.</span></span> <span data-ttu-id="a5da1-124">다음 예에서는 [Capacity](xref:System.Text.StringBuilder.Capacity) 속성을 사용하여 최대 개체 길이를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-124">The following example uses the [Capacity](xref:System.Text.StringBuilder.Capacity) property to define the maximum object length.</span></span>

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

<span data-ttu-id="a5da1-125">[EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) 메서드를 사용하여 현재 [StringBuilder](xref:System.Text.StringBuilder)의 용량을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-125">The [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) method can be used to check the capacity of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="a5da1-126">용량이 전달된 값보다 크면 변경되지 않고, 용량이 전달된 값보다 작으면 현재 용량이 전달된 값과 일치하도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>

<span data-ttu-id="a5da1-127">[Length](xref:System.Text.StringBuilder.Length) 속성을 보거나 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-127">The [Length](xref:System.Text.StringBuilder.Length) property can also be viewed or set.</span></span> <span data-ttu-id="a5da1-128">[Length](xref:System.Text.StringBuilder.Length) 속성을 [Capacity](xref:System.Text.StringBuilder.Capacity) 속성보다 큰 값으로 설정하면 [Capacity](xref:System.Text.StringBuilder.Capacity) 속성이 [Length](xref:System.Text.StringBuilder.Length) 속성과 동일한 값으로 자동으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-128">If you set the [Length](xref:System.Text.StringBuilder.Length) property to a value that is greater than the [Capacity](xref:System.Text.StringBuilder.Capacity) property, the [Capacity](xref:System.Text.StringBuilder.Capacity) property is automatically changed to the same value as the [Length](xref:System.Text.StringBuilder.Length) property.</span></span> <span data-ttu-id="a5da1-129">[Length](xref:System.Text.StringBuilder.Length) 속성을 현재 [StringBuilder](xref:System.Text.StringBuilder) 내의 문자열 길이보다 작은 값으로 설정하면 문자열이 단축됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-129">Setting the [Length](xref:System.Text.StringBuilder.Length) property to a value that is less than the length of the string within the current [StringBuilder](xref:System.Text.StringBuilder) shortens the string.</span></span>

## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="a5da1-130">StringBuilder 문자열 수정</span><span class="sxs-lookup"><span data-stu-id="a5da1-130">Modifying the StringBuilder String</span></span>

<span data-ttu-id="a5da1-131">다음 표에서는 [StringBuilder](xref:System.Text.StringBuilder)의 내용을 수정하는 데 사용할 수 있는 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-131">The following table lists the methods you can use to modify the contents of a [StringBuilder](xref:System.Text.StringBuilder).</span></span>

<span data-ttu-id="a5da1-132">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="a5da1-132">Method name</span></span> | <span data-ttu-id="a5da1-133">기능</span><span class="sxs-lookup"><span data-stu-id="a5da1-133">Use</span></span>
----------- | ---
<span data-ttu-id="a5da1-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span><span class="sxs-lookup"><span data-stu-id="a5da1-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span></span> | <span data-ttu-id="a5da1-135">현재 [StringBuilder](xref:System.Text.StringBuilder)의 끝에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-135">Appends information to the end of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="a5da1-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="a5da1-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | <span data-ttu-id="a5da1-137">문자열에 전달된 서식 지정자를 서식 있는 텍스트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-137">Replaces a format specifier passed in a string with formatted text.</span></span>
<span data-ttu-id="a5da1-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span><span class="sxs-lookup"><span data-stu-id="a5da1-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span></span> | <span data-ttu-id="a5da1-139">현재 [StringBuilder](xref:System.Text.StringBuilder)의 지정된 인덱스에 문자열 또는 개체를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-139">Inserts a string or object into the specified index of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="a5da1-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="a5da1-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span></span> | <span data-ttu-id="a5da1-141">현재 [StringBuilder](xref:System.Text.StringBuilder)에서 지정된 수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-141">Removes a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="a5da1-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span><span class="sxs-lookup"><span data-stu-id="a5da1-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span></span> | <span data-ttu-id="a5da1-143">지정된 인덱스에서 지정된 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-143">Replaces a specified character at a specified index.</span></span>

### <a name="append"></a><span data-ttu-id="a5da1-144">추가</span><span class="sxs-lookup"><span data-stu-id="a5da1-144">Append</span></span>

<span data-ttu-id="a5da1-145">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) 메서드를 사용하여 현재 [StringBuilder](xref:System.Text.StringBuilder)에 표시되는 문자열의 끝에 개체의 문자열 표현이나 텍스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-145">The [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) method can be used to add text or a string representation of an object to the end of a string represented by the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="a5da1-146">다음 예에서는 [StringBuilder](xref:System.Text.StringBuilder)를 "Hello World"로 초기화한 다음 개체의 끝에 일부 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-146">The following example initializes a [StringBuilder](xref:System.Text.StringBuilder) to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="a5da1-147">필요한 경우 공간이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-147">Space is allocated automatically as needed.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a><span data-ttu-id="a5da1-148">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="a5da1-148">AppendFormat</span></span>

<span data-ttu-id="a5da1-149">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) 메서드는 [StringBuilder](xref:System.Text.StringBuilder) 개체의 끝에 텍스트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-149">The [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) method adds text to the end of the [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="a5da1-150">서식 지정할 개체의 [IFormattable](xref:System.IFormattable) 구현을 호출하여 복합 서식 지정 기능을 지원합니다. 자세한 내용은 [복합 서식 지정](composite-format.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5da1-150">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-format.md)) by calling the [IFormattable](xref:System.IFormattable) implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="a5da1-151">따라서 숫자, 날짜 및 시간, 열거형 값에 대한 표준 서식 문자열, 숫자, 날짜 및 시간 값에 대한 사용자 지정 서식 문자열, 사용자 지정 형식에 대해 정의된 서식 문자열을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-151">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="a5da1-152">서식 지정에 대한 자세한 내용은 [서식 지정 형식](formatting-types.md)을 참조하세요. 이 메서드를 사용하여 변수의 서식을 사용자 지정하고 해당 값을 [StringBuilder](xref:System.Text.StringBuilder)에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-152">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="a5da1-153">다음 예에서는 [AppendFormat] 메서드를 사용하여 통화 값으로 서식 지정된 정수 값을 [StringBuilder](xref:System.Text.StringBuilder) 개체의 끝에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-153">The following example uses the AppendFormat method to place an integer value formatted as a currency value at the end of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a><span data-ttu-id="a5da1-154">Insert</span><span class="sxs-lookup"><span data-stu-id="a5da1-154">Insert</span></span>

<span data-ttu-id="a5da1-155">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) 메서드는 현재 [StringBuilder](xref:System.Text.StringBuilder) 개체의 지정된 위치에 문자열 또는 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-155">The [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) method adds a string or object to a specified position in the current [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="a5da1-156">다음 예에서는 이 메서드를 사용하여 [StringBuilder](xref:System.Text.StringBuilder) 개체의 여섯 번째 위치에 단어를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-156">The following example uses this method to insert a word into the sixth position of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a><span data-ttu-id="a5da1-157">제거</span><span class="sxs-lookup"><span data-stu-id="a5da1-157">Remove</span></span>

<span data-ttu-id="a5da1-158">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) 메서드를 사용하여 지정된&0;부터 시작하는 인덱스를 기준으로 현재 [StringBuilder](xref:System.Text.StringBuilder) 개체에서 지정된 수의 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-158">You can use the [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to remove a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder) object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="a5da1-159">다음 예에서는 [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) 메서드를 사용하여 [StringBuilder](xref:System.Text.StringBuilder) 개체를 단축합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-159">The following example uses the [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to shorten a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a><span data-ttu-id="a5da1-160">바꾸기</span><span class="sxs-lookup"><span data-stu-id="a5da1-160">Replace</span></span>

<span data-ttu-id="a5da1-161">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | 지정된 인덱스에서 지정된 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-161">The [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="a5da1-162">메서드는 [StringBuilder](xref:System.Text.StringBuilder) 개체 내의 문자를 다른 지정된 문자로 바꾸는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-162">method can be used to replace characters within the [StringBuilder](xref:System.Text.StringBuilder) object with another specified character.</span></span> <span data-ttu-id="a5da1-163">다음 예제에서는 [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))를 사용합니다. | 지정된 인덱스에서 지정된 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-163">The following example uses the [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="a5da1-164">메서드는 [StringBuilder](xref:System.Text.StringBuilder) 개체에서 느낌표 문자(!)의 모든 인스턴스를 검색한 다음 물음표 문자(?)로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-164">method to search a [StringBuilder](xref:System.Text.StringBuilder) object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="a5da1-165">StringBuilder 개체를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="a5da1-165">Converting a StringBuilder Object to a String</span></span>

<span data-ttu-id="a5da1-166">[StringBuilder](xref:System.Text.StringBuilder) 개체에서 표시하는 문자열을 [String](xref:System.String) 매개 변수를 가진 메서드에 전달하거나 사용자 인터페이스에 표시하려면 [StringBuilder](xref:System.Text.StringBuilder) 개체를 [String](xref:System.String) 개체로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-166">You must convert the [StringBuilder](xref:System.Text.StringBuilder) object to a [String](xref:System.String) object before you can pass the string represented by the [StringBuilder](xref:System.Text.StringBuilder) object to a method that has a [String](xref:System.String) parameter or display it in the user interface.</span></span> <span data-ttu-id="a5da1-167">[StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) 메서드를 호출하여 이 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-167">You do this conversion by calling the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method.</span></span> <span data-ttu-id="a5da1-168">다음 예에서는 다양한 [StringBuilder](xref:System.Text.StringBuilder) 메서드를 호출한 다음 [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) 메서드를 호출하여 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5da1-168">The following example calls a number of [StringBuilder](xref:System.Text.StringBuilder) methods and then calls the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method to display the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a><span data-ttu-id="a5da1-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5da1-169">See Also</span></span>

[<span data-ttu-id="a5da1-170">System.Text.StringBuilder</span><span class="sxs-lookup"><span data-stu-id="a5da1-170">System.Text.StringBuilder</span></span>](xref:System.Text.StringBuilder)

[<span data-ttu-id="a5da1-171">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="a5da1-171">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="a5da1-172">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="a5da1-172">Formatting types</span></span>](formatting-types.md)


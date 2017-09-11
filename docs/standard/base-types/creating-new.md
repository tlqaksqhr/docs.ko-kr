---
title: "새 문자열 만들기"
description: "새 문자열 만들기"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a><span data-ttu-id="c4ecd-104">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="c4ecd-104">Creating new strings</span></span>

<span data-ttu-id="c4ecd-105">.NET에서는 단순한 할당을 사용하여 문자열을 만들 수 있으며 다양한 매개 변수를 사용한 문자열 생성을 지원하기 위해 클래스 생성자도 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-105">.NET  allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="c4ecd-106">또한 .NET은 여러 문자열, 문자열 배열 또는 개체를 결합하여 새 문자열 개체를 만드는 여러 메서드를 [System.String](xref:System.String) 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-106">.NET also provides several methods in the [System.String](xref:System.String) class that create new string objects by combining several strings, arrays of strings, or objects.</span></span> 

## <a name="creating-strings-using-assignment"></a><span data-ttu-id="c4ecd-107">할당을 사용하여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="c4ecd-107">Creating Strings Using Assignment</span></span>

<span data-ttu-id="c4ecd-108">새 [String](xref:System.String) 개체를 만드는 가장 쉬운 방법은 [String](xref:System.String) 개체에 문자열 리터럴을 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-108">The easiest way to create a new [String](xref:System.String) object is simply to assign a string literal to a [String](xref:System.String) object.</span></span> 

## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="c4ecd-109">클래스 생성자를 사용하여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="c4ecd-109">Creating Strings Using a Class Constructor</span></span>

<span data-ttu-id="c4ecd-110">[String](xref:System.String) 클래스 생성자의 오버로드를 사용하여 문자 배열에서 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-110">You can use overloads of the [String](xref:System.String) class constructor to create strings from character arrays.</span></span> <span data-ttu-id="c4ecd-111">특정 문자를 지정된 횟수만큼 복제하여 새 문자열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-111">You can also create a new string by duplicating a particular character a specified number of times.</span></span> 

## <a name="methods-that-return-strings"></a><span data-ttu-id="c4ecd-112">문자열을 반환하는 메서드</span><span class="sxs-lookup"><span data-stu-id="c4ecd-112">Methods that Return Strings</span></span>

<span data-ttu-id="c4ecd-113">다음 표에서는 새 문자열 개체를 반환하는 여러 유용한 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-113">The following table lists several useful methods that return new string objects.</span></span>

<span data-ttu-id="c4ecd-114">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="c4ecd-114">Method name</span></span> | <span data-ttu-id="c4ecd-115">기능</span><span class="sxs-lookup"><span data-stu-id="c4ecd-115">Use</span></span>
----------- | ---
<span data-ttu-id="c4ecd-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="c4ecd-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span></span> | <span data-ttu-id="c4ecd-117">입력 개체 집합에서 형식이 지정된 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-117">Builds a formatted string from a set of input objects.</span></span>
<span data-ttu-id="c4ecd-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span><span class="sxs-lookup"><span data-stu-id="c4ecd-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span></span> | <span data-ttu-id="c4ecd-119">둘 이상의 문자열에서 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-119">Builds strings from two or more strings.</span></span>
<span data-ttu-id="c4ecd-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span><span class="sxs-lookup"><span data-stu-id="c4ecd-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span></span> |<span data-ttu-id="c4ecd-121">문자열 배열을 결합하여 새 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-121">Builds a new string by combining an array of strings.</span></span>
<span data-ttu-id="c4ecd-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span><span class="sxs-lookup"><span data-stu-id="c4ecd-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span></span> | <span data-ttu-id="c4ecd-123">기존 문자열의 지정된 인덱스에 문자열을 삽입하여 새 문자열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-123">Builds a new string by inserting a string into the specified index of an existing string.</span></span>
<span data-ttu-id="c4ecd-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="c4ecd-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span></span> | <span data-ttu-id="c4ecd-125">문자열의 지정된 문자를 문자 배열의 지정된 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-125">Copies specified characters in a string into a specified position in an array of characters.</span></span>

### <a name="format"></a><span data-ttu-id="c4ecd-126">서식</span><span class="sxs-lookup"><span data-stu-id="c4ecd-126">Format</span></span>

<span data-ttu-id="c4ecd-127">`String.Format` 메서드를 사용하여 형식이 지정된 문자열을 만들고 여러 개체를 나타내는 문자열을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-127">You can use the `String.Format` method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="c4ecd-128">이 메서드는 전달된 모든 개체를 문자열로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-128">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="c4ecd-129">예를 들어 응용 프로그램이 [Int32](xref:System.Int32) 값과 [DateTime](xref:System.DateTime) 값을 사용자에게 표시해야 하는 경우 `Format` 메서드를 사용하여 이러한 값을 나타내는 문자열을 쉽게 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-129">For example, if your application must display an [Int32](xref:System.Int32) value and a [DateTime](xref:System.DateTime) value to the user, you can easily construct a string to represent these values using the `Format` method.</span></span> <span data-ttu-id="c4ecd-130">이 메서드에서 사용되는 형식 지정 규칙에 대한 자세한 내용은 [복합 형식 지정](composite-format.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-130">For information about formatting conventions used with this method, see the section on [composite formatting](composite-format.md).</span></span>

<span data-ttu-id="c4ecd-131">다음 예제에서는 `Format` 메서드를 통해 정수 변수를 사용하는 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-131">The following example uses the `Format` method to create a string that uses an integer variable.</span></span>

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

<span data-ttu-id="c4ecd-132">이 예제에서 [DateTime.Now](xref:System.DateTime.Now)는 현재 스레드와 연결된 문화권에서 지정된 방식으로 현재 날짜와 시간을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-132">In this example, [DateTime.Now](xref:System.DateTime.Now) displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>

### <a name="concat"></a><span data-ttu-id="c4ecd-133">Concat</span><span class="sxs-lookup"><span data-stu-id="c4ecd-133">Concat</span></span>

<span data-ttu-id="c4ecd-134">`String.Concat` 메서드를 사용하여 둘 이상의 기존 개체에서 새 문자열 개체를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-134">The `String.Concat` method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="c4ecd-135">문자열을 연결하는 언어 독립적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-135">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="c4ecd-136">이 메서드는 `System.Object`에서 파생된 모든 클래스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-136">This method accepts any class that derives from `System.Object`.</span></span> <span data-ttu-id="c4ecd-137">다음 예제에서는 두 개의 기존 문자열 개체와 구분 문자에서 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-137">The following example creates a string from two existing string objects and a separating character.</span></span>

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a><span data-ttu-id="c4ecd-138">Join</span><span class="sxs-lookup"><span data-stu-id="c4ecd-138">Join</span></span>

<span data-ttu-id="c4ecd-139">`String.Join` 메서드는 문자열 배열과 구분 기호 문자열에서 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-139">The `String.Join` method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="c4ecd-140">이 메서드는 여러 문자열을 함께 연결하여 쉼표 등으로 구분된 목록을 만들려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-140">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>

<span data-ttu-id="c4ecd-141">다음 예제에서는 공백을 사용하여 문자열 배열을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-141">The following example uses a space to bind a string array.</span></span>

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a><span data-ttu-id="c4ecd-142">Insert</span><span class="sxs-lookup"><span data-stu-id="c4ecd-142">Insert</span></span>

<span data-ttu-id="c4ecd-143">`String.Insert` 메서드는 다른 문자열의 지정된 위치에 문자열을 삽입하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-143">The `String.Insert` method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="c4ecd-144">이 메서드는&0;부터 시작하는 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-144">This method uses a zero-based index.</span></span> <span data-ttu-id="c4ecd-145">다음 예제에서는 `MyString`의 다섯 번째 인덱스 위치에 문자열을 삽입하고 이 값으로 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-145">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a><span data-ttu-id="c4ecd-146">CopyTo</span><span class="sxs-lookup"><span data-stu-id="c4ecd-146">CopyTo</span></span>

<span data-ttu-id="c4ecd-147">`String.CopyTo` 메서드는 문자열의 일부를 문자 배열에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-147">The `String.CopyTo` method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="c4ecd-148">기존 문자열의 시작 인덱스와 복사할 문자 수를 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-148">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="c4ecd-149">이 메서드는 소스 인덱스, 문자 배열, 대상 인덱스 및 복사할 문자 수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-149">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="c4ecd-150">모든 인덱스는&0;부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-150">All indexes are zero-based.</span></span>

<span data-ttu-id="c4ecd-151">다음 예제에서는 `CopyTo` 메서드를 사용하여 문자열 개체에서 "Hello" 단어의 문자를 문자 배열의 첫 번째 인덱스 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ecd-151">The following example uses the `CopyTo` method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a><span data-ttu-id="c4ecd-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4ecd-152">See Also</span></span>

[<span data-ttu-id="c4ecd-153">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="c4ecd-153">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="c4ecd-154">복합 서식 지정</span><span class="sxs-lookup"><span data-stu-id="c4ecd-154">Composite formatting</span></span>](composite-format.md)



---
title: "문자열에서 문자 트리밍 및 제거"
description: "문자열에서 문자 트리밍 및 제거"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
ms.translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 6105861882c3bfd525a2d902fd2600f5da10417d
ms.contentlocale: ko-kr
ms.lasthandoff: 11/16/2016

---

# <a name="trimming-and-removing-characters-from-strings"></a><span data-ttu-id="c4ac7-104">문자열에서 문자 트리밍 및 제거</span><span class="sxs-lookup"><span data-stu-id="c4ac7-104">Trimming and removing characters from strings</span></span>

<span data-ttu-id="c4ac7-105">문장을 개별 단어로 구문 분석할 경우 단어의 끝에 빈 공간(공백이라고도 함)이 있는 단어가 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-105">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="c4ac7-106">이 경우에 [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) 클래스에서 trim 메서드 중 하나를 사용하여 문자열에 지정된 위치에서 공백의 수나 다른 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-106">In this situation, you can use one of the trim methods in the [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="c4ac7-107">다음 테이블에서는 사용할 수 있는 trim 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-107">The following table describes the available trim methods.</span></span>

<span data-ttu-id="c4ac7-108">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="c4ac7-108">Method name</span></span> | <span data-ttu-id="c4ac7-109">기능</span><span class="sxs-lookup"><span data-stu-id="c4ac7-109">Use</span></span>
----------- | ---
[<span data-ttu-id="c4ac7-110">String.Trim</span><span class="sxs-lookup"><span data-stu-id="c4ac7-110">String.Trim</span></span>](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | <span data-ttu-id="c4ac7-111">문자열의 시작과 끝에서 문자 배열에 지정된 문자 또는 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-111">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>
<span data-ttu-id="c4ac7-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="c4ac7-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span></span> | <span data-ttu-id="c4ac7-113">문자열의 끝에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-113">Removes characters specified in an array of characters from the end of a string.</span></span>
<span data-ttu-id="c4ac7-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="c4ac7-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span></span> | <span data-ttu-id="c4ac7-115">문자열의 시작에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-115">Removes characters specified in an array of characters from the beginning of a string.</span></span>
<span data-ttu-id="c4ac7-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="c4ac7-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span></span> | <span data-ttu-id="c4ac7-117">문자열의 지정한 인덱스 위치에서 지정한 개수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-117">Removes a specified number of characters from a specified index position in a string.</span></span>


## <a name="trim"></a><span data-ttu-id="c4ac7-118">Trim</span><span class="sxs-lookup"><span data-stu-id="c4ac7-118">Trim</span></span>

<span data-ttu-id="c4ac7-119">다음 예제와 같이 [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) 메서드를 사용하여 문자열의 양쪽 끝에서 공백의 쉽게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-119">You can easily remove white spaces from both ends of a string by using the [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) method, as shown in the following example.</span></span>

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

<span data-ttu-id="c4ac7-120">문자열의 시작과 끝의 문자 배열에서 지정하는 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-120">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="c4ac7-121">다음 예제에서는 공백 문자, 마침표 또는 별표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-121">The following example removes white-space characters, periods, and asterisks.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a><span data-ttu-id="c4ac7-122">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="c4ac7-122">TrimEnd</span></span>

<span data-ttu-id="c4ac7-123">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 메서드는 새 문자열 개체를 생성하여 문자열의 끝에서 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-123">The [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="c4ac7-124">문자 배열을 이 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-124">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="c4ac7-125">문자 배열에서 요소의 순서는 trim 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-125">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="c4ac7-126">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-126">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="c4ac7-127">다음 예제에서는 TrimEnd 메서드를 사용하여 문자열의 마지막 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-127">The following example removes the last letters of a string using the TrimEnd method.</span></span> <span data-ttu-id="c4ac7-128">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'r'` 문자 및 `'W'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-128">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="c4ac7-129">이 코드는 `MyString`의 마지막 단어 및 첫 번째 단어의 일부를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-129">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="c4ac7-130">이 코드는 콘솔에 `He`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-130">This code displays `He` to the console.</span></span>

<span data-ttu-id="c4ac7-131">다음 예제에서는 [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 메서드를 사용하여 문자열의 마지막 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-131">The following example removes the last word of a string using the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method.</span></span> <span data-ttu-id="c4ac7-132">이 코드에서 쉼표는 `Hello` 단어 뒤에 오면 쉼표가 trim에 대한 문자의 배열에 지정되지 않기 때문에 해당 trim은 쉼표에서 끝나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-132">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="c4ac7-133">이 코드는 콘솔에 `Hello,`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-133">This code displays `Hello,` to the console.</span></span>

## <a name="trimstart"></a><span data-ttu-id="c4ac7-134">TrimStart</span><span class="sxs-lookup"><span data-stu-id="c4ac7-134">TrimStart</span></span>

<span data-ttu-id="c4ac7-135">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) 메서드는 기존 문자열 개체의 시작 부분에서 문자를 제거하여 새 문자열을 만든다는 점을 제외하고 [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-135">The [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method is similar to the [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="c4ac7-136">문자 배열을 [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-136">An array of characters is passed to the [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method to specify the characters to be removed.</span></span> <span data-ttu-id="c4ac7-137">[TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) 메서드와 마찬가지로 문자 배열에서 요소의 순서는 트리밍 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-137">As with the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="c4ac7-138">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-138">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="c4ac7-139">다음 예제에서는 문자열의 첫 번째 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-139">The following example removes the first word of a string.</span></span> <span data-ttu-id="c4ac7-140">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'l'` 문자 및 `'H'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-140">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="c4ac7-141">이 코드는 콘솔에 `World!`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-141">This code displays `World!` to the console.</span></span>

## <a name="remove"></a><span data-ttu-id="c4ac7-142">제거</span><span class="sxs-lookup"><span data-stu-id="c4ac7-142">Remove</span></span>

<span data-ttu-id="c4ac7-143">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) 메서드는 기존 문자열의 지정된 위치에서 시작하는 지정된 수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-143">The [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="c4ac7-144">이 메서드에서는 0 기반 인덱스를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-144">This method assumes a zero-based index.</span></span>

<span data-ttu-id="c4ac7-145">다음 예제에서는 문자열의 0 기반 인덱스 중 5번째 위치에서 시작하는 문자열에서 10개의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-145">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

<span data-ttu-id="c4ac7-146">[String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) 메서드를 호출하고 빈 문자열인 [String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)를 대체로 지정하여 문자열에서 지정된 문자나 부분 문자열을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-146">You can also remove a specified character or substring from a string by calling the [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) method and specifying an empty string ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) as the replacement.</span></span> <span data-ttu-id="c4ac7-147">다음 예제에서는 문자열에서 모든 쉼표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ac7-147">The following example removes all commas from a string.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a><span data-ttu-id="c4ac7-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4ac7-148">See Also</span></span>

[<span data-ttu-id="c4ac7-149">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="c4ac7-149">Basic string operations</span></span>](basic-string-operations.md)



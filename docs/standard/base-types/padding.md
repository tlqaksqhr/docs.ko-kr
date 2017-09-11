---
title: "문자열 채우기"
description: "문자열 채우기"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bc3cc9028b232cc2ba6ca3130c4bdb261c4a0a42
ms.contentlocale: ko-kr
ms.lasthandoff: 03/02/2017

---

# <a name="padding-strings"></a><span data-ttu-id="b52a1-104">문자열 채우기</span><span class="sxs-lookup"><span data-stu-id="b52a1-104">Padding strings</span></span>

<span data-ttu-id="b52a1-105">다음 [System.String](xref:System.String) 메서드 중 하나를 사용하여 선행 또는 후행 문자로 지정된 총 길이를 채운 원래 문자열에 구성된 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-105">Use one of the following [System.String](xref:System.String) methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="b52a1-106">채움 문자는 공백이나 지정된 문자를 사용할 수 있고 결과적으로 오른쪽에 맞춤인지 아니면 왼쪽 맞춤인지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-106">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>

<span data-ttu-id="b52a1-107">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="b52a1-107">Method name</span></span> | <span data-ttu-id="b52a1-108">기능</span><span class="sxs-lookup"><span data-stu-id="b52a1-108">Use</span></span>
----------- | ---
<span data-ttu-id="b52a1-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b52a1-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span></span> | <span data-ttu-id="b52a1-110">선행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-110">Pads a string with leading characters to a specified total length.</span></span>
<span data-ttu-id="b52a1-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b52a1-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span></span> | <span data-ttu-id="b52a1-112">후행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-112">Pads a string with trailing characters to a specified total length.</span></span>

## <a name="padleft"></a><span data-ttu-id="b52a1-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="b52a1-113">PadLeft</span></span>

<span data-ttu-id="b52a1-114">[String.PadLeft](xref:System.String.PadLeft(System.Int32)) 메서드는 지정된 총 길이에 맞도록 필요한 만큼 원래 문자열에 선행 채움 문자를 연결하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-114">The [String.PadLeft](xref:System.String.PadLeft(System.Int32)) method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b52a1-115">[String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) 메서드는 공백을 채움 문자로 사용하며 [String.PadLeft (Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) 메서드를 사용하면 고유한 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-115">The [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) method uses white space as the padding character and the [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="b52a1-116">다음 코드 예제에서는 [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) 메서드를 사용하여&20;자 길이의 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-116">The following code example uses the [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b52a1-117">이 예제에서는 콘솔에 "`--------Hello World!`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-117">The example displays "`--------Hello World!`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a><span data-ttu-id="b52a1-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="b52a1-118">PadRight</span></span>

<span data-ttu-id="b52a1-119">[String.PadRight](xref:System.String.PadRight(System.Int32)) 메서드는 지정된 총 길이에 맞도록 필요한 만큼 원래 문자열에 후행 채움 문자를 연결하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-119">The [String.PadRight](xref:System.String.PadRight(System.Int32)) method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b52a1-120">[String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) 메서드는 공백을 채움 문자로 사용하며 [String.PadRight (Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) 메서드를 사용하면 고유한 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-120">The [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) method uses white space as the padding character and the [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="b52a1-121">다음 코드 예제에서는 [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) 메서드를 사용하여&20;자 길이의 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-121">The following code example uses the [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b52a1-122">이 예제에서는 콘솔에 "`Hello World!--------`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b52a1-122">The example displays "`Hello World!--------`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a><span data-ttu-id="b52a1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b52a1-123">See Also</span></span>

[<span data-ttu-id="b52a1-124">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="b52a1-124">Basic string operations</span></span>](basic-string-operations.md)



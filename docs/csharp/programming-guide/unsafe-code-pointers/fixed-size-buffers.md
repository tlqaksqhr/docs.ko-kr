---
title: "고정 크기 버퍼(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f99c2c6d477fca988fcca77de5ca5c2f8addd4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="cd18c-102">고정 크기 버퍼(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="cd18c-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="cd18c-103">C#에서는 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문을 사용하여 데이터 구조에 고정 크기 배열이 있는 버퍼를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="cd18c-104">그러면 다른 언어로 작성된 코드 같은 기존 코드, 기존 DLL 또는 COM 프로젝트로 작업할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="cd18c-105">고정 배열은 일반 구조체 멤버에 허용되는 특성이나 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="cd18c-106">배열 형식이 `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` 또는 `double`이어야 한다는 것이 유일한 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd18c-107">주의</span><span class="sxs-lookup"><span data-stu-id="cd18c-107">Remarks</span></span>  
 <span data-ttu-id="cd18c-108">초기 C# 버전에서는 배열이 포함된 C# 구조체에 배열 요소가 포함되어 있지 않기 때문에 C++ 스타일 고정 크기 구조체를 선언하기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="cd18c-109">대신 구조체에 요소에 대한 참조가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="cd18c-110">C# 2.0에서는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 코드 블록에서 사용될 경우 [struct](../../../csharp/language-reference/keywords/struct.md)에 고정 크기 배열을 포함하는 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="cd18c-111">예를 들어 C# 2.0 이전에는 다음 `struct`의 크기가 8바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="cd18c-112">`pathName` 배열은 힙 할당 배열에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 [!code-csharp[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 <span data-ttu-id="cd18c-113">C# 2.0부터는 `struct`에 포함된 배열이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-113">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="cd18c-114">다음 예제에서 `fixedBuffer` 배열은 고정 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="cd18c-115">배열의 요소에 액세스하려면 `fixed` 문을 사용하여 첫 번째 요소에 대한 포인터를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-115">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="cd18c-116">`fixed` 문은 `fixedBuffer`의 인스턴스를 메모리의 특정 위치에 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-116">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 [!code-csharp[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 <span data-ttu-id="cd18c-117">128개 요소 `char` 배열의 크기는 256바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="cd18c-118">고정 크기 [char](../../../csharp/language-reference/keywords/char.md) 버퍼는 인코딩에 관계없이 항상 문자당 2바이트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-118">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="cd18c-119">이는 char 버퍼가 `CharSet = CharSet.Auto` 또는 `CharSet = CharSet.Ansi`를 사용하는 API 메서드 또는 구조체로 마샬링되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="cd18c-120">자세한 내용은 <xref:System.Runtime.InteropServices.CharSet>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cd18c-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="cd18c-121">또 다른 일반적인 고정 크기 배열은 [bool](../../../csharp/language-reference/keywords/bool.md) 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-121">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="cd18c-122">`bool` 배열의 요소 크기는 항상 1바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-122">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="cd18c-123">`bool` 배열은 비트 배열이나 버퍼를 만드는 데 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-123">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd18c-124">[stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)를 사용하여 만든 메모리를 제외하고 C# 컴파일러와 CLR(공용 언어 런타임)에서 보안 버퍼 오버런 검사를 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-124">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="cd18c-125">모든 안전하지 않은 코드와 마찬가지로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-125">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="cd18c-126">안전하지 않은 버퍼는 다음과 같은 측면에서 일반 배열과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-126">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="cd18c-127">안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-127">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="cd18c-128">안전하지 않은 버퍼는 항상 벡터 또는 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-128">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="cd18c-129">배열의 선언에는 `char id[8]`와 같이 개수가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-129">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="cd18c-130">`char id[]`를 대신 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-130">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="cd18c-131">안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서 구조체의 인스턴스 필드만 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd18c-131">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd18c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd18c-132">See Also</span></span>  
 [<span data-ttu-id="cd18c-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cd18c-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cd18c-134">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="cd18c-134">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="cd18c-135">fixed 문</span><span class="sxs-lookup"><span data-stu-id="cd18c-135">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="cd18c-136">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="cd18c-136">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)

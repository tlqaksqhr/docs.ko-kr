---
title: 안전하지 않은 코드 및 포인터(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: b57a6f607dbdbc84c60889a5ce2b1e3c33d7f435
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331606"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="924c7-102">안전하지 않은 코드 및 포인터(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="924c7-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="924c7-103">형식 안전성 및 보안을 유지하기 위해 C#에서는 포인터 산술 연산을 기본적으로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="924c7-104">그러나 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용하여 포인터를 사용할 수 있는 안전하지 않은 컨텍스트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="924c7-105">포인터에 대한 자세한 내용은 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="924c7-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="924c7-106">CLR(공용 언어 런타임)에서 안전하지 않은 코드를 확인할 수 없는 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="924c7-107">C#에 안전하지 않은 코드가 반드시 위험한 것은 아니며, CLR에서 안전을 확인할 수 없는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="924c7-108">그러므로 CLR은 완전히 신뢰할 수 있는 어셈블리에 있는 경우 안전하지 않은 코드만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="924c7-109">안전하지 않은 코드를 사용하는 경우 코드로 인해 보안 위험이나 포인터 오류가 발생하지 않도록 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="924c7-110">안전하지 않은 코드 개요</span><span class="sxs-lookup"><span data-stu-id="924c7-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="924c7-111">안전하지 않은 코드에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-111">Unsafe code has the following properties:</span></span>  
  
-   <span data-ttu-id="924c7-112">메서드, 형식 및 코드 블록은 안전하지 않은 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
-   <span data-ttu-id="924c7-113">경우에 따라 안전하지 않은 코드는 배열 범위 검사를 제거하여 응용 프로그램의 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
-   <span data-ttu-id="924c7-114">포인터가 필요한 네이티브 함수를 호출하는 경우 안전하지 않은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
-   <span data-ttu-id="924c7-115">안전하지 않은 코드를 사용하면 보안 및 안정성 위험이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-115">Using unsafe code introduces security and stability risks.</span></span>  
  
-   <span data-ttu-id="924c7-116">C#에서 안전하지 않은 코드를 컴파일하기 위해 응용 프로그램을 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)를 사용하여 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="924c7-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="924c7-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="924c7-117">Related Sections</span></span>  
 <span data-ttu-id="924c7-118">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="924c7-118">For more information, see:</span></span>  
  
-   [<span data-ttu-id="924c7-119">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="924c7-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
-   [<span data-ttu-id="924c7-120">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="924c7-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
-   [<span data-ttu-id="924c7-121">방법: 포인터를 사용하여 바이트 배열 복사</span><span class="sxs-lookup"><span data-stu-id="924c7-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
-   [<span data-ttu-id="924c7-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="924c7-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="924c7-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="924c7-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="924c7-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="924c7-124">See Also</span></span>  
 [<span data-ttu-id="924c7-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="924c7-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

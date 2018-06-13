---
title: unsafe(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: c476bdcea4993b27c0e8f8148a985f18a43ba09b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171956"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="5298c-102">unsafe(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5298c-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="5298c-103">`unsafe` 키워드는 포인터와 관련된 모든 작업에 필요한 안전하지 않은 컨텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="5298c-104">자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5298c-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="5298c-105">형식 또는 멤버 선언에서 `unsafe` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="5298c-106">따라서 형식 또는 멤버의 전체 텍스트 범위가 안전하지 않은 컨텍스트로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="5298c-107">예를 들어 다음은 `unsafe` 한정자를 사용하여 선언된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="5298c-108">안전하지 않은 컨텍스트의 범위는 매개 변수 목록에서 메서드의 끝까지 확장되므로 매개 변수 목록에 포인터를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="5298c-109">안전하지 않은 블록을 통해 이 블록 내에서 안전하지 않은 코드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="5298c-110">예:</span><span class="sxs-lookup"><span data-stu-id="5298c-110">For example:</span></span>  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="5298c-111">안전하지 않은 코드를 컴파일하려면 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="5298c-112">안전하지 않은 코드는 공용 언어 런타임에서 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5298c-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5298c-113">예</span><span class="sxs-lookup"><span data-stu-id="5298c-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5298c-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5298c-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5298c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5298c-115">See Also</span></span>  
 [<span data-ttu-id="5298c-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5298c-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5298c-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5298c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5298c-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="5298c-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5298c-119">fixed 문</span><span class="sxs-lookup"><span data-stu-id="5298c-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="5298c-120">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="5298c-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="5298c-121">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="5298c-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

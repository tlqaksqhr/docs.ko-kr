---
title: "sizeof(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords: sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="61808-102">sizeof(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="61808-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="61808-103">관리되지 않는 형식의 크기(바이트)를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61808-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="61808-104">관리되지 않는 형식에는 뒤에 나오는 표에 나열된 기본 제공 형식과 다음 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61808-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="61808-105">열거형</span><span class="sxs-lookup"><span data-stu-id="61808-105">Enum types</span></span>  
  
-   <span data-ttu-id="61808-106">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="61808-106">Pointer types</span></span>  
  
-   <span data-ttu-id="61808-107">참조 형식인 필드 또는 속성을 포함하지 않는 사용자 정의 구조체</span><span class="sxs-lookup"><span data-stu-id="61808-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="61808-108">다음 예제에서는 `int`의 크기를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61808-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="61808-109">주의</span><span class="sxs-lookup"><span data-stu-id="61808-109">Remarks</span></span>  
 <span data-ttu-id="61808-110">C# 버전 2.0부터 기본 제공 형식에 `sizeof`를 적용하기 위해 [비안전](../../../csharp/language-reference/keywords/unsafe.md) 모드를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61808-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="61808-111">`sizeof` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61808-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="61808-112">`sizeof` 연산자에서 반환되는 값은 `int` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="61808-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="61808-113">다음 표에서는 특정 기본 제공 형식이 피연산자로 포함된 `sizeof` 식을 대체하는 상수 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61808-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="61808-114">식</span><span class="sxs-lookup"><span data-stu-id="61808-114">Expression</span></span>|<span data-ttu-id="61808-115">상수 값</span><span class="sxs-lookup"><span data-stu-id="61808-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="61808-116">1</span><span class="sxs-lookup"><span data-stu-id="61808-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="61808-117">1</span><span class="sxs-lookup"><span data-stu-id="61808-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="61808-118">2</span><span class="sxs-lookup"><span data-stu-id="61808-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="61808-119">2</span><span class="sxs-lookup"><span data-stu-id="61808-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="61808-120">4</span><span class="sxs-lookup"><span data-stu-id="61808-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="61808-121">4</span><span class="sxs-lookup"><span data-stu-id="61808-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="61808-122">8</span><span class="sxs-lookup"><span data-stu-id="61808-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="61808-123">8</span><span class="sxs-lookup"><span data-stu-id="61808-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="61808-124">2(유니코드)</span><span class="sxs-lookup"><span data-stu-id="61808-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="61808-125">4</span><span class="sxs-lookup"><span data-stu-id="61808-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="61808-126">8</span><span class="sxs-lookup"><span data-stu-id="61808-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="61808-127">16</span><span class="sxs-lookup"><span data-stu-id="61808-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="61808-128">1</span><span class="sxs-lookup"><span data-stu-id="61808-128">1</span></span>|  
  
 <span data-ttu-id="61808-129">구조체를 비롯한 다른 모든 형식의 경우 `sizeof` 연산자는 안전하지 않은 코드 블록에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61808-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="61808-130"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 메서드를 사용할 수 있지만 이 메서드에서 반환된 값이 `sizeof`에서 반환된 값과 항상 같지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61808-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="61808-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>는 형식이 마샬링된 후의 크기를 반환하는 반면, `sizeof`는 안쪽 여백을 포함하여 공용 언어 런타임에 의해 할당된 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61808-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61808-132">예제</span><span class="sxs-lookup"><span data-stu-id="61808-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="61808-133">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="61808-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61808-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61808-134">See Also</span></span>  
 [<span data-ttu-id="61808-135">C# 참조</span><span class="sxs-lookup"><span data-stu-id="61808-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="61808-136">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="61808-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="61808-137">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="61808-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="61808-138">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="61808-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="61808-139">enum</span><span class="sxs-lookup"><span data-stu-id="61808-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="61808-140">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="61808-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="61808-141">구조체</span><span class="sxs-lookup"><span data-stu-id="61808-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="61808-142">상수</span><span class="sxs-lookup"><span data-stu-id="61808-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

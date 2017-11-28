---
title: "포인터 형식(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0699793e91199cc623c0d13e42937c8b919e992a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="da3ff-102">포인터 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="da3ff-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="da3ff-103">안전하지 않은 컨텍스트에서는 형식이 포인터 형식, 값 형식 또는 참조 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="da3ff-104">포인터 형식 선언은 다음 형식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="da3ff-105">포인터 형식은 다음과 같은 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="da3ff-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="da3ff-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="da3ff-107">모든 [enum](../../../csharp/language-reference/keywords/enum.md) 형식</span><span class="sxs-lookup"><span data-stu-id="da3ff-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="da3ff-108">임의의 포인터 형식</span><span class="sxs-lookup"><span data-stu-id="da3ff-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="da3ff-109">관리되지 않는 형식의 필드만 포함하는 임의의 사용자 정의 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="da3ff-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="da3ff-110">포인터 형식은 [개체](../../../csharp/language-reference/keywords/object.md)에서 상속되지 않으며 포인터 형식과 `object`는 서로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="da3ff-111">또한 boxing과 unboxing은 포인터를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="da3ff-112">그러나 다른 포인터 형식 간의 변환 및 포인터 형식과 정수 형식 사이의 변환은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="da3ff-113">동일한 선언에서 여러 포인터를 선언하는 경우 별표(*)는 기본 형식에만 함께 사용되고 각 포인터 이름의 접두사로는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-113">When you declare multiple pointers in the same declaration, the asterisk (*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="da3ff-114">예:</span><span class="sxs-lookup"><span data-stu-id="da3ff-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="da3ff-115">개체 참조는 포인터가 해당 개체 참조를 가리키는 경우에도 가비지 수집될 수 있으므로 포인터는 참조나 참조가 들어 있는 [구조체](../../../csharp/language-reference/keywords/struct.md)를 가리킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="da3ff-116">가비지 수집기는 포인터 형식에서 개체를 가리키는지 여부를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="da3ff-117">`myType*` 형식의 포인터 변수 값은 `myType` 형식의 변수 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="da3ff-118">다음은 포인터 형식 선언의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="da3ff-119">예제</span><span class="sxs-lookup"><span data-stu-id="da3ff-119">Example</span></span>|<span data-ttu-id="da3ff-120">설명</span><span class="sxs-lookup"><span data-stu-id="da3ff-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="da3ff-121">`p`는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="da3ff-122">`p`는 정수에 대한 포인터를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="da3ff-123">`p`는 정수에 대한 포인터의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="da3ff-124">`p`는 문자에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="da3ff-125">`p`는 알 수 없는 형식에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="da3ff-126">포인터 간접 참조 연산자 *를 사용하면 포인터 변수가 가리키는 위치의 내용에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-126">The pointer indirection operator * can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="da3ff-127">예를 들어, 다음 선언을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da3ff-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="da3ff-128">여기서 `*myVariable` 식은 `int`에 포함된 주소에 있는 `myVariable` 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="da3ff-129">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) 및 [포인터 변환](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) 항목에 포인터에 대한 몇 가지 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="da3ff-130">다음 예제는 `unsafe` 키워드 및 `fixed` 문에 대한 필요성과 정수 포인터를 증분하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="da3ff-131">이 코드를 실행하려면 콘솔 응용 프로그램의 주 함수에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="da3ff-132">**프로젝트 디자이너**에서 안전하지 않은 코드를 사용하도록 설정해야 합니다. 메뉴 모음에서 **프로젝트**, **속성**을 선택한 다음 **빌드** 탭에서 **안전하지 않은 코드 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="da3ff-133">`void*` 형식의 포인터에는 간접 참조 연산자를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="da3ff-134">그러나 캐스트를 사용하여 void 포인터를 다른 포인터 형식으로 변환하거나 반대로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="da3ff-135">포인터는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-135">A pointer can be `null`.</span></span> <span data-ttu-id="da3ff-136">null 포인터에 간접 참조 연산자를 적용할 때 발생하는 동작은 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="da3ff-137">메서드 사이에 포인터를 전달하면 정의되지 않은 동작이 발생할 수 있다는 사실에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="da3ff-138">Out 또는 Ref 매개 변수를 통해, 또는 함수 결과로 지역 변수에 포인터를 반환하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-138">Examples are returning a pointer to a local variable through an Out or Ref parameter or as the function result.</span></span> <span data-ttu-id="da3ff-139">fixed 블록에서 포인터가 설정되면 이 포인터가 가리키는 변수의 고정 상태가 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="da3ff-140">다음 표에서는 안전하지 않은 컨텍스트에서 포인터에 대해 수행할 수 있는 연산자와 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="da3ff-141">연산자/문</span><span class="sxs-lookup"><span data-stu-id="da3ff-141">Operator/Statement</span></span>|<span data-ttu-id="da3ff-142">기능</span><span class="sxs-lookup"><span data-stu-id="da3ff-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="da3ff-143">포인터 간접 참조를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="da3ff-144">포인터를 통해 구조체 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="da3ff-145">[]</span><span class="sxs-lookup"><span data-stu-id="da3ff-145">[]</span></span>|<span data-ttu-id="da3ff-146">포인터를 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="da3ff-147">변수 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="da3ff-148">++ 및 --</span><span class="sxs-lookup"><span data-stu-id="da3ff-148">++ and --</span></span>|<span data-ttu-id="da3ff-149">포인터를 증가 및 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="da3ff-150">+ 및 -</span><span class="sxs-lookup"><span data-stu-id="da3ff-150">+ and -</span></span>|<span data-ttu-id="da3ff-151">포인터 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="da3ff-152">==, !=, \<, >, \<= 및 >=</span><span class="sxs-lookup"><span data-stu-id="da3ff-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="da3ff-153">포인터를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="da3ff-154">스택에 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="da3ff-155">`fixed` 문</span><span class="sxs-lookup"><span data-stu-id="da3ff-155">`fixed` statement</span></span>|<span data-ttu-id="da3ff-156">해당 주소를 찾을 수 있도록 임시로 변수를 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="da3ff-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="da3ff-157">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="da3ff-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da3ff-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da3ff-158">See Also</span></span>  
 [<span data-ttu-id="da3ff-159">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="da3ff-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="da3ff-160">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="da3ff-160">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="da3ff-161">포인터 변환</span><span class="sxs-lookup"><span data-stu-id="da3ff-161">Pointer Conversions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [<span data-ttu-id="da3ff-162">포인터 식</span><span class="sxs-lookup"><span data-stu-id="da3ff-162">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="da3ff-163">유형</span><span class="sxs-lookup"><span data-stu-id="da3ff-163">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="da3ff-164">unsafe</span><span class="sxs-lookup"><span data-stu-id="da3ff-164">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="da3ff-165">fixed 문</span><span class="sxs-lookup"><span data-stu-id="da3ff-165">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="da3ff-166">stackalloc</span><span class="sxs-lookup"><span data-stu-id="da3ff-166">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="da3ff-167">boxing 및 unboxing</span><span class="sxs-lookup"><span data-stu-id="da3ff-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

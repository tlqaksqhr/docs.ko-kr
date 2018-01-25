---
title: "캐스팅 및 형식 변환(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: "52"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1361a7f115e2bae4b2d1f6271fa9020706581691
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="1733c-102">캐스팅 및 형식 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1733c-102">Casting and Type Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="1733c-103">C#은 컴파일 시간에 정적으로 형식화되므로 변수가 선언된 후에는 다시 선언되거나 다른 형식의 값을 저장하는 데 사용될 수 없습니다. 단, 형식이 변수의 형식으로 변환될 수 있는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or used to store values of another type unless that type is convertible to the variable's type.</span></span> <span data-ttu-id="1733c-104">예를 들어 정수에서 임의 문자열로의 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-104">For example, there is no conversion from an integer to any arbitrary string.</span></span> <span data-ttu-id="1733c-105">따라서 `i`를 정수로 선언한 후에는 다음 코드와 같이 문자열 "Hello"를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-105">Therefore, after you declare `i` as an integer, you cannot assign the string "Hello" to it, as is shown in the following code.</span></span>  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 <span data-ttu-id="1733c-106">그러나 다른 형식의 변수 또는 메서드 매개 변수에 값을 복사해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="1733c-107">예를 들어 매개 변수가 `double`로 형식화된 메서드에 전달해야 하는 정수 변수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="1733c-108">또는 인터페이스 형식의 변수에 클래스 변수를 할당해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="1733c-109">이러한 작업을 *형식 변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="1733c-110">C#에서는 다음과 같은 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
-   <span data-ttu-id="1733c-111">**암시적 변환**: 변환은 형식이 안전하고 데이터가 손실되지 않으므로 특수 구문이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="1733c-112">예제에는 작은 정수 형식에서 큰 정수 형식으로의 변환 및 파생 클래스에서 기본 클래스로의 변환이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
-   <span data-ttu-id="1733c-113">**명시적 변환(캐스트)**: 명시적 변환에는 캐스트 연산자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="1733c-114">변환 시 정보가 손실되거나 다른 이유로 변환에 실패할 경우 캐스팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="1733c-115">일반적인 예제에는 숫자를 정밀도가 낮거나 범위가 더 작은 형식으로 변환하는 작업과 기본 클래스 인스턴스를 파생 클래스로 변환하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
-   <span data-ttu-id="1733c-116">**사용자 정의 변환**: 사용자 정의 변환은 기본 클래스-파생 클래스 관계가 없는 사용자 지정 형식 간의 명시적 및 암시적 변환을 사용하도록 정의할 수 있는 특수 메서드를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="1733c-117">자세한 내용은 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-117">For more information, see [Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>  
  
-   <span data-ttu-id="1733c-118">**도우미 클래스를 사용한 변환**: 정수와 <xref:System.DateTime?displayProperty=nameWithType> 개체, 16진수 문자열과 바이트 배열 등 호환되지 않는 형식 간에 변환하려면 <xref:System.BitConverter?displayProperty=nameWithType> 클래스, <xref:System.Convert?displayProperty=nameWithType> 클래스, 기본 제공 숫자 형식(예: <xref:System.Int32.Parse%2A?displayProperty=nameWithType>)의 `Parse` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=nameWithType> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=nameWithType> class, the <xref:System.Convert?displayProperty=nameWithType> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1733c-119">자세한 내용은 [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) 및 [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-119">For more information, see [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="1733c-120">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="1733c-120">Implicit Conversions</span></span>  
 <span data-ttu-id="1733c-121">기본 제공 숫자 형식의 경우 저장되는 값이 잘리거나 반올림되지 않고 변수에 맞출 수 있을 때 암시적 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="1733c-122">예를 들어 [long](../../../csharp/language-reference/keywords/long.md) 형식의 변수(8바이트 정수)는 [int](../../../csharp/language-reference/keywords/int.md)(32비트 컴퓨터의 4바이트)가 저장할 수 있는 모든 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-122">For example, a variable of type [long](../../../csharp/language-reference/keywords/long.md) (8 byte integer) can store any value that an [int](../../../csharp/language-reference/keywords/int.md) (4 bytes on a 32-bit computer) can store.</span></span> <span data-ttu-id="1733c-123">다음 예제에서 컴파일러는 오른쪽의 값을 `long` 형식으로 암시적으로 변환한 후 `bigNum`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-123">In the following example, the compiler implicitly converts the value on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 <span data-ttu-id="1733c-124">모든 암시적 숫자 변환 규칙의 전체 목록은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-124">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="1733c-125">참조 형식의 경우 클래스에서 직접 또는 간접 기본 클래스나 인터페이스로의 암시적 변환이 항상 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-125">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="1733c-126">파생 클래스에 항상 기본 클래스의 모든 멤버가 포함되므로 특수 구문이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-126">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="1733c-127">명시적 변환</span><span class="sxs-lookup"><span data-stu-id="1733c-127">Explicit Conversions</span></span>  
 <span data-ttu-id="1733c-128">그러나 변환을 수행할 때 정보 손실의 위험이 있는 경우에는 컴파일러에서 *캐스트*라는 명시적 변환을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-128">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="1733c-129">캐스트는 변환을 수행하고자 하고 데이터 손실이 발생할 가능성을 알고 있음을 컴파일러에 명시적으로 알리는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-129">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="1733c-130">캐스트를 수행하려면 변환할 값 또는 변수 앞에 캐스트할 형식을 괄호 안에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-130">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="1733c-131">다음 프로그램은 [double](../../../csharp/language-reference/keywords/double.md)을 [int](../../../csharp/language-reference/keywords/int.md)로 캐스트합니다. 캐스트가 없으면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-131">The following program casts a [double](../../../csharp/language-reference/keywords/double.md) to an [int](../../../csharp/language-reference/keywords/int.md). The program will not compile without the cast.</span></span>  
  
 [!code-csharp[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 <span data-ttu-id="1733c-132">허용되는 명시적 숫자 변환 목록은 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-132">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="1733c-133">참조 형식의 경우 기본 형식에서 파생 형식으로 변환해야 할 경우에는 명시적 캐스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-133">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 <span data-ttu-id="1733c-134">참조 형식 간 캐스트 작업은 기본 개체의 런타임 형식을 변경하지 않습니다. 참조로 사용되는 값의 형식을 해당 개체로만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-134">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="1733c-135">자세한 내용은 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-135">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="1733c-136">런타임의 형식 변환 예외</span><span class="sxs-lookup"><span data-stu-id="1733c-136">Type Conversion Exceptions at Run Time</span></span>  
 <span data-ttu-id="1733c-137">일부 참조 형식 변환 시에는 컴파일러에서 캐스트가 유효한지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-137">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="1733c-138">제대로 컴파일되는 캐스트 작업이 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-138">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="1733c-139">다음 예제와 같이 런타임에 형식 캐스트가 실패하면 <xref:System.InvalidCastException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-139">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 [!code-csharp[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 <span data-ttu-id="1733c-140">C#에서는 실제로 캐스트를 수행하기 전에 호환성을 테스트할 수 있는 [is](../../../csharp/language-reference/keywords/is.md) 및 [as](../../../csharp/language-reference/keywords/as.md) 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1733c-140">C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="1733c-141">자세한 내용은 [방법: AS 및 IS 연산자를 사용한 안전한 캐스트](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1733c-141">For more information, see [How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1733c-142">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1733c-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="1733c-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1733c-143">See Also</span></span>  
 [<span data-ttu-id="1733c-144">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1733c-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1733c-145">유형</span><span class="sxs-lookup"><span data-stu-id="1733c-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="1733c-146">() 연산자</span><span class="sxs-lookup"><span data-stu-id="1733c-146">() Operator</span></span>](../../../csharp/language-reference/operators/invocation-operator.md)  
 [<span data-ttu-id="1733c-147">explicit</span><span class="sxs-lookup"><span data-stu-id="1733c-147">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="1733c-148">implicit</span><span class="sxs-lookup"><span data-stu-id="1733c-148">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="1733c-149">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="1733c-149">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [<span data-ttu-id="1733c-150">일반화된 형식 변환</span><span class="sxs-lookup"><span data-stu-id="1733c-150">Generalized Type Conversion</span></span>](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)  
 [<span data-ttu-id="1733c-151">내보낸 형식 변환</span><span class="sxs-lookup"><span data-stu-id="1733c-151">Exported Type Conversion</span></span>](http://msdn.microsoft.com/library/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)  
 [<span data-ttu-id="1733c-152">방법: 문자열을 숫자로 변환</span><span class="sxs-lookup"><span data-stu-id="1733c-152">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)

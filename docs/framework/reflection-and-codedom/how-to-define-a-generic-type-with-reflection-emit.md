---
title: "방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- generics [.NET Framework], dynamic types
- reflection emit, generic types
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6096a54c6a530035bd32c24d427ba047f905476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-define-a-generic-type-with-reflection-emit"></a><span data-ttu-id="b1f74-102">방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의</span><span class="sxs-lookup"><span data-stu-id="b1f74-102">How to: Define a Generic Type with Reflection Emit</span></span>
<span data-ttu-id="b1f74-103">이 항목에서는 두 개의 형식 매개 변수가 있는 간단한 제네릭 형식을 만드는 방법, 형식 매개 변수에 클래스 제약 조건, 인터페이스 제약 조건, 특수 제약 조건을 적용하는 방법, 클래스의 형식 매개 변수를 매개 변수 형식 및 반환 형식으로 사용하는 멤버를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-103">This topic shows how to create a simple generic type with two type parameters, how to apply class constraints, interface constraints, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1f74-104">제네릭 형식에 속하고 해당 형식의 형식 매개 변수를 사용한다고 해서 제네릭 메서드가 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-104">A method is not generic just because it belongs to a generic type and uses the type parameters of that type.</span></span> <span data-ttu-id="b1f74-105">고유한 형식 매개 변수 목록을 포함하는 경우에만 제네릭 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-105">A method is generic only if it has its own type parameter list.</span></span> <span data-ttu-id="b1f74-106">제네릭 형식의 메서드는 대부분 이 예제와 같이 제네릭 메서드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-106">Most methods on generic types are not generic, as in this example.</span></span> <span data-ttu-id="b1f74-107">제네릭 메서드를 내보내는 방법에 대한 예제는 [방법: 리플렉션 내보내기를 사용하여 제네릭 메서드 정의](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-method-with-reflection-emit.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1f74-107">For an example of emitting a generic method, see [How to: Define a Generic Method with Reflection Emit](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-method-with-reflection-emit.md).</span></span>  
  
### <a name="to-define-a-generic-type"></a><span data-ttu-id="b1f74-108">제네릭 형식을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="b1f74-108">To define a generic type</span></span>  
  
1.  <span data-ttu-id="b1f74-109">`GenericEmitExample1`이라는 동적 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-109">Define a dynamic assembly named `GenericEmitExample1`.</span></span> <span data-ttu-id="b1f74-110">이 예제에서는 어셈블리가 실행되고 디스크에 저장되므로 <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-110">In this example, the assembly is executed and saved to disk, so <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType> is specified.</span></span>  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2.  <span data-ttu-id="b1f74-111">동적 모듈을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-111">Define a dynamic module.</span></span> <span data-ttu-id="b1f74-112">어셈블리는 실행 모듈로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-112">An assembly is made up of executable modules.</span></span> <span data-ttu-id="b1f74-113">단일 모듈 어셈블리의 경우 모듈 이름은 어셈블리 이름과 같고, 파일 이름은 모듈 이름에 확장명을 추가한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-113">For a single-module assembly, the module name is the same as the assembly name, and the file name is the module name plus an extension.</span></span>  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3.  <span data-ttu-id="b1f74-114">클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-114">Define a class.</span></span> <span data-ttu-id="b1f74-115">이 예제에서 클래스 이름은 `Sample`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-115">In this example, the class is named `Sample`.</span></span>  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4.  <span data-ttu-id="b1f74-116">매개 변수 이름이 포함된 문자열 배열을 <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType> 메서드에 전달하여 `Sample`의 제네릭 형식 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-116">Define the generic type parameters of `Sample` by passing an array of strings containing the names of the parameters to the <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b1f74-117">이렇게 하면 클래스가 제네릭 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-117">This makes the class a generic type.</span></span> <span data-ttu-id="b1f74-118">반환 값은 내보낸 코드에서 사용할 수 있는 형식 매개 변수를 나타내는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 개체 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-118">The return value is an array of <xref:System.Reflection.Emit.GenericTypeParameterBuilder> objects representing the type parameters, which can be used in your emitted code.</span></span>  
  
     <span data-ttu-id="b1f74-119">다음 코드에서 `Sample`은 형식 매개 변수 `TFirst` 및 `TSecond`가 있는 제네릭 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-119">In the following code, `Sample` becomes a generic type with type parameters `TFirst` and `TSecond`.</span></span> <span data-ttu-id="b1f74-120">코드를 읽기 쉽도록 각 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>는 형식 매개 변수와 동일한 이름을 가진 변수에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-120">To make the code easier to read, each <xref:System.Reflection.Emit.GenericTypeParameterBuilder> is placed in a variable with the same name as the type parameter.</span></span>  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5.  <span data-ttu-id="b1f74-121">형식 매개 변수에 특수 제약 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-121">Add special constraints to the type parameters.</span></span> <span data-ttu-id="b1f74-122">이 예제에서 형식 매개 변수 `TFirst`는 매개 변수가 없는 생성자를 가진 형식과 참조 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-122">In this example, type parameter `TFirst` is constrained to types that have parameterless constructors, and to reference types.</span></span>  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6.  <span data-ttu-id="b1f74-123">필요에 따라 형식 매개 변수에 클래스 및 인터페이스 제약 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-123">Optionally add class and interface constraints to the type parameters.</span></span> <span data-ttu-id="b1f74-124">이 예제에서 형식 매개 변수 `TFirst`는 `baseType` 변수에 포함된 <xref:System.Type> 개체가 나타내는 기본 클래스에서 파생되고 `interfaceA` 및 `interfaceB` 변수에 포함된 형식의 인터페이스를 구현하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-124">In this example, type parameter `TFirst` is constrained to types that derive from the base class represented by the <xref:System.Type> object contained in the variable `baseType`, and that implement the interfaces whose types are contained in the variables `interfaceA` and `interfaceB`.</span></span> <span data-ttu-id="b1f74-125">이러한 변수의 선언 및 할당은 코드 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1f74-125">See the code example for the declaration and assignment of these variables.</span></span>  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7.  <span data-ttu-id="b1f74-126">필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-126">Define a field.</span></span> <span data-ttu-id="b1f74-127">이 예제에서 필드 형식은 형식 매개 변수 `TFirst`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-127">In this example, the type of the field is specified by type parameter `TFirst`.</span></span> <span data-ttu-id="b1f74-128"><xref:System.Reflection.Emit.GenericTypeParameterBuilder>는 <xref:System.Type>에서 파생되므로 형식을 사용할 수 있는 어디에서든 제네릭 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-128"><xref:System.Reflection.Emit.GenericTypeParameterBuilder> derives from <xref:System.Type>, so you can use generic type parameters anywhere a type can be used.</span></span>  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8.  <span data-ttu-id="b1f74-129">제네릭 형식의 형식 매개 변수를 사용하는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-129">Define a method that uses the type parameters of the generic type.</span></span> <span data-ttu-id="b1f74-130">이러한 메서드는 고유한 형식 매개 변수 목록이 없을 경우 제네릭 메서드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-130">Note that such methods are not generic unless they have their own type parameter lists.</span></span> <span data-ttu-id="b1f74-131">다음 코드는 `TFirst` 배열을 사용하고배열의 모든 요소가 포함된 `List<TFirst>`(Visual Basic에서는 `List(Of TFirst)`)를 반환하는 `static` 메서드(Visual Basic에서는 `Shared`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-131">The following code defines a `static` method (`Shared` in Visual Basic) that takes an array of `TFirst` and returns a `List<TFirst>` (`List(Of TFirst)` in Visual Basic) containing all the elements of the array.</span></span> <span data-ttu-id="b1f74-132">이 메서드를 정의하려면 제네릭 형식 정의 `List<T>`에 대해 <xref:System.Type.MakeGenericType%2A>을 호출하여 `List<TFirst>` 형식을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-132">To define this method, it is necessary to create the type `List<TFirst>` by calling <xref:System.Type.MakeGenericType%2A> on the generic type definition, `List<T>`.</span></span> <span data-ttu-id="b1f74-133">`typeof` 연산자(Visual Basic에서는 `GetType`)를 사용하여 제네릭 형식 정의를 가져오는 경우 `T`가 생략됩니다. 매개 변수 형식은 <xref:System.Type.MakeArrayType%2A> 메서드를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-133">(The `T` is omitted when you use the `typeof` operator (`GetType` in Visual Basic) to get the generic type definition.) The parameter type is created by using the <xref:System.Type.MakeArrayType%2A> method.</span></span>  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. <span data-ttu-id="b1f74-134">메서드 본문을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-134">Emit the method body.</span></span> <span data-ttu-id="b1f74-135">메서드 본문은 입력 배열을 스택에 로드하고 `IEnumerable<TFirst>`(입력 요소를 목록에 넣는 모든 작업 수행)를 사용하는 `List<TFirst>` 생성자를 호출하고 반환하는 세 개의 opcode로 구성됩니다(스택에 새 <xref:System.Collections.Generic.List%601> 개체를 남김).</span><span class="sxs-lookup"><span data-stu-id="b1f74-135">The method body consists of three opcodes that load the input array onto the stack, call the `List<TFirst>` constructor that takes `IEnumerable<TFirst>` (which does all the work of putting the input elements into the list), and return (leaving the new <xref:System.Collections.Generic.List%601> object on the stack).</span></span> <span data-ttu-id="b1f74-136">이 코드를 내보내는 작업의 어려운 부분은 생성자를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-136">The difficult part of emitting this code is getting the constructor.</span></span>  
  
     <span data-ttu-id="b1f74-137"><xref:System.Type.GetConstructor%2A> 메서드는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>에서 지원되지 않으므로 `List<TFirst>`의 생성자를 직접 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-137">The <xref:System.Type.GetConstructor%2A> method is not supported on a <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, so it is not possible to get the constructor of `List<TFirst>` directly.</span></span> <span data-ttu-id="b1f74-138">먼저 제네릭 형식 정의 `List<T>`의 생성자를 가져온 다음 해당하는 `List<TFirst>`의 생성자로 변환하는 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-138">First, it is necessary to get the constructor of the generic type definition `List<T>` and then to call a method that converts it to the corresponding constructor of `List<TFirst>`.</span></span>  
  
     <span data-ttu-id="b1f74-139">이 코드 예제에 사용되는 생성자는 `IEnumerable<T>`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-139">The constructor used for this code example takes an `IEnumerable<T>`.</span></span> <span data-ttu-id="b1f74-140">그러나 <xref:System.Collections.Generic.IEnumerable%601> 제네릭 인터페이스의 제네릭 형식 정의는 아니며, `List<T>`의 형식 매개 변수 `T`를 `IEnumerable<T>`의 형식 매개 변수 `T` 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-140">Note, however, that this is not the generic type definition of the <xref:System.Collections.Generic.IEnumerable%601> generic interface; instead, the type parameter `T` from `List<T>` must be substituted for the type parameter `T` of `IEnumerable<T>`.</span></span> <span data-ttu-id="b1f74-141">이는 두 형식에 모두 `T`라는 형식 매개 변수가 있기 때문에 혼동을 주는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-141">(This seems confusing only because both types have type parameters named `T`.</span></span> <span data-ttu-id="b1f74-142">이 때문에 이 코드 예제에서는 `TFirst` 및 `TSecond`라는 이름을 사용합니다. 생성자 인수의 형식의 가져오려면 제네릭 형식 정의 `IEnumerable<T>`로 시작하고 `List<T>`의 첫 번째 제네릭 형식 매개 변수를 사용하여 <xref:System.Type.MakeGenericType%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-142">That is why this code example uses the names `TFirst` and `TSecond`.) To get the type of the constructor argument, start with the generic type definition `IEnumerable<T>` and call <xref:System.Type.MakeGenericType%2A> with the first generic type parameter of `List<T>`.</span></span> <span data-ttu-id="b1f74-143">생성자 인수 목록은 배열로 전달되어야 합니다. 여기서는 하나의 인수만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-143">The constructor argument list must be passed as an array, with just one argument in this case.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1f74-144">제네릭 형식 정의는 C#에서 `typeof` 연산자를 사용하는 경우 `IEnumerable<>`로 표현되고, Visual Basic에서 `IEnumerable(Of )` 연산자를 사용하는 경우 `GetType`로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-144">The generic type definition is expressed as `IEnumerable<>` when you use the `typeof` operator in C#, or `IEnumerable(Of )` when you use the `GetType` operator in Visual Basic.</span></span>  
  
     <span data-ttu-id="b1f74-145">이제 제네릭 형식 정의에서 <xref:System.Type.GetConstructor%2A>를 호출하여 `List<T>`의 생성자를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-145">Now it is possible to get the constructor of `List<T>` by calling <xref:System.Type.GetConstructor%2A> on the generic type definition.</span></span> <span data-ttu-id="b1f74-146">이 생성자를 해당하는 `List<TFirst>`의 생성자로 변환하려면 `List<TFirst>` 및 `List<T>`의 생성자를 static <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-146">To convert this constructor to the corresponding constructor of `List<TFirst>`, pass `List<TFirst>` and the constructor from `List<T>` to the static <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType> method.</span></span>  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. <span data-ttu-id="b1f74-147">형식을 만들고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-147">Create the type and save the file.</span></span>  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. <span data-ttu-id="b1f74-148">메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-148">Invoke the method.</span></span> <span data-ttu-id="b1f74-149">`ExampleMethod`는 제네릭이 아니지만 이 메서드가 속하는 형식이 제네릭이므로 호출할 수 있는 <xref:System.Reflection.MethodInfo>를 가져오려면 `Sample`에 대한 형식 정의에서 생성된 형식을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-149">`ExampleMethod` is not generic, but the type it belongs to is generic, so in order to get a <xref:System.Reflection.MethodInfo> that can be invoked it is necessary to create a constructed type from the type definition for `Sample`.</span></span> <span data-ttu-id="b1f74-150">생성된 형식은 매개 변수가 없는 기본 생성자를 가진 참조 형식이므로 `Example`의 제약 조건을 충족하는 `TFirst` 클래스 및 `TSecond`의 제약 조건을 충족하는 `ExampleDerived` 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-150">The constructed type uses the `Example` class, which satisfies the constraints on `TFirst` because it is a reference type and has a default parameterless constructor, and the `ExampleDerived` class which satisfies the constraints on `TSecond`.</span></span> <span data-ttu-id="b1f74-151">`ExampleDerived`에 대한 코드는 예제 코드 섹션에서 확인할 수 있습니다. 이러한 두 형식이 <xref:System.Type.MakeGenericType%2A>에 전달되어 생성된 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-151">(The code for `ExampleDerived` can be found in the example code section.) These two types are passed to <xref:System.Type.MakeGenericType%2A> to create the constructed type.</span></span> <span data-ttu-id="b1f74-152">그런 다음 <xref:System.Type.GetMethod%2A> 메서드를 사용하여 <xref:System.Reflection.MethodInfo>를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-152">The <xref:System.Reflection.MethodInfo> is then obtained using the <xref:System.Type.GetMethod%2A> method.</span></span>  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. <span data-ttu-id="b1f74-153">다음 코드는 `Example` 개체 배열을 만들고 호출할 메서드의 인수를 나타내는 <xref:System.Object> 형식의 배열에 해당 배열을 배치한 다음 <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-153">The following code creates an array of `Example` objects, places that array in an array of type <xref:System.Object> representing the arguments of the method to be invoked, and passes them to the <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29> method.</span></span> <span data-ttu-id="b1f74-154"><xref:System.Reflection.MethodBase.Invoke%2A> 메서드가 `static`이기 때문에 해당 메서드의 첫 번째 인수는 null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-154">The first argument of the <xref:System.Reflection.MethodBase.Invoke%2A> method is a null reference because the method is `static`.</span></span>  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="b1f74-155">예</span><span class="sxs-lookup"><span data-stu-id="b1f74-155">Example</span></span>  
 <span data-ttu-id="b1f74-156">다음 코드 예제에서는 기본 클래스 및 두 개의 인터페이스와 함께 `Sample`이라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-156">The following code example defines a class named `Sample`, along with a base class and two interfaces.</span></span> <span data-ttu-id="b1f74-157">프로그램은 `Sample`에 대한 두 개의 제네릭 형식 매개 변수를 정의하고 제네릭 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-157">The program defines two generic type parameters for `Sample`, turning it into a generic type.</span></span> <span data-ttu-id="b1f74-158">형식 매개 변수를 통해서만 제네릭 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-158">Type parameters are the only thing that makes a type generic.</span></span> <span data-ttu-id="b1f74-159">프로그램은 형식 매개 변수 정의 앞과 뒤에 테스트 메시지를 표시하여 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-159">The program shows this by displaying a test message before and after the definition of the type parameters.</span></span>  
  
 <span data-ttu-id="b1f74-160">형식 매개 변수 `TSecond`는 기본 클래스 및 인터페이스를 통해 클래스 및 인터페이스 제약 조건을 보여 주는 데 사용되고, 형식 매개 변수 `TFirst`는 특수 제약 조건을 보여 주는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-160">The type parameter `TSecond` is used to demonstrate class and interface constraints, using the base class and interfaces, and the type parameter `TFirst` is used to demonstrate special constraints.</span></span>  
  
 <span data-ttu-id="b1f74-161">코드 예제에서는 필드 형식과 메서드의 매개 변수 및 반환 형식에 대해 클래스의 형식 매개 변수를 사용하여 필드와 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-161">The code example defines a field and a method using the class's type parameters for the field type and for the parameter and return type of the method.</span></span>  
  
 <span data-ttu-id="b1f74-162">`Sample` 클래스를 만든 후 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-162">After the `Sample` class has been created, the method is invoked.</span></span>  
  
 <span data-ttu-id="b1f74-163">프로그램에는 제네릭 형식에 대한 정보를 나열하는 메서드 및 형식 매개 변수에 대한 특수 제약 조건을 나열하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-163">The program includes a method that lists information about a generic type, and a method that lists the special constraints on a type parameter.</span></span> <span data-ttu-id="b1f74-164">이러한 메서드는 완성된 `Sample` 클래스에 대한 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-164">These methods are used to display information about the finished `Sample` class.</span></span>  
  
 <span data-ttu-id="b1f74-165">프로그램은 완성된 모듈을 디스크에 `GenericEmitExample1.dll`로 저장하므로 [Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 열고 `Sample` 클래스에 대한 MSIL을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-165">The program saves the finished module to disk as `GenericEmitExample1.dll`, so you can open it with the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) and examine the MSIL for the `Sample` class.</span></span>  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1f74-166">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b1f74-166">Compiling the Code</span></span>  
  
-   <span data-ttu-id="b1f74-167">코드에는 컴파일하는 데 필요한 C# `using` 문(Visual Basic에서는 `Imports`)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-167">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="b1f74-168">추가 어셈블리 참조는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-168">No additional assembly references are required.</span></span>  
  
-   <span data-ttu-id="b1f74-169">csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-169">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="b1f74-170">Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로그램 프로젝트 템플릿에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f74-170">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f74-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1f74-171">See Also</span></span>  
 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>  
 [<span data-ttu-id="b1f74-172">리플렉션 내보내기 사용</span><span class="sxs-lookup"><span data-stu-id="b1f74-172">Using Reflection Emit</span></span>](http://msdn.microsoft.com/library/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)  
 [<span data-ttu-id="b1f74-173">리플렉션 내보내기 동적 어셈블리 시나리오</span><span class="sxs-lookup"><span data-stu-id="b1f74-173">Reflection Emit Dynamic Assembly Scenarios</span></span>](http://msdn.microsoft.com/library/e1cc6750-e20f-473b-bb4e-f43bc66aecce)

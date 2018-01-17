---
title: "방법: 동적 메서드 정의 및 실행"
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
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7384f625a6d1609294297645bebc335e72d1e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-execute-dynamic-methods"></a><span data-ttu-id="448cc-102">방법: 동적 메서드 정의 및 실행</span><span class="sxs-lookup"><span data-stu-id="448cc-102">How to: Define and Execute Dynamic Methods</span></span>
<span data-ttu-id="448cc-103">다음 절차에서는 간단한 동적 메서드 및 클래스 인스턴스에 바인딩된 동적 메서드를 정의하고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-103">The following procedures show how to define and execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span> <span data-ttu-id="448cc-104">동적 메서드에 대한 자세한 내용은 <xref:System.Reflection.Emit.DynamicMethod> 클래스 및 [리플렉션 내보내기 동적 메서드 시나리오](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="448cc-104">For more information on dynamic methods, see the <xref:System.Reflection.Emit.DynamicMethod> class and [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e).</span></span>  
  
### <a name="to-define-and-execute-a-dynamic-method"></a><span data-ttu-id="448cc-105">동적 메서드를 정의하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="448cc-105">To define and execute a dynamic method</span></span>  
  
1.  <span data-ttu-id="448cc-106">메서드를 실행할 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-106">Declare a delegate type to execute the method.</span></span> <span data-ttu-id="448cc-107">제네릭 대리자를 사용하여 선언해야 하는 대리자 형식 수를 최소화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-107">Consider using a generic delegate to minimize the number of delegate types you need to declare.</span></span> <span data-ttu-id="448cc-108">다음 코드는 `SquareIt` 메서드에 사용할 수 있는 두 개의 대리자 형식을 선언하며, 둘 중 하나는 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-108">The following code declares two delegate types that could be used for the `SquareIt` method, and one of them is generic.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  <span data-ttu-id="448cc-109">동적 메서드에 대한 매개 변수 형식을 지정하는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-109">Create an array that specifies the parameter types for the dynamic method.</span></span> <span data-ttu-id="448cc-110">이 예제에서 유일한 매개 변수는 `int`(Visual Basic에서는 `Integer`)이므로 배열에 요소가 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-110">In this example, the only parameter is an `int` (`Integer` in Visual Basic), so the array has only one element.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  <span data-ttu-id="448cc-111"><xref:System.Reflection.Emit.DynamicMethod>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-111">Create a <xref:System.Reflection.Emit.DynamicMethod>.</span></span> <span data-ttu-id="448cc-112">이 예제에서 메서드 이름은 `SquareIt`입니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-112">In this example the method is named `SquareIt`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="448cc-113">동적 메서드에는 이름을 지정할 필요가 없으며, 이름으로 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-113">It is not necessary to give dynamic methods names, and they cannot be invoked by name.</span></span> <span data-ttu-id="448cc-114">여러 동적 메서드가 동일한 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-114">Multiple dynamic methods can have the same name.</span></span> <span data-ttu-id="448cc-115">그러나 이름은 호출 스택에 표시되며 디버그하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-115">However, the name appears in call stacks and can be useful for debugging.</span></span>  
  
     <span data-ttu-id="448cc-116">반환 값의 형식은 `long`으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-116">The type of the return value is specified as `long`.</span></span> <span data-ttu-id="448cc-117">메서드는 예제 코드가 들어 있는 `Example` 클래스를 포함하는 모듈에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-117">The method is associated with the module that contains the `Example` class, which contains the example code.</span></span> <span data-ttu-id="448cc-118">로드된 모든 모듈을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-118">Any loaded module could be specified.</span></span> <span data-ttu-id="448cc-119">동적 메서드는 모듈 수준 `static` 메서드(Visual Basic에서는 `Shared`)처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-119">The dynamic method acts like a module-level `static` method (`Shared` in Visual Basic).</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  <span data-ttu-id="448cc-120">메서드 본문을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-120">Emit the method body.</span></span> <span data-ttu-id="448cc-121">이 예제에서 <xref:System.Reflection.Emit.ILGenerator> 개체는 MSIL(Microsoft Intermediate Language)을 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-121">In this example, an <xref:System.Reflection.Emit.ILGenerator> object is used to emit the Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="448cc-122">또는 <xref:System.Reflection.Emit.DynamicILInfo> 개체를 비관리 코드 생성기와 함께 사용하여 <xref:System.Reflection.Emit.DynamicMethod>에 대한 메서드 본문을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-122">Alternatively, a <xref:System.Reflection.Emit.DynamicILInfo> object can be used in conjunction with unmanaged code generators to emit the method body for a <xref:System.Reflection.Emit.DynamicMethod>.</span></span>  
  
     <span data-ttu-id="448cc-123">이 예제의 MSIL은 `int`인 인수를 스택에 로드하고, `long`으로 변환한 다음 `long`을 복제하고 두 개의 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-123">The MSIL in this example loads the argument, which is an `int`, onto the stack, converts it to a `long`, duplicates the `long`, and multiplies the two numbers.</span></span> <span data-ttu-id="448cc-124">이렇게 하면 스택의 거듭제곱 결과가 구해지며, 메서드가 반환하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-124">This leaves the squared result on the stack, and all the method has to do is return.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  <span data-ttu-id="448cc-125"><xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 호출하여 동적 메서드를 나타내는 대리자 인스턴스(1단계에서 선언됨)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-125">Create an instance of the delegate (declared in step 1) that represents the dynamic method by calling the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="448cc-126">대리자를 만들면 메서드가 완성되고, MSIL 추가 등 메서드를 변경하려는 이후의 모든 시도는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-126">Creating the delegate completes the method, and any further attempts to change the method — for example, adding more MSIL — are ignored.</span></span> <span data-ttu-id="448cc-127">다음 코드는 대리자를 만들고 제네릭 대리자를 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-127">The following code creates the delegate and invokes it, using a generic delegate.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### <a name="to-define-and-execute-a-dynamic-method-that-is-bound-to-an-object"></a><span data-ttu-id="448cc-128">개체에 바인딩된 동적 메서드를 정의하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="448cc-128">To define and execute a dynamic method that is bound to an object</span></span>  
  
1.  <span data-ttu-id="448cc-129">메서드를 실행할 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-129">Declare a delegate type to execute the method.</span></span> <span data-ttu-id="448cc-130">제네릭 대리자를 사용하여 선언해야 하는 대리자 형식 수를 최소화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-130">Consider using a generic delegate to minimize the number of delegate types you need to declare.</span></span> <span data-ttu-id="448cc-131">다음 코드는 매개 변수 하나가 있는 메서드 및 대리자가 개체에 바인딩된 경우 매개 변수 두 개와 반환 값이 있는 메서드를 실행하는 데 사용할 수 있는 제네릭 대리자 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-131">The following code declares a generic delegate type that can be used to execute any method with one parameter and a return value, or a method with two parameters and a return value if the delegate is bound to an object.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  <span data-ttu-id="448cc-132">동적 메서드에 대한 매개 변수 형식을 지정하는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-132">Create an array that specifies the parameter types for the dynamic method.</span></span> <span data-ttu-id="448cc-133">메서드를 나타내는 대리자가 개체에 바인딩된 경우 첫 번째 매개 변수는 대리자가 바인딩된 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-133">If the delegate representing the method is to be bound to an object, the first parameter must match the type the delegate is bound to.</span></span> <span data-ttu-id="448cc-134">이 예제에는 `Example` 형식과 `int`(Visual Basic에서는 `Integer`) 형식의 두 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-134">In this example, there are two parameters, of type `Example` and type `int` (`Integer` in Visual Basic).</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  <span data-ttu-id="448cc-135"><xref:System.Reflection.Emit.DynamicMethod>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-135">Create a <xref:System.Reflection.Emit.DynamicMethod>.</span></span> <span data-ttu-id="448cc-136">이 예제에서는 메서드에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-136">In this example the method has no name.</span></span> <span data-ttu-id="448cc-137">반환 값의 형식은 `int`(Visual Basic에서는 `Integer`)로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-137">The type of the return value is specified as `int` (`Integer` in Visual Basic).</span></span> <span data-ttu-id="448cc-138">메서드는 `Example` 클래스의 private 및 protected 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-138">The method has access to the private and protected members of the `Example` class.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  <span data-ttu-id="448cc-139">메서드 본문을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-139">Emit the method body.</span></span> <span data-ttu-id="448cc-140">이 예제에서 <xref:System.Reflection.Emit.ILGenerator> 개체는 MSIL(Microsoft Intermediate Language)을 내보내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-140">In this example, an <xref:System.Reflection.Emit.ILGenerator> object is used to emit the Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="448cc-141">또는 <xref:System.Reflection.Emit.DynamicILInfo> 개체를 비관리 코드 생성기와 함께 사용하여 <xref:System.Reflection.Emit.DynamicMethod>에 대한 메서드 본문을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-141">Alternatively, a <xref:System.Reflection.Emit.DynamicILInfo> object can be used in conjunction with unmanaged code generators to emit the method body for a <xref:System.Reflection.Emit.DynamicMethod>.</span></span>  
  
     <span data-ttu-id="448cc-142">이 예제의 MSIL은 `Example` 클래스 인스턴스인 첫 번째 인수를 로드하고 `int` 형식의 private 인스턴스 필드 값을 로드하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-142">The MSIL in this example loads the first argument, which is an instance of the `Example` class, and uses it to load the value of a private instance field of type `int`.</span></span> <span data-ttu-id="448cc-143">두 번째 인수가 로드되고, 두 개의 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-143">The second argument is loaded, and the two numbers are multiplied.</span></span> <span data-ttu-id="448cc-144">결과가 `int`보다 크면 값이 잘리고, 최상위 비트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-144">If the result is larger than `int`, the value is truncated and the most significant bits are discarded.</span></span> <span data-ttu-id="448cc-145">메서드가 반환하고 반환 값이 스택에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-145">The method returns, with the return value on the stack.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  <span data-ttu-id="448cc-146"><xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29> 메서드 오버로드를 호출하여 동적 메서드를 나타내는 대리자 인스턴스(1단계에서 선언됨)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-146">Create an instance of the delegate (declared in step 1) that represents the dynamic method by calling the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29> method overload.</span></span> <span data-ttu-id="448cc-147">대리자를 만들면 메서드가 완성되고, MSIL 추가 등 메서드를 변경하려는 이후의 모든 시도는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-147">Creating the delegate completes the method, and any further attempts to change the method — for example, adding more MSIL — are ignored.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="448cc-148"><xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 여러 번 호출하여 대상 형식의 다른 인스턴스에 바인딩된 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-148">You can call the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method multiple times to create delegates bound to other instances of the target type.</span></span>  
  
     <span data-ttu-id="448cc-149">다음 코드는 private 테스트 필드가 42로 설정된 `Example` 클래스의 새 인스턴스에 메서드를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-149">The following code binds the method to a new instance of the `Example` class whose private test field is set to 42.</span></span> <span data-ttu-id="448cc-150">즉, 대리자를 호출할 때마다 `Example` 인스턴스가 메서드의 첫 번째 매개 변수에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-150">That is, each time the delegate is invoked the instance of `Example` is passed to the first parameter of the method.</span></span>  
  
     <span data-ttu-id="448cc-151">메서드의 첫 번째 매개 변수는 항상 `Example` 인스턴스를 받기 때문에 `OneParameter` 대리자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-151">The delegate `OneParameter` is used because the first parameter of the method always receives the instance of `Example`.</span></span> <span data-ttu-id="448cc-152">대리자를 호출하는 경우 두 번째 매개 변수만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-152">When the delegate is invoked, only the second parameter is required.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="448cc-153">예</span><span class="sxs-lookup"><span data-stu-id="448cc-153">Example</span></span>  
 <span data-ttu-id="448cc-154">다음 코드 예제에서는 간단한 동적 메서드 및 클래스 인스턴스에 바인딩된 동적 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-154">The following code example demonstrates a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>  
  
 <span data-ttu-id="448cc-155">간단한 동적 메서드는 32비트 정수인 인수 하나를 사용하고 해당 정수의 64비트 거듭제곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-155">The simple dynamic method takes one argument, a 32-bit integer, and returns the 64-bit square of that integer.</span></span> <span data-ttu-id="448cc-156">제네릭 대리자는 메서드를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-156">A generic delegate is used to invoke the method.</span></span>  
  
 <span data-ttu-id="448cc-157">두 번째 동적 메서드에는 `Example` 형식과 `int`(Visual Basic에서는 `Integer`) 형식의 두 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-157">The second dynamic method has two parameters, of type `Example` and type `int` (`Integer` in Visual Basic).</span></span> <span data-ttu-id="448cc-158">동적 메서드를 만들면 `int` 형식의 인수 하나가 있는 제네릭 대리자를 사용하여 `Example` 인스턴스에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-158">When the dynamic method has been created, it is bound to an instance of `Example`, using a generic delegate that has one argument of type `int`.</span></span> <span data-ttu-id="448cc-159">메서드의 첫 번째 매개 변수는 항상 `Example`의 바인딩된 인스턴스를 받기 때문에 대리자에 `Example` 형식의 인수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-159">The delegate does not have an argument of type `Example` because the first parameter of the method always receives the bound instance of `Example`.</span></span> <span data-ttu-id="448cc-160">대리자를 호출할 때 `int` 인수만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-160">When the delegate is invoked, only the `int` argument is supplied.</span></span> <span data-ttu-id="448cc-161">이 동적 메서드는 `Example` 클래스의 private 필드에 액세스하고 private 필드와 `int` 인수의 곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-161">This dynamic method accesses a private field of the `Example` class and returns the product of the private field and the `int` argument.</span></span>  
  
 <span data-ttu-id="448cc-162">코드 예제에서는 메서드 실행에 사용할 수 있는 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-162">The code example defines delegates that can be used to execute the methods.</span></span>  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="448cc-163">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="448cc-163">Compiling the Code</span></span>  
  
-   <span data-ttu-id="448cc-164">코드에는 컴파일하는 데 필요한 C# `using` 문(Visual Basic에서는 `Imports`)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-164">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="448cc-165">추가 어셈블리 참조는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-165">No additional assembly references are required.</span></span>  
  
-   <span data-ttu-id="448cc-166">csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-166">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="448cc-167">Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로그램 프로젝트 템플릿에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="448cc-167">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448cc-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448cc-168">See Also</span></span>  
 <xref:System.Reflection.Emit.DynamicMethod>  
 [<span data-ttu-id="448cc-169">리플렉션 내보내기 사용</span><span class="sxs-lookup"><span data-stu-id="448cc-169">Using Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)  
 [<span data-ttu-id="448cc-170">리플렉션 내보내기 동적 메서드 시나리오</span><span class="sxs-lookup"><span data-stu-id="448cc-170">Reflection Emit Dynamic Method Scenarios</span></span>](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)

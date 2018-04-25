---
title: 참조 반환 값 및 참조 로컬(C# 가이드)
description: 참조 반환 및 참조 로컬 값을 정의하고 사용하는 방법을 알아봅니다.
author: rpetrusha
ms.author: ronpet
ms.date: 04/04/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 57fa8f52320b30a1cb228b41e3f5e6655c235561
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="ff170-103">참조 반환 및 참조 로컬</span><span class="sxs-lookup"><span data-stu-id="ff170-103">Ref returns and ref locals</span></span>

<span data-ttu-id="ff170-104">C# 7부터 C#에서 참조 반환 값(ref return)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-104">Starting with C# 7, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="ff170-105">참조 반환 값을 사용하면 메서드가 값이 아니라 변수 참조를 호출자에게 다시 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-105">A reference return value allows a method to return a reference to a variable, rather than a value, back to a caller.</span></span> <span data-ttu-id="ff170-106">그러면 호출자는 반환된 변수를 마치 값이나 참조로 반환된 것처럼 처리하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-106">The caller can then choose to treat the returned variable as if it were returned by value or by reference.</span></span> <span data-ttu-id="ff170-107">호출자는 참조 로컬이라고 하는, 반환된 값에 대한 참조 자체인 새 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-107">The caller can create a new variable that is itself a reference to the returned value, called a ref local.</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="ff170-108">참조 반환 값이란?</span><span class="sxs-lookup"><span data-stu-id="ff170-108">What is a reference return value?</span></span>

<span data-ttu-id="ff170-109">대부분의 개발자는 호출된 메서드에 인수를 *참조로* 전달하는 데 익숙합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="ff170-110">호출된 메서드의 인수 목록에는 참조로 전달되는 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-110">A called method's argument list includes a variable passed by reference.</span></span> <span data-ttu-id="ff170-111">호출자는 호출된 메서드에 의한 해당 값의 변경 내용을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-111">Any changes made to its value by the called method are observed by the caller.</span></span> <span data-ttu-id="ff170-112">‘참조 반환 값’은 메서드가 일부 변수에 대한 ‘참조’(또는 별칭)를 반환한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-112">A *reference return value* means that a method returns a *reference* (or an alias) to some variable.</span></span> <span data-ttu-id="ff170-113">해당 변수의 범위는 메서드를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-113">That variable's scope must include the method.</span></span> <span data-ttu-id="ff170-114">해당 변수의 수명은 메서드의 반환 이후로 연장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-114">That variable's lifetime must extend beyond the return of the method.</span></span> <span data-ttu-id="ff170-115">호출자가 메서드의 반환 값을 수정하면 메서드가 반환한 변수가 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-115">Modifications to the method's return value by the caller are made to the variable that is returned by the method.</span></span>

<span data-ttu-id="ff170-116">메서드가 ‘참조 반환 값’을 반환한다는 선언은 메서드가 변수에 별칭을 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-116">Declaring that a method returns a *reference return value* indicates that the method returns an alias to a variable.</span></span> <span data-ttu-id="ff170-117">설계 의도에 따라 호출 코드가 변수 수정을 비롯하여 별칭을 통해 해당 변수에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-117">The design intent is often that the calling code should have access to that variable through the alias, including to modify it.</span></span> <span data-ttu-id="ff170-118">결과적으로 참조로 반환하는 메서드는 `void` 반환 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-118">It follows that methods returning by reference can't have the return type `void`.</span></span>

<span data-ttu-id="ff170-119">메서드가 참조 반환 값으로 반환할 수 있는 식에는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-119">There are some restrictions on the expression that a method can return as a reference return value.</span></span> <span data-ttu-id="ff170-120">제한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-120">Restrictions include:</span></span>

- <span data-ttu-id="ff170-121">반환 값의 수명은 메서드 실행 이후까지 연장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-121">The return value must have a lifetime that extends beyond the execution of the method.</span></span> <span data-ttu-id="ff170-122">즉, 반환하는 메서드의 지역 변수일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-122">In other words, it cannot be a local variable in the method that returns it.</span></span> <span data-ttu-id="ff170-123">클래스의 인스턴스 또는 정적 필드이거나 메서드에 전달된 인수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-123">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="ff170-124">지역 변수를 반환하려고 하면 컴파일러 오류 CS8168, “’obj’ 로컬은 참조 로컬이 아니므로 참조로 반환할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-124">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="ff170-125">반환 값은 리터럴 `null`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-125">The return value cannot be the literal `null`.</span></span> <span data-ttu-id="ff170-126">`null`을 반환하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-126">Returning `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="ff170-127">참조 반환이 있는 메서드는 값이 현재 null(인스턴스화되지 않음) 값이거나 값 형식이 [nullable 형식](../nullable-types/index.md)인 변수에 별칭을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-127">A method with a ref return can return an alias to a variable whose value is currently the null (uninstantiated) value or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="ff170-128">반환 값은 상수, 열거형 멤버, 속성의 값 형식 반환 값 또는 `class`나 `struct`의 메서드일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-128">The return value cannot be a constant, an enumeration member, the by-value return value from a property, or a method of a `class` or `struct`.</span></span> <span data-ttu-id="ff170-129">이 규칙을 위반하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-129">Violating this rule generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="ff170-130">또한 참조 반환 값은 비동기 메서드에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-130">In addition, reference return values are not allowed on async methods.</span></span> <span data-ttu-id="ff170-131">비동기 메서드는 실행을 마치기 전에 반환할 수 있지만 반환 값을 여전히 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-131">An asynchronous method may return before it has finished execution, while its return value is still unknown.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="ff170-132">참조 반환 값 정의</span><span class="sxs-lookup"><span data-stu-id="ff170-132">Defining a ref return value</span></span>

<span data-ttu-id="ff170-133">메서드 시그니처의 반환 형식에 [ref](../../language-reference/keywords/ref.md) 키워드를 추가하여 참조 반환 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-133">You define a ref return value by adding the [ref](../../language-reference/keywords/ref.md) keyword to the return type of the method signature.</span></span> <span data-ttu-id="ff170-134">예를 들어 다음 시그니처는 `GetContactInformation` 속성이 `Person` 개체에 대한 참조를 호출자에게 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-134">For example, the following signature indicates that the `GetContactInformation` property returns a reference to a `Person` object to the caller:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

<span data-ttu-id="ff170-135">또한 메서드 본문의 각 [return](../../language-reference/keywords/return.md) 문에서 반환되는 개체의 이름 앞에는 [ref](../../language-reference/keywords/ref.md) 키워드가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-135">In addition, the name of the object returned by each [return](../../language-reference/keywords/return.md) statement in the method body must be preceded by the [ref](../../language-reference/keywords/ref.md) keyword.</span></span> <span data-ttu-id="ff170-136">예를 들어 다음 `return` 문은 `p`라는 `Person` 개체에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-136">For example, the following `return` statement returns a reference to a `Person` object named `p`:</span></span>

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="ff170-137">참조 반환 값 사용</span><span class="sxs-lookup"><span data-stu-id="ff170-137">Consuming a ref return value</span></span>

<span data-ttu-id="ff170-138">참조 반환 값은 호출된 메서드 범위 내 다른 변수에 대한 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-138">The ref return value is an alias to another variable in the called method's scope.</span></span> <span data-ttu-id="ff170-139">참조 반환의 사용은 다음과 같이 별칭이 있는 변수를 사용하는 것으로 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-139">You can interpret any use of the ref return as using the variable it aliases:</span></span>

- <span data-ttu-id="ff170-140">해당 값을 할당할 경우 별칭이 있는 변수에 값을 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-140">When you assign its value, you are assigning a value to the variable it aliases.</span></span>
- <span data-ttu-id="ff170-141">해당 값을 읽을 경우 별칭이 있는 변수의 값을 읽는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-141">When you read its value, you are reading the value of the variable it aliases.</span></span>
- <span data-ttu-id="ff170-142">‘참조로’ 반환하는 경우 동일한 변수에 대한 별칭을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-142">If you return it *by reference*, you are returning an alias to that same variable.</span></span>
- <span data-ttu-id="ff170-143">다른 메서드에 ‘참조로’ 전달하는 경우 별칭이 있는 변수에 대한 참조를 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-143">If you pass it to another method *by reference*, you are passing a reference to the variable it aliases.</span></span>
- <span data-ttu-id="ff170-144">[참조 로컬](#ref-local) 별칭을 만들 경우 동일한 변수에 대한 새 별칭을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-144">When you make a [ref local](#ref-local) alias, you make a new alias to the same variable.</span></span>


## <a name="ref-locals"></a><span data-ttu-id="ff170-145">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="ff170-145">Ref locals</span></span>

<span data-ttu-id="ff170-146">`GetContactInformation` 메서드가 다음과 같이 참조 반환으로 선언된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-146">Assume the `GetContactInformation` method is declared as a ref return:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

<span data-ttu-id="ff170-147">값 형식 할당은 변수의 값을 읽고 다음과 같이 새 변수에 해당 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-147">A by-value assignment reads the value of a variable and assigns it to a new variable:</span></span>

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="ff170-148">이전의 할당은 `p`를 지역 변수로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-148">The preceding assignment declares `p` as a local variable.</span></span> <span data-ttu-id="ff170-149">초기 값은 `GetContactInformation`으로 반환된 값을 읽은 것에서 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-149">Its initial value is copied from reading the value returned by `GetContactInformation`.</span></span> <span data-ttu-id="ff170-150">향후 `p`에 대한 할당이 `GetContactInformation`으로 반환된 변수의 값을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-150">Any future assignments to `p` will not change the value of the variable returned by `GetContactInformation`.</span></span> <span data-ttu-id="ff170-151">`p` 변수는 더 이상 반환된 변수에 대한 별칭이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-151">The variable `p` is no longer an alias to the variable returned.</span></span>

<span data-ttu-id="ff170-152">‘참조 로컬’ 변수를 선언하여 원래 값에 대한 별칭을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-152">You declare a *ref local* variable to copy the alias to the original value.</span></span> <span data-ttu-id="ff170-153">다음 할당에서 `p`는 `GetContactInformation`에서 반환된 변수에 대한 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-153">In the following assignment, `p` is an alias to the variable returned from `GetContactInformation`.</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="ff170-154">`p`가 해당 변수의 별칭이므로 이후 `p` 사용은 `GetContactInformation`에서 반환된 변수를 사용하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-154">Subsequent usage of `p` is the same as using the variable returned by `GetContactInformation` because `p` is an alias for that variable.</span></span> <span data-ttu-id="ff170-155">또한 `p`를 변경하면 `GetContactInformation`에서 반환된 변수도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-155">Changes to `p` also change the variable returned from `GetContactInformation`.</span></span>

<span data-ttu-id="ff170-156">`ref` 키워드는 지역 변수 선언 앞, ‘그리고’ 메서드 호출 앞에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-156">The `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> 

<span data-ttu-id="ff170-157">동일한 방법으로 참조로 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-157">You can access a value by reference in the same way.</span></span> <span data-ttu-id="ff170-158">경우에 따라 참조로 값에 액세스하면 비용이 많이 들 수 있는 복사 작업을 피함으로써 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-158">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="ff170-159">예를 들어, 다음 명령문은 값을 참조하는 데 사용되는 참조 로컬 값을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-159">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="ff170-160">`ref` 키워드는 지역 변수 선언 앞 ‘그리고’ 두 번째 예의 값 앞에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-160">The `ref` keyword is used both before the local variable declaration *and* before the value in the second example.</span></span> <span data-ttu-id="ff170-161">두 예에서 변수 선언과 할당에 `ref` 키워드를 둘 다 포함하지 않으면 컴파일러 오류 CS8172, "값을 사용하여 참조 형식 변수를 초기화할 수 없습니다."가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-161">Failure to include both `ref` keywords in the variable declaration and assignment in both examples results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 

<span data-ttu-id="ff170-162">C# 7.3 이전에 참조 로컬 변수는 초기화되기 전에 다른 저장소 공간을 참조하도록 다시 할당될 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-162">Prior to C# 7.3, ref local variables couldn't be reassigned to refer to different storage after being initialized.</span></span> <span data-ttu-id="ff170-163">해당 제한 사항이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-163">That restriction has been removed.</span></span> <span data-ttu-id="ff170-164">다음 예제에서는 재할당을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-164">The following example shows a reassignment:</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

 <span data-ttu-id="ff170-165">참조 로컬 변수는 선언될 때 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-165">Ref local variables must still be initialized when they are declared.</span></span>

## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="ff170-166">참조 반환 및 참조 로컬: 예제</span><span class="sxs-lookup"><span data-stu-id="ff170-166">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="ff170-167">다음 예제에서는 정수 값의 배열을 저장하는 `NumberStore` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-167">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="ff170-168">`FindNumber` 메서드는 인수로 전달된 숫자보다 크거나 같은 첫 번째 숫자를 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-168">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="ff170-169">인수보다 크거나 같은 숫자가 없으면 메서드는 인덱스 0의 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-169">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#1)]

<span data-ttu-id="ff170-170">다음 예제에서는 `NumberStore.FindNumber` 메서드를 호출하여 16보다 크거나 같은 첫 번째 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-170">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="ff170-171">그런 다음 호출자가 메서드에서 반환된 값을 두 배로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-171">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="ff170-172">예제의 출력에서는 `NumberStore` 인스턴스의 배열 요소 값에 반영된 변경 내용을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-172">The output from the example shows the change reflected in the value of the array elements of the `NumberStore` instance.</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#2)]

<span data-ttu-id="ff170-173">참조 반환 값이 지원되지 않을 경우 이러한 작업은 해당 값과 함께 배열 요소의 인덱스를 반환하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-173">Without support for reference return values, such an operation is performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="ff170-174">그런 다음 호출자는 이 인덱스를 사용하여 별도 메서드 호출에서 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-174">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="ff170-175">그러나 호출자가 인덱스를 수정하여 다른 배열 값에 액세스하고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-175">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  

<span data-ttu-id="ff170-176">다음 예제에서는 C# 7.3 이후에 `FindNumber` 메서드를 다시 작성하여 참조 로컬 재할당을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-176">The following example shows how the `FindNumber` method could be rewritten after C# 7.3 to use ref local reassignment:</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStoreUpdated.cs#1)]

<span data-ttu-id="ff170-177">이 두 번째 버전은 검색된 수가 배열의 끝에 더 가까운 시나리오에서 더 긴 시퀀스를 사용하여 더욱 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="ff170-177">This second version is more efficient with longer sequences in scenarios where the number sought is closer to the end of the array.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff170-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff170-178">See also</span></span>

[<span data-ttu-id="ff170-179">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="ff170-179">ref keyword</span></span>](../../language-reference/keywords/ref.md)  
[<span data-ttu-id="ff170-180">값 형식과 참조 의미 체계</span><span class="sxs-lookup"><span data-stu-id="ff170-180">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)

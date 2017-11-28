---
title: "참조 반환 값 및 참조 로컬(C# 가이드)"
description: "참조 반환 및 참조 로컬 값을 정의하고 사용하는 방법을 알아봅니다."
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.openlocfilehash: 1d8fb092b578602b5d4f791a3fd14f47dfae1ba6
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="57195-103">참조 반환 및 참조 로컬</span><span class="sxs-lookup"><span data-stu-id="57195-103">Ref returns and ref locals</span></span>

<span data-ttu-id="57195-104">C# 7부터 C#에서 참조 반환 값(ref return)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-104">Starting with C# 7, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="57195-105">참조 반환 값을 사용하면 메서드가 값이 아니라 개체 참조를 호출자에게 다시 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-105">A reference return value allows a method to return a reference to an object, rather than a value, back to a caller.</span></span> <span data-ttu-id="57195-106">그러면 호출자가 값이나 참조로 반환된 것처럼 반환된 개체를 처리하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-106">The caller can then choose to treat the returned object returned as if it were returned by value or by reference.</span></span> <span data-ttu-id="57195-107">호출자가 값이 아니라 참조로 처리하는 참조로 반환된 값은 참조 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="57195-107">A value returned by reference that the caller handles as a reference rather than a value is a ref local.</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="57195-108">참조 반환 값이란?</span><span class="sxs-lookup"><span data-stu-id="57195-108">What is a reference return value?</span></span>

<span data-ttu-id="57195-109">대부분의 개발자는 호출된 메서드에 인수를 *참조로* 전달하는 데 익숙합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="57195-110">호출된 메서드의 인수 목록에는 참조로 전달된 값이 포함되며, 호출된 메서드가 해당 값을 변경할 경우 변경 내용이 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-110">A called method's argument list includes a value passed by reference, and any changes made to its value by the called method are returned to the caller.</span></span> <span data-ttu-id="57195-111">*참조 반환 값*은 그 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="57195-111">A *reference return value* is the opposite:</span></span>

- <span data-ttu-id="57195-112">전달된 인수가 아니라 호출된 메서드의 반환 값이 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="57195-112">The called method's return value, rather than an argument passed to it, is a reference.</span></span>

- <span data-ttu-id="57195-113">호출된 메서드가 아니라 호출자가 메서드에 의해 반환된 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-113">The caller, rather than the called method, can modify the value returned by the method.</span></span>

- <span data-ttu-id="57195-114">호출자의 개체 상태에 반영되는 인수 수정 대신, 호출자의 메서드 반환 값 수정은 해당 메서드가 호출된 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-114">Instead of modifications to the argument that are reflected in state of the object on the caller, modifications to the method's return value by the caller are reflected in the state of the object whose method was called.</span></span>

<span data-ttu-id="57195-115">참조 반환 값은 더욱 간단한 코드를 생성할 수 있을 뿐만 아니라 개체가 호출자에게 중요한 배열 요소 등의 개별 데이터 항목만 공개하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-115">Reference return values can produce more compact code, as well as allow an object to expose only the individual data items, such as an array element, that are of interest to the caller.</span></span> <span data-ttu-id="57195-116">이렇게 하면 호출자가 개체 상태를 실수로 수정할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="57195-116">This reduces the likelihood that the caller will inadvertently modify the object's state.</span></span>

<span data-ttu-id="57195-117">메서드가 참조 반환 값으로 반환할 수 있는 값에는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-117">There are some restrictions on the value that a method can return as a reference return value.</span></span> <span data-ttu-id="57195-118">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-118">These include:</span></span>

- <span data-ttu-id="57195-119">반환 값은 `void`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-119">The return value cannot be `void`.</span></span> <span data-ttu-id="57195-120">`void` 참조 반환 값으로 메서드를 정의하려고 하면 컴파일러 오류 CS1547, “이 컨텍스트에는 ‘void’ 키워드를 사용할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-120">Attempting to define a method with a `void` reference return value generates compiler error CS1547, "Keyword 'void' cannot be used in this context."</span></span>
 
- <span data-ttu-id="57195-121">반환 값은 반환하는 메서드의 지역 변수일 수 없습니다. 범위가 반환하는 메서드를 벗어나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-121">The return value cannot be a local variable in the method that returns it; it must have a scope that is outside the method that returns it.</span></span> <span data-ttu-id="57195-122">클래스의 인스턴스 또는 정적 필드이거나 메서드에 전달된 인수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-122">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="57195-123">지역 변수를 반환하려고 하면 컴파일러 오류 CS8168, “’obj’ 로컬은 참조 로컬이 아니므로 참조로 반환할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-123">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="57195-124">반환 값은 `null`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-124">The return value cannot be a `null`.</span></span> <span data-ttu-id="57195-125">`null`을 반환하려고 하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-125">Attempting to return `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="57195-126">참조 반환을 사용한 메서드에서 null 값을 반환해야 하는 경우 참조 형식에 대해 null(인스턴스화되지 않은) 값을 반환하거나 값 형식에 대해 [nullable 형식](../nullable-types/index.md)을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-126">If a method with a ref return needs to return a null value, you can either return a null (uninstantiated) value for a reference type or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="57195-127">반환 값은 상수, 열거형 멤버, `class` 또는 `struct`의 속성일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-127">The return value cannot be a constant, an enumeration member, or a property of a `class` or `struct`.</span></span> <span data-ttu-id="57195-128">이러한 값을 반환하려고 하면 컴파일러 오류 CS8156, “식이 참조로 반환될 수 없으므로 이 컨텍스트에서 해당 식을 사용할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-128">Attempting to return these generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="57195-129">또한 비동기 메서드는 실행을 마치기 전에 반환할 수 있으므로, 해당 반환 값을 여전히 알 수 없는 동안 비동기 메서드에서는 참조 반환 값이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-129">In addition, because an asynchronous method may return before it has finished execution, while its return value is still unknown, reference return values are not allowed on async methods.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="57195-130">참조 반환 값 정의</span><span class="sxs-lookup"><span data-stu-id="57195-130">Defining a ref return value</span></span>

<span data-ttu-id="57195-131">메서드 시그니처의 반환 형식에 [ref](../../language-reference/keywords/ref.md) 키워드를 추가하여 참조 반환 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-131">You define a ref return value by adding the [ref](../../language-reference/keywords/ref.md) keyword to the return type of the method signature.</span></span> <span data-ttu-id="57195-132">예를 들어 다음 시그니처는 `GetContactInformation` 속성이 `Person` 개체에 대한 참조를 호출자에게 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57195-132">For example, the following signature indicates that the `GetContactInformation` property returns a reference to a `Person` object to the caller:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

<span data-ttu-id="57195-133">또한 메서드 본문의 각 [return](../../language-reference/keywords/return.md) 문에서 반환되는 개체의 이름 앞에는 [ref](../../language-reference/keywords/ref.md) 키워드가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-133">In addition, the name of the object returned by each [return](../../language-reference/keywords/return.md) statement in the method body must be preceded by the [ref](../../language-reference/keywords/ref.md) keyword.</span></span> <span data-ttu-id="57195-134">예를 들어 다음 `return` 문은 `p`라는 `Person` 개체를 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-134">For example, the following `return` statement returns a `Person` object named `p` by reference:</span></span>

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="57195-135">참조 반환 값 사용</span><span class="sxs-lookup"><span data-stu-id="57195-135">Consuming a ref return value</span></span>

<span data-ttu-id="57195-136">호출자는 다음 두 가지 방법 중 하나로 참조 반환 값을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-136">A caller can handle a ref return value in either of two ways:</span></span>

- <span data-ttu-id="57195-137">메서드에서 값으로 반환된 일반 값.</span><span class="sxs-lookup"><span data-stu-id="57195-137">As an ordinary value returned by value from a method.</span></span> <span data-ttu-id="57195-138">호출자는 반환 값이 참조 반환 값임을 무시하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-138">The caller can choose to ignore that the return value is a reference return value.</span></span> <span data-ttu-id="57195-139">이 경우 메서드 호출에서 반환된 값을 변경해도 호출된 형식의 상태에 변경 내용이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-139">In this case, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span> <span data-ttu-id="57195-140">반환된 값이 값 형식인 경우 메서드 호출에서 반환된 값을 변경해도 호출된 형식의 상태에 변경 내용이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-140">If the returned value is a value type, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span>

- <span data-ttu-id="57195-141">참조 반환 값.</span><span class="sxs-lookup"><span data-stu-id="57195-141">As a reference return value.</span></span> <span data-ttu-id="57195-142">호출자가 참조 반환 값이 할당되는 변수를 [참조 로컬](#ref-local)로 정의해야 하며, 메서드 호출에서 반환된 값을 변경하면 호출된 형식의 상태에 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-142">The caller must define the variable to which the reference return value is assigned as a [ref local](#ref-local), and any changes to the value returned by the method call are reflected in the state of the called type.</span></span> 

## <a name="ref-locals"></a><span data-ttu-id="57195-143">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="57195-143">Ref locals</span></span>

<span data-ttu-id="57195-144">참조 반환 값을 참조로 처리하려면 호출자가 `ref` 키워드를 사용하여 값을 *참조 로컬*로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-144">To handle the reference return value as a reference, the caller must declare the value to be a *ref local* by using the `ref` keyword.</span></span> <span data-ttu-id="57195-145">예를 들어 `Person.GetContactInfomation` 메서드에서 반환된 값을 값이 아니라 참조로 사용해야 하는 경우 메서드 호출이 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="57195-145">For example, if the value returned by the `Person.GetContactInfomation` method is to be consumed as a reference rather than a value, the method call appears as:</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="57195-146">`ref` 키워드는 지역 변수 선언 앞, *그리고* 메서드 호출 앞에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-146">Note that the `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> <span data-ttu-id="57195-147">변수 선언과 할당에 `ref` 키워드를 둘 다 포함하지 않으면 컴파일러 오류 CS8172, “값을 사용하여 참조 형식 변수를 초기화할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-147">Failure to include both `ref` keywords in the variable declaration and assignment results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
<span data-ttu-id="57195-148">메서드에서 반환된 `Person` 개체에 대한 후속 변경 내용은 `contacts` 개체에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-148">Subsequent changes to the `Person` object returned by the method are reflected in the `contacts` object.</span></span>

<span data-ttu-id="57195-149">`ref` 키워드를 사용하여 `p`가 참조 로컬로 정의되지 않은 경우 `p`에 대한 호출자의 변경 내용이 `contacts` 개체에 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-149">If `p` is not defined as a ref local by using the `ref` keyword, any changes made to `p` by the caller are not reflected in the `contacts` object.</span></span>
 
## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="57195-150">참조 반환 및 참조 로컬: 예제</span><span class="sxs-lookup"><span data-stu-id="57195-150">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="57195-151">다음 예제에서는 정수 값의 배열을 저장하는 `NumberStore` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-151">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="57195-152">`FindNumber` 메서드는 인수로 전달된 숫자보다 크거나 같은 첫 번째 숫자를 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-152">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="57195-153">인수보다 크거나 같은 숫자가 없으면 메서드는 인덱스 0의 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-153">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

<span data-ttu-id="57195-154">다음 예제에서는 `NumberStore.FindNumber` 메서드를 호출하여 16보다 크거나 같은 첫 번째 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="57195-154">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="57195-155">그런 다음 호출자가 메서드에서 반환된 값을 두 배로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57195-155">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="57195-156">예제의 출력에서 볼 수 있듯이 이 변경 내용은 `NumberStore` 인스턴스의 배열 요소 값에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-156">As the output from the example shows, this change is reflected in the value of the array elements of the `NumberStore` instance.</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

<span data-ttu-id="57195-157">참조 반환 값이 지원되지 않을 경우 이러한 작업은 일반적으로 해당 값과 함께 배열 요소의 인덱스를 반환하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="57195-157">Without support for reference return values, such an operation is usually performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="57195-158">그런 다음 호출자는 이 인덱스를 사용하여 별도 메서드 호출에서 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-158">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="57195-159">그러나 호출자가 인덱스를 수정하여 다른 배열 값에 액세스하고 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57195-159">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="57195-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57195-160">See also</span></span>

[<span data-ttu-id="57195-161">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="57195-161">ref keyword</span></span>](../../language-reference/keywords/ref.md)

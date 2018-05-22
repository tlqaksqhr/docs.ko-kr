---
title: 명명된 인수와 선택적 인수(C# 프로그래밍 가이드)
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: b0963457e22bf0c3fc92d33c5ed0eb699be27cf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="dc6f9-102">명명된 인수와 선택적 인수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="dc6f9-102">Named and Optional Arguments (C# Programming Guide)</span></span>
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]<span data-ttu-id="dc6f9-103">에서는 명명된 인수 및 선택적 인수를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-103"> introduces named and optional arguments.</span></span> <span data-ttu-id="dc6f9-104">*명명된 인수*를 사용하면 인수를 매개 변수 목록 내의 매개 변수 위치가 아니라 매개 변수 이름과 연결하여 특정 매개 변수에 대한 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="dc6f9-105">*선택적 인수*를 사용하면 일부 매개 변수에 대한 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="dc6f9-106">두 기법 모두 메서드, 인덱서, 생성자 및 대리자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="dc6f9-107">명명된 인수와 선택적 인수를 사용하는 경우 매개 변수 목록이 아니라 인수 목록에 표시되는 순서대로 인수가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="dc6f9-108">명명된 매개 변수와 선택적 매개 변수를 함께 사용하는 경우 선택적 매개 변수 목록에서 몇 개의 매개 변수에 대해서만 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="dc6f9-109">이 기능은 Microsoft Office 자동화 API와 같은 COM 인터페이스에 대한 호출에 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="dc6f9-110">명명된 인수</span><span class="sxs-lookup"><span data-stu-id="dc6f9-110">Named Arguments</span></span>  
 <span data-ttu-id="dc6f9-111">명명된 인수를 사용하면 호출된 메서드의 매개 변수 목록에서 매개 변수의 순서를 기억하거나 조회할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="dc6f9-112">각 인수에 대한 매개 변수를 매개 변수 이름으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="dc6f9-113">예를 들어 함수에 정의된 순서의 위치로 인수를 보내서 표준 방법으로 주문 세부 정보(예: 판매자 이름, 주문 번호 및 제품 이름)를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-113">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="dc6f9-114">매개 변수의 순서를 기억하지 못하지만 해당 이름을 알고 있는 경우 임의의 순서로 인수를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-114">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="dc6f9-115">또한 명명된 인수는 각 인수가 무엇을 나타내는지를 식별하여 코드의 가독성을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="dc6f9-116">아래 예제 메서드에서 `sellerName`은 null 또는 공백일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-116">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="dc6f9-117">`sellerName` 및 `productName`은 모두 문자열 형식이므로, 위치로 인수를 보내는 대신, 명명된 인수를 사용하여 두 코드를 구분하고 코드를 읽는 사람의 혼동을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-117">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="dc6f9-118">위치 인수와 함께 사용된 명명된 인수는</span><span class="sxs-lookup"><span data-stu-id="dc6f9-118">Named arguments, when used with positional arguments, are valid as long as</span></span> 

- <span data-ttu-id="dc6f9-119">그 다음에 위치 인수가 없거나</span><span class="sxs-lookup"><span data-stu-id="dc6f9-119">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="dc6f9-120">_C# 7.2로 시작하고_ 올바른 위치에 사용되는 한 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-120">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="dc6f9-121">아래 예제에서 `orderNum` 매개 변수는 올바른 위치에 있지만 명시적으로 명명되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-121">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="dc6f9-122">그러나 순서 상관없이 명명된 인수는 그 다음에 위치 인수가 나오는 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-122">However, out-of-order named arguments are invalid if they're followed by positional arguments.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="dc6f9-123">예</span><span class="sxs-lookup"><span data-stu-id="dc6f9-123">Example</span></span>  
 <span data-ttu-id="dc6f9-124">다음 코드는 몇 가지 추가 코드와 함께 이 섹션의 예제를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-124">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="dc6f9-125">선택적 인수</span><span class="sxs-lookup"><span data-stu-id="dc6f9-125">Optional Arguments</span></span>  
 <span data-ttu-id="dc6f9-126">메서드, 생성자, 인덱서 또는 대리자의 정의에서 해당 매개 변수를 필수 또는 선택 사항으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-126">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="dc6f9-127">호출 시 모든 필수 매개 변수에 대한 인수를 제공해야 하지만 선택적 매개 변수에 대한 인수는 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-127">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="dc6f9-128">각 선택적 매개 변수에는 해당 정의의 일부로 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-128">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="dc6f9-129">해당 매개 변수에 대한 인수가 전송되지 않은 경우 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-129">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="dc6f9-130">기본값은 다음 유형의 식 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-130">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="dc6f9-131">상수 식</span><span class="sxs-lookup"><span data-stu-id="dc6f9-131">a constant expression;</span></span>  
  
-   <span data-ttu-id="dc6f9-132">`new ValType()` 형태의 식. 여기서 `ValType`은 [enum](../../../csharp/language-reference/keywords/enum.md) 또는 [struct](../../../csharp/programming-guide/classes-and-structs/structs.md)와 같은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-132">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="dc6f9-133">[default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) 형태의 식. 여기서 `ValType`은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-133">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="dc6f9-134">선택적 매개 변수는 매개 변수 목록의 끝에서 모든 필수 매개 변수 다음에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-134">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="dc6f9-135">호출자가 연속된 선택적 매개 변수 중 하나에 대한 인수를 제공하는 경우 이전의 모든 선택적 매개 변수에 대한 인수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-135">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="dc6f9-136">인수 목록에서 쉼표로 구분된 간격은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-136">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="dc6f9-137">예를 들어 다음 코드에서 인스턴스 메서드 `ExampleMethod`는 필수 매개 변수 하나와 선택적 매개 변수 두 개로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-137">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 <span data-ttu-id="dc6f9-138">다음과 같은 `ExampleMethod` 호출에서는 세 번째 매개 변수에 대한 인수가 제공되었지만 두 번째 매개 변수에 대한 인수는 제공되지 않았기 때문에 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-138">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="dc6f9-139">그러나 세 번째 매개 변수의 이름을 알고 있으면 명명된 인수를 사용하여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-139">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="dc6f9-140">IntelliSense는 다음 그림과 같이 대괄호를 사용하여 선택적 매개 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-140">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="dc6f9-141">![ExampleMethod 메서드에 대한 IntelliSense 요약 정보](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="dc6f9-141">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="dc6f9-142">ExampleMethod의 선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc6f9-142">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc6f9-143">.NET <xref:System.Runtime.InteropServices.OptionalAttribute> 클래스를 사용하여 선택적 매개 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-143">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="dc6f9-144">`OptionalAttribute` 매개 변수는 기본값이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-144">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc6f9-145">예</span><span class="sxs-lookup"><span data-stu-id="dc6f9-145">Example</span></span>  
 <span data-ttu-id="dc6f9-146">다음 예제에서는 `ExampleClass`에 대한 생성자에 선택 사항인 매개 변수 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-146">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="dc6f9-147">인스턴스 메서드 `ExampleMethod`에는 `required`라는 필수 매개 변수 하나와 `optionalstr` 및 `optionalint`라는 선택적 매개 변수 두 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-147">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="dc6f9-148">`Main`의 코드는 생성자와 메서드를 호출할 수 있는 여러 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-148">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="dc6f9-149">COM 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc6f9-149">COM Interfaces</span></span>  
 <span data-ttu-id="dc6f9-150">동적 개체 및 기타 향상된 기능에 대한 지원과 더불어 명명된 인수와 선택적 인수는 Office 자동화 API와 같은 COM API와의 상호 운용성을 크게 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-150">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="dc6f9-151">예를 들어 Microsoft Office Excel [범위](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range(v=office.15).aspx) 인터페이스의 [AutoFormat](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.autoformat(v=office.15).aspx) 메서드에는 모두 선택 사항인 매개 변수 7개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-151">For example, the [AutoFormat](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.autoformat(v=office.15).aspx) method in the Microsoft Office Excel [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range(v=office.15).aspx) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="dc6f9-152">해당 매개 변수는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-152">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="dc6f9-153">![AutoFormat 메서드에 대한 IntelliSense 요약 정보](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="dc6f9-153">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="dc6f9-154">AutoFormat 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc6f9-154">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="dc6f9-155">C# 3.0 및 이전 버전에서는 다음 예제와 같이 각 매개 변수에 대한 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 <span data-ttu-id="dc6f9-156">그러나 C# 4.0에서 도입된 명명된 인수와 선택적 인수를 사용하면 `AutoFormat` 호출을 훨씬 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="dc6f9-157">명명된 인수와 선택적 인수를 사용하면 매개 변수의 기본값을 변경하지 않으려는 경우 선택적 매개 변수에 대한 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="dc6f9-158">다음 호출에서는 7개 매개 변수 중 하나에 대한 값만 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 <span data-ttu-id="dc6f9-159">자세한 내용 및 예제는 [방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) 및 [방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-159">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="dc6f9-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="dc6f9-160">Overload Resolution</span></span>  
 <span data-ttu-id="dc6f9-161">명명된 인수 및 선택적 인수를 사용하면 다음과 같은 방법으로 오버로드 확인에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="dc6f9-162">메서드, 인덱서 또는 생성자는 해당 매개 변수가 각각 선택 사항이거나 이름 또는 위치로 호출하는 문의 단일 인수에 해당하고 이 인수를 매개 변수의 형식으로 변환할 수 있는 경우 실행 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="dc6f9-163">둘 이상의 인증서가 있으면 기본 설정 변환에 대한 오버로드 확인 규칙이 명시적으로 지정된 인수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="dc6f9-164">선택적 매개 변수에 대해 생략된 인수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="dc6f9-165">두 후보가 똑같이 정상이라고 판단되는 경우 기본적으로 호출에서 인수가 생략된 선택적 매개 변수가 없는 후보가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="dc6f9-166">이는 매개 변수가 적은 후보에 대한 오버로드 확인에서 일반적인 기본 설정의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f9-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dc6f9-167">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="dc6f9-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc6f9-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc6f9-168">See Also</span></span>  
 [<span data-ttu-id="dc6f9-169">방법: Office 프로그래밍에서 명명된 인수 및 선택적 인수 사용</span><span class="sxs-lookup"><span data-stu-id="dc6f9-169">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [<span data-ttu-id="dc6f9-170">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="dc6f9-170">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="dc6f9-171">생성자 사용</span><span class="sxs-lookup"><span data-stu-id="dc6f9-171">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [<span data-ttu-id="dc6f9-172">인덱서 사용</span><span class="sxs-lookup"><span data-stu-id="dc6f9-172">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)

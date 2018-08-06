---
title: 최선의 예외 구현 방법
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd38b59e39f938d6347457100243f09935444d88
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "33578086"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="7f3f0-102">예외에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7f3f0-102">Best practices for exceptions</span></span>

<span data-ttu-id="7f3f0-103">잘 설계된 응용 프로그램이 응용 프로그램 충돌을 방지하기 위해 예외와 오류를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="7f3f0-104">이 섹션에서는 예외를 처리하고 만들기 위한 모범 사례를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks"></a><span data-ttu-id="7f3f0-105">try/catch/finally 블록 사용</span><span class="sxs-lookup"><span data-stu-id="7f3f0-105">Use try/catch/finally blocks</span></span>

<span data-ttu-id="7f3f0-106">잠재적으로 예외를 생성할 수 있는 코드 주변에서 `try`/`catch`/`finally` 블록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-106">Use `try`/`catch`/`finally` blocks around code that can potentially generate an exception.</span></span> 

<span data-ttu-id="7f3f0-107">`catch` 블록에서 항상 가장 특정한 예외부터 가장 일반적인 예외의 순서로 예외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-107">In `catch` blocks, always order exceptions from the most specific to the least specific.</span></span>

<span data-ttu-id="7f3f0-108">복구 가능 여부에 관계없이 `finally` 블록을 사용하여 리소스를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-108">Use a `finally` block to clean up resources, whether you can recover or not.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="7f3f0-109">예외를 throw하지 않고 일반적인 조건 처리</span><span class="sxs-lookup"><span data-stu-id="7f3f0-109">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="7f3f0-110">발생할 가능성이 높지만 예외를 트리거할 수도 있는 조건의 경우 예외를 방지하는 방식으로 조건을 처리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-110">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="7f3f0-111">예를 들어 이미 닫혀 있는 연결을 닫으려고 하면 `InvalidOperationException`이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-111">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="7f3f0-112">닫기 전에 `if` 문을 사용하여 연결 상태를 확인하면 이 예외를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-112">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

<span data-ttu-id="7f3f0-113">닫기 전에 연결 상태를 확인하지 않을 경우 `InvalidOperationException` 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-113">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

<span data-ttu-id="7f3f0-114">어떤 방법을 선택할 것인지는 해당 이벤트의 예상 발생 빈도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-114">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="7f3f0-115">이벤트가 그다지 자주 발생하지 않으면(즉, 예상치 못한 파일 끝과 같은 이벤트가 실제로 예외이고 오류를 나타내는 경우) 예외 처리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-115">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="7f3f0-116">예외 처리를 사용하면 정상적인 조건에서 적은 수의 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-116">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="7f3f0-117">이벤트가 일상적으로 발생하고 정상적인 실행의 일부로 간주될 수 있는 경우 코드에서 오류 조건을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-117">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="7f3f0-118">일반적인 오류 조건을 확인하면 예외가 방지되기 때문에 실행되는 코드가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-118">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="7f3f0-119">예외를 방지할 수 있도록 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="7f3f0-119">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="7f3f0-120">클래스는 예외를 트리거하는 호출을 방지할 수 있도록 하는 메서드 또는 속성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-120">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="7f3f0-121">예를 들어, <xref:System.IO.FileStream> 클래스는 파일 끝에 도달했는지 확인하는 데 도움이 되는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-121">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="7f3f0-122">이러한 메서드를 사용하면 파일의 끝을 지나서 읽을 경우 throw되는 예외를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-122">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="7f3f0-123">다음 예제에서는 예외를 트리거하지 않고 파일의 끝까지 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-123">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

<span data-ttu-id="7f3f0-124">예외를 방지하는 또 다른 방법은 매우 일반적인 오류의 경우 예외를 throw하는 대신 null을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-124">Another way to avoid exceptions is to return null for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="7f3f0-125">매우 흔한 오류 사례는 정상적인 제어 흐름으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-125">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="7f3f0-126">이러한 경우에 null을 반환함으로써, 응용 프로그램의 성능에 미치는 영향을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-126">By returning null in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="7f3f0-127">오류 코드를 반환하는 대신 예외 throw</span><span class="sxs-lookup"><span data-stu-id="7f3f0-127">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="7f3f0-128">예외는 호출하는 코드에서 반환 코드를 확인하지 않아 오류가 발견되지 않는 것을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-128">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span> 

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="7f3f0-129">미리 정의된 .NET 예외 형식 사용</span><span class="sxs-lookup"><span data-stu-id="7f3f0-129">Use the predefined .NET exception types</span></span>

<span data-ttu-id="7f3f0-130">새 예외 클래스는 미리 정의된 예외 클래스가 적용되지 않는 경우에만 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-130">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="7f3f0-131">예:</span><span class="sxs-lookup"><span data-stu-id="7f3f0-131">For example:</span></span>

- <span data-ttu-id="7f3f0-132">개체의 현재 상태에서 속성 집합이나 메서드 호출이 적절하지 않을 경우 <xref:System.InvalidOperationException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-132">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="7f3f0-133">잘못된 매개 변수가 전달되면 <xref:System.ArgumentException> 예외 또는 <xref:System.ArgumentException>에서 파생된 미리 정의된 클래스 중 하나를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-133">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="7f3f0-134">예외 클래스 이름 뒤에 단어 `Exception` 추가</span><span class="sxs-lookup"><span data-stu-id="7f3f0-134">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="7f3f0-135">사용자 지정 예외가 필요한 경우 적절한 이름을 지정하고 <xref:System.Exception> 클래스에서 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-135">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="7f3f0-136">예:</span><span class="sxs-lookup"><span data-stu-id="7f3f0-136">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="7f3f0-137">사용자 지정 예외 클래스에 세 가지 생성자 포함</span><span class="sxs-lookup"><span data-stu-id="7f3f0-137">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="7f3f0-138">사용자 고유의 예외 클래스를 만들 때 최소한 다음 세 가지 일반 생성자를 사용합니다. 즉, 기본 생성자, 문자열 메시지를 사용하는 생성자, 문자열 메시지와 내부 예외를 사용하는 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-138">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="7f3f0-139">기본값을 사용하는 <xref:System.Exception.%23ctor>.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-139"><xref:System.Exception.%23ctor>, which uses default values.</span></span>
  
* <span data-ttu-id="7f3f0-140">문자열 메시지를 수락하는 <xref:System.Exception.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-140"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>  
  
* <span data-ttu-id="7f3f0-141">문자열 메시지와 내부 예외를 허용하는 <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>  
  
<span data-ttu-id="7f3f0-142">예를 들어 [방법: 사용자 정의 예외 만들기](how-to-create-user-defined-exceptions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-142">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="7f3f0-143">코드를 원격으로 실행하는 경우 예외 데이터를 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="7f3f0-143">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="7f3f0-144">사용자 정의 예외를 만드는 경우 원격으로 실행하는 코드에서 예외에 대한 메타데이터를 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-144">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span> 

<span data-ttu-id="7f3f0-145">예를 들어 앱 도메인을 지원하는 .NET 구현에서 앱 도메인 간에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-145">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="7f3f0-146">앱 도메인 A에서 앱 도메인 B를 만들고, 여기서 예외를 throw하는 코드를 실행한다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-146">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="7f3f0-147">앱 도메인 A에서 예외를 정확하게 catch하고 처리하려면 앱 도메인 B에서 throw된 예외를 포함하는 어셈블리를 찾을 수 있어야 합니다. 앱 도메인 B에서 앱 도메인 A의 응용 프로그램 기준 위치가 아니라 해당 응용 프로그램 기준 위치 아래의 어셈블리에 포함된 예외를 throw할 경우 앱 도메인 A는 예외를 찾을 수 없으며 공용 언어 런타임에서 <xref:System.IO.FileNotFoundException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-147">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="7f3f0-148">이러한 상황을 방지하기 위해 예외 정보가 포함된 어셈블리를 다음과 같은 두 가지 방법으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-148">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="7f3f0-149">해당 어셈블리를 두 응용 프로그램 도메인이 공유하는 공통 응용 프로그램 기본 구조에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-149">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="7f3f0-150">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="7f3f0-150">\- or -</span></span>

- <span data-ttu-id="7f3f0-151">도메인이 공통 응용 프로그램 기반 구조를 공유하지 않을 경우, 예외 정보가 포함된 어셈블리를 강력한 이름으로 지정한 다음, 이 어셈블리를 전역 어셈블리 캐시에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-151">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="7f3f0-152">문법적으로 올바른 오류 메시지 사용</span><span class="sxs-lookup"><span data-stu-id="7f3f0-152">Use grammatically correct error messages</span></span>

<span data-ttu-id="7f3f0-153">명확한 문을 작성하고 종료 문장 부호를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-153">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="7f3f0-154"><xref:System.Exception.Message?displayProperty=nameWithType> 속성에 할당된 문자열의 각 문장은 마침표로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-154">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="7f3f0-155">예를 들어 “로그 테이블이 오버플로되었습니다.”는</span><span class="sxs-lookup"><span data-stu-id="7f3f0-155">For example, "The log table has overflowed."</span></span> <span data-ttu-id="7f3f0-156">적절한 메시지 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-156">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="7f3f0-157">모든 예외에 지역화된 문자열 메시지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-157">Include a localized string message in every exception</span></span>

<span data-ttu-id="7f3f0-158">사용자에게 표시되는 오류 메시지는 예외 클래스 이름에서 파생된 메시지가 아니라 throw된 예외의 <xref:System.Exception.Message?displayProperty=nameWithType> 속성에서 파생된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-158">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="7f3f0-159">일반적으로 [예외 생성자](xref:System.Exception.%23ctor%2A)의 `message` 인수에 메시지 문자열을 전달하여 값을 <xref:System.Exception.Message?displayProperty=nameWithType> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-159">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span> 

<span data-ttu-id="7f3f0-160">지역화된 응용 프로그램의 경우 응용 프로그램에서 throw할 수 있는 모든 예외에 대해 지역화된 메시지 문자열을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-160">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="7f3f0-161">리소스 파일을 사용하여 지역화된 오류 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-161">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="7f3f0-162">응용 프로그램을 지역화하고 지역화된 문자열을 검색하는 방법은 [데스크톱 앱의 리소스](../../framework/resources/index.md) 및 <xref:System.Resources.ResourceManager?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-162">For information on localizing applications and retrieving localized strings, see [Resources in Desktop Apps](../../framework/resources/index.md) and <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="7f3f0-163">필요에 따라 사용자 지정 예외에서 추가 속성 제공</span><span class="sxs-lookup"><span data-stu-id="7f3f0-163">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="7f3f0-164">추가 정보가 유용한 프로그래밍 시나리오에 대해서만 예외에 사용자 지정 메시지 문자열 이외의 추가 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-164">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="7f3f0-165">예를 들어, <xref:System.IO.FileNotFoundException>은 <xref:System.IO.FileNotFoundException.FileName> 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-165">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="7f3f0-166">스택 추적이 도움이 되도록 throw 문 포함</span><span class="sxs-lookup"><span data-stu-id="7f3f0-166">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="7f3f0-167">스택 추적은 예외가 throw되는 문에서 시작하여 예외를 catch하는 `catch` 문까지 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-167">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="7f3f0-168">예외 작성기 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="7f3f0-168">Use exception builder methods</span></span>

<span data-ttu-id="7f3f0-169">클래스는 구현된 여러 위치에서 동일한 예외를 throw하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-169">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="7f3f0-170">코드를 많이 사용하지 않으려면 예외를 만들어 반환하는 도우미 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-170">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="7f3f0-171">예:</span><span class="sxs-lookup"><span data-stu-id="7f3f0-171">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
<span data-ttu-id="7f3f0-172">예외의 생성자를 사용하여 예외를 작성하는 것이 더 적합한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-172">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="7f3f0-173">예를 들어 <xref:System.ArgumentException>과 같은 전역 예외 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-173">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a><span data-ttu-id="7f3f0-174">예외를 throw할 때 중간 결과 정리</span><span class="sxs-lookup"><span data-stu-id="7f3f0-174">Clean up intermediate results when throwing an exception</span></span>

<span data-ttu-id="7f3f0-175">호출자가 메서드에서 예외가 throw될 때 의도하지 않은 결과가 발생하지 않는다고 가정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-175">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="7f3f0-176">예를 들어 하나의 계좌에서 출금한 후 다른 계좌에 입금하여 돈을 이체하는 코드가 있고 입금을 실행하는 동안 예외가 발생할 경우 출금이 적용되기를 원하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-176">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

<span data-ttu-id="7f3f0-177">이 상황을 처리하는 한 가지 방법은 입금 트랜잭션에서 throw된 예외를 catch하고 출금을 롤백하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-177">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

<span data-ttu-id="7f3f0-178">이 예제에서는 `throw`를 사용하여 원래 예외를 다시 throw하는 방법을 보여 줍니다. 이렇게 하면 호출자가 <xref:System.Exception.InnerException> 속성을 검사하지 않아도 문제의 실제 원인을 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-178">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="7f3f0-179">또는 새 예외를 throw하고 원래 예외를 내부 예외로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f3f0-179">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a><span data-ttu-id="7f3f0-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f3f0-180">See Also</span></span>  
[<span data-ttu-id="7f3f0-181">예외</span><span class="sxs-lookup"><span data-stu-id="7f3f0-181">Exceptions</span></span>](index.md)

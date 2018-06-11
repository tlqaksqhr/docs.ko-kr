---
title: 대리자에 대한 일반적인 패턴
description: 코드에서 대리자를 사용하여 구성 요소 간의 강력한 결합을 방지하기 위한 일반적인 패턴에 대해 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 20d55a1aba345b962c506bbc3f82248a817923ea
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827022"
---
# <a name="common-patterns-for-delegates"></a><span data-ttu-id="33af0-103">대리자에 대한 일반적인 패턴</span><span class="sxs-lookup"><span data-stu-id="33af0-103">Common Patterns for Delegates</span></span>

[<span data-ttu-id="33af0-104">이전</span><span class="sxs-lookup"><span data-stu-id="33af0-104">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="33af0-105">대리자는 구성 요소 간 결합이 최소화된 소프트웨어 디자인을 사용하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-105">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="33af0-106">이러한 디자인의 가장 좋은 예는 LINQ입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-106">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="33af0-107">LINQ 쿼리 식 패턴은 모든 기능에 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-107">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="33af0-108">간단한 다음 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="33af0-108">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="33af0-109">이 예제에서는 숫자 시퀀스를 값 10보다 작은 숫자로만 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-109">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="33af0-110">`Where` 메서드는 필터를 통과하는 시퀀스의 요소를 결정하는 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-110">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="33af0-111">LINQ 쿼리를 만들 때 이러한 특정 용도를 위해 대리자의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-111">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="33af0-112">Where 메서드의 프로토타입은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-112">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<TSource> (this IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="33af0-113">이 예제에서는 LINQ의 일부인 모든 메서드가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-113">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="33af0-114">이러한 메서드는 모두 특정 쿼리를 관리하는 코드에 대해 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-114">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="33af0-115">이 API 디자인 패턴은 매우 간단하게 배우고 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-115">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="33af0-116">이 간단한 예제에서는 어떻게 대리자에 구성 요소 간 결합이 거의 필요하지 않은지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-116">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="33af0-117">특정 기본 클래스에서 파생되는 클래스를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-117">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="33af0-118">특정 인터페이스를 구현하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-118">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="33af0-119">현재 작업에 기본적으로 필요한 하나의 메서드만 구현하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-119">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="33af0-120">대리자를 사용하여 고유한 구성 요소 빌드</span><span class="sxs-lookup"><span data-stu-id="33af0-120">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="33af0-121">대리자를 사용하는 디자인으로 구성 요소를 만들어 해당 예제에서 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-121">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="33af0-122">큰 시스템의 로그 메시지에 사용할 수 있는 구성 요소를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-122">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="33af0-123">라이브러리 구성 요소는 여러 가지 다른 플랫폼의 다양한 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-123">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="33af0-124">로그를 관리하는 구성 요소에는 공통된 기능이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-124">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="33af0-125">시스템의 모든 구성 요소에서 전달된 메시지를 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-125">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="33af0-126">이러한 메시지는 핵심 구성 요소에서 관리할 수 있는 우선 순위가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-126">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="33af0-127">메시지는 최종 보관된 양식에 타임스탬프가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-127">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="33af0-128">고급 시나리오의 경우 소스 구성 요소에 따라 메시지를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-128">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="33af0-129">메시지가 기록되는 위치와 같이 자주 변경되는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-129">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="33af0-130">일부 환경에서는 메시지가 오류 콘솔에 기록되고,</span><span class="sxs-lookup"><span data-stu-id="33af0-130">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="33af0-131">다른 환경에서는 파일에 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-131">In others, a file.</span></span> <span data-ttu-id="33af0-132">데이터베이스 저장소, OS 이벤트 로그, 기타 문서 저장소 등에 기록될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-132">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="33af0-133">또한 다양한 시나리오에서 사용될 수 있는 출력의 조합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-133">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="33af0-134">메시지를 콘솔 및 파일에 기록하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-134">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="33af0-135">대리자 기반 디자인은 뛰어난 유연성을 제공하며 나중에 추가할 수 있는 저장소 메커니즘을 지원하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-135">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="33af0-136">이 디자인에서 기본 로그 구성 요소는 비가상이며 sealed 클래스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-136">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="33af0-137">모든 대리자 집합을 연결하여 다양한 저장소 미디어에 메시지를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-137">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="33af0-138">멀티캐스트 대리자에 대한 기본 제공 지원을 통해 메시지가 여러 위치(파일 및 콘솔)에 기록되어야 하는 시나리오를 쉽게 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-138">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="33af0-139">첫 번째 구현</span><span class="sxs-lookup"><span data-stu-id="33af0-139">A First Implementation</span></span>

<span data-ttu-id="33af0-140">작은 규모로 시작해 보겠습니다. 초기 구현에서는 새 메시지를 수락하고 연결된 대리자를 사용하여 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-140">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="33af0-141">메시지를 콘솔에 기록하는 대리자에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-141">You can start with one delegate that writes messages to the console.</span></span>

[!code-csharp[LoggerImplementation](../../samples/csharp/delegates-and-events/Logger.cs#FirstImplementation "A first Logger implementation.")]

<span data-ttu-id="33af0-142">위의 정적 클래스는 사용할 수 있는 가장 간단한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-142">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="33af0-143">메시지를 콘솔에 기록하는 메서드에 대한 단일 구현을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-143">We need to write the single implementation for the method that writes messages to the console:</span></span> 

[!code-csharp[LogToConsole](../../samples/csharp/delegates-and-events/Program.cs#LogToConsole "A Console logger.")]

<span data-ttu-id="33af0-144">마지막으로 로거에 선언된 WriteMessage 대리자에 대리자를 연결함으로써 대리자를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-144">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

[!code-csharp[ConnectDelegate](../../samples/csharp/delegates-and-events/Program.cs#ConnectDelegate "Connect to the delegate")]

## <a name="practices"></a><span data-ttu-id="33af0-145">사례</span><span class="sxs-lookup"><span data-stu-id="33af0-145">Practices</span></span>

<span data-ttu-id="33af0-146">지금까지 샘플은 매우 간단하지만 대리자 관련 디자인에 대한 몇 가지 중요한 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-146">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="33af0-147">Core Framework에 정의된 대리자 형식을 사용하면 사용자가 대리자를 사용하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-147">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="33af0-148">새 형식을 정의할 필요가 없으며, 라이브러리를 사용하는 개발자는 특수화된 새 대리자 형식을 배울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-148">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="33af0-149">사용되는 인터페이스는 최대한 최소화되고 유연합니다. 새 출력 로거를 만들려면 메서드 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-149">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="33af0-150">이 메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-150">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="33af0-151">모든 액세스 권한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-151">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="33af0-152">출력 서식 지정</span><span class="sxs-lookup"><span data-stu-id="33af0-152">Formatting Output</span></span>

<span data-ttu-id="33af0-153">이 첫 번째 버전을 약간 더 강력하게 만든 후 다른 로깅 메커니즘을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-153">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="33af0-154">다음으로 로그 클래스에서 보다 구조적인 메시지를 만들도록 `LogMessage()` 메서드에 몇 가지 인수를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-154">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

[!code-csharp[Severity](../../samples/csharp/delegates-and-events/Logger.cs#Severity "Define severities")]
[!code-csharp[NextLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerTwo "Refine the Logger")]

<span data-ttu-id="33af0-155">그런 다음 해당 `Severity` 인수를 사용하여 로그의 출력으로 전송되는 메시지를 필터링해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-155">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

[!code-csharp[FinalLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerFinal "Finish the Logger")]

## <a name="practices"></a><span data-ttu-id="33af0-156">사례</span><span class="sxs-lookup"><span data-stu-id="33af0-156">Practices</span></span>

<span data-ttu-id="33af0-157">로깅 인프라에 새 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-157">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="33af0-158">로거 구성 요소는 모든 출력 메커니즘에 매우 느슨하게 결합되므로 로거 대리자를 구현하는 코드에 영향을 주지 않고 이러한 새 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-158">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="33af0-159">계속 구축하면 이 느슨한 결합을 통해 다른 위치를 변경하지 않고 사이트의 일부를 업데이트할 때 유연성을 향상시킬 수 있는 방법에 대한 예제가 더 많이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-159">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="33af0-160">실제로 더 큰 응용 프로그램에서는 로거 출력 클래스가 다른 어셈블리에 있을 수 있으며 심지어 다시 작성할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-160">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="33af0-161">두 번째 출력 엔진 구축</span><span class="sxs-lookup"><span data-stu-id="33af0-161">Building a Second Output Engine</span></span>

<span data-ttu-id="33af0-162">로그 구성 요소가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-162">The Log component is coming along well.</span></span> <span data-ttu-id="33af0-163">메시지를 파일에 기록하는 출력 엔진을 하나 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-163">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="33af0-164">그러면 약간 더 복잡한 출력 엔진이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-164">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="33af0-165">이 엔진은 파일 작업을 캡슐화하는 클래스가 되고 기록할 때마다 파일이 항상 닫히도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-165">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="33af0-166">또한 각 메시지가 생성된 후 모든 데이터가 디스크로 플러시되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-166">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="33af0-167">다음 해당 파일 기반 로거입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-167">Here is that file based logger:</span></span>

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/FileLogger.cs#FileLogger "Log to files")]


<span data-ttu-id="33af0-168">이 클래스를 만들었으면 인스턴스화하고 해당 LogMessage 메서드를 로거 구성 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-168">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/Program.cs#FileLogger "Log to files")]

<span data-ttu-id="33af0-169">이러한 두 메서드는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-169">These two are not mutually exclusive.</span></span> <span data-ttu-id="33af0-170">두 로그 메서드를 연결하고 메시지를 콘솔 및 파일에 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-170">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="33af0-171">나중에 시스템에 문제를 발생시키지 않고 동일한 응용 프로그램에서도 대리자 중 하나를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-171">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="33af0-172">사례</span><span class="sxs-lookup"><span data-stu-id="33af0-172">Practices</span></span>

<span data-ttu-id="33af0-173">이제 로깅 하위 시스템에 대한 두 번째 출력 처리기를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-173">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="33af0-174">파일 시스템을 올바르게 지원하려면 조금 더 많은 인프라가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-174">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="33af0-175">대리자는 인스턴스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-175">The delegate is an instance method.</span></span> <span data-ttu-id="33af0-176">전용 메서드이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-176">It's also a private method.</span></span>
<span data-ttu-id="33af0-177">대리자 인프라는 대리자를 연결할 수 있기 때문에 더 큰 액세스 가능성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-177">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="33af0-178">두 번째로 대리자 기반 디자인에서는 코드를 추가하지 않고도 여러 출력 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-178">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="33af0-179">따라서 여러 출력 메서드를 지원하기 위해 추가 인프라를 구축하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-179">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="33af0-180">이러한 메서드는 호출 목록에서 또 다른 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-180">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="33af0-181">파일 로깅 출력 메서드의 코드에 특별히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-181">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="33af0-182">예외를 throw하지 않도록 이 코드를 코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-182">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="33af0-183">이는 항상 엄격한 요건은 아니지만 종종 좋은 사례가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-183">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="33af0-184">대리자 메서드 중 하나가 예외를 throw하는 경우 호출 목록에 있는 나머지 대리자가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-184">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="33af0-185">마지막으로 파일 로거는 각 로그 메시지에서 파일을 열고 닫아 해당 리소스를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-185">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="33af0-186">파일을 열어 두고 작업이 완료되면 IDisposable을 구현하여 파일을 닫도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-186">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="33af0-187">두 메서드에는 장점과 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-187">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="33af0-188">둘 다 클래스 간 결합을 약간 더 많이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-188">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="33af0-189">두 시나리오를 지원하기 위해 로거 클래스의 코드를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-189">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="33af0-190">Null 대리자 처리</span><span class="sxs-lookup"><span data-stu-id="33af0-190">Handling Null Delegates</span></span>

<span data-ttu-id="33af0-191">마지막으로 출력 메커니즘을 선택하지 않은 경우에 보다 강력하도록 LogMessage 메서드를 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-191">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="33af0-192">`WriteMessage` 대리자에 연결된 호출 목록이 없는 경우 현재 구현에서는 `NullReferenceException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-192">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="33af0-193">메서드가 연결되지 않은 경우에도 자동으로 계속되는 디자인을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-193">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="33af0-194">`Delegate.Invoke()` 메서드와 결합된 null 조건부 연산자를 사용하면 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-194">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="33af0-195">왼쪽 피연산자(이 경우 `WriteMessage`)가 null이면 null 조건부 연산자(`?.`)가 단락됩니다. 즉, 메시지를 기록하려고 시도하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-195">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="33af0-196">`System.Delegate` 또는 `System.MulticastDelegate`에 대한 설명서에 나열된 `Invoke()` 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-196">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="33af0-197">컴파일러는 선언된 모든 대리자 형식에 대해 형식이 안전한 `Invoke` 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-197">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="33af0-198">따라서 이 예제에서 `Invoke`는 단일 `string` 인수를 사용하고 void 반환 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-198">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="33af0-199">사례의 요약</span><span class="sxs-lookup"><span data-stu-id="33af0-199">Summary of Practices</span></span>

<span data-ttu-id="33af0-200">다른 기록기 및 다른 기능으로 확장할 수 있는 로그 구성 요소의 시작 부분을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-200">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="33af0-201">디자인에서 대리자를 사용하면 서로 다른 구성 요소가 매우 느슨하게 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-201">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="33af0-202">그러면 여러 가지 장점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-202">This provides several advantages.</span></span> <span data-ttu-id="33af0-203">새 출력 메커니즘을 만들어 시스템에 연결하기가 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-203">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="33af0-204">이러한 다른 메커니즘에는 로그 메시지를 기록하는 메서드 하나만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-204">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="33af0-205">이 디자인은 새 기능을 추가할 때 매우 복원력이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-205">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="33af0-206">모든 기록기에 필요한 계약은 하나의 메서드를 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-206">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="33af0-207">해당 메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-207">That method could be a static or instance method.</span></span> <span data-ttu-id="33af0-208">공용, 개인 또는 기타 법적 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-208">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="33af0-209">로거 클래스는 새로운 변경 사항 없이 원하는 대로 기능 향상 또는 변경을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-209">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="33af0-210">모든 클래스와 마찬가지로 새로운 변경 위험이 없으면 공용 API를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-210">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="33af0-211">그러나 로거와 모든 출력 엔진 간 결합은 대리자를 통해서만 가능하므로 다른 형식(예: 인터페이스 또는 기본 클래스)이 관련되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-211">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="33af0-212">결합은 최대한 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33af0-212">The coupling is as small as possible.</span></span>

[<span data-ttu-id="33af0-213">다음</span><span class="sxs-lookup"><span data-stu-id="33af0-213">Next</span></span>](events-overview.md)

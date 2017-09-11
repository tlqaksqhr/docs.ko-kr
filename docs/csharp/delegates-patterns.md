---
title: "대리자에 대한 일반적인 패턴"
description: "코드에서 대리자를 사용하여 구성 요소 간의 강력한 결합을 방지하기 위한 일반적인 패턴에 대해 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83214800fb997e9274cacfd1bae85ab07c4515a2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="common-patterns-for-delegates"></a><span data-ttu-id="03904-104">대리자에 대한 일반적인 패턴</span><span class="sxs-lookup"><span data-stu-id="03904-104">Common Patterns for Delegates</span></span>

[<span data-ttu-id="03904-105">이전</span><span class="sxs-lookup"><span data-stu-id="03904-105">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="03904-106">대리자는 구성 요소 간 결합이 최소화된 소프트웨어 디자인을 사용하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-106">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="03904-107">이러한 디자인의 가장 좋은 예는 LINQ입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-107">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="03904-108">LINQ 쿼리 식 패턴은 모든 기능에 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-108">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="03904-109">간단한 다음 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="03904-109">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="03904-110">이 예제에서는 숫자 시퀀스를 값 10보다 작은 숫자로만 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-110">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="03904-111">`Where` 메서드는 필터를 통과하는 시퀀스의 요소를 결정하는 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-111">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="03904-112">LINQ 쿼리를 만들 때 이러한 특정 용도를 위해 대리자의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-112">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="03904-113">Where 메서드의 프로토타입은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-113">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<in TSource> (IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="03904-114">이 예제에서는 LINQ의 일부인 모든 메서드가 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-114">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="03904-115">이러한 메서드는 모두 특정 쿼리를 관리하는 코드에 대해 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-115">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="03904-116">이 API 디자인 패턴은 매우 간단하게 배우고 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-116">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="03904-117">이 간단한 예제에서는 어떻게 대리자에 구성 요소 간 결합이 거의 필요하지 않은지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03904-117">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="03904-118">특정 기본 클래스에서 파생되는 클래스를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-118">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="03904-119">특정 인터페이스를 구현하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-119">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="03904-120">현재 작업에 기본적으로 필요한 하나의 메서드만 구현하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-120">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="03904-121">대리자를 사용하여 고유한 구성 요소 빌드</span><span class="sxs-lookup"><span data-stu-id="03904-121">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="03904-122">대리자를 사용하는 디자인으로 구성 요소를 만들어 해당 예제에서 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-122">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="03904-123">큰 시스템의 로그 메시지에 사용할 수 있는 구성 요소를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-123">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="03904-124">라이브러리 구성 요소는 여러 가지 다른 플랫폼의 다양한 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-124">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="03904-125">로그를 관리하는 구성 요소에는 공통된 기능이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-125">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="03904-126">시스템의 모든 구성 요소에서 전달된 메시지를 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-126">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="03904-127">이러한 메시지는 핵심 구성 요소에서 관리할 수 있는 우선 순위가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="03904-127">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="03904-128">메시지는 최종 보관된 양식에 타임스탬프가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-128">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="03904-129">고급 시나리오의 경우 소스 구성 요소에 따라 메시지를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-129">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="03904-130">메시지가 기록되는 위치와 같이 자주 변경되는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-130">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="03904-131">일부 환경에서는 메시지가 오류 콘솔에 기록되고,</span><span class="sxs-lookup"><span data-stu-id="03904-131">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="03904-132">다른 환경에서는 파일에 기록될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-132">In others, a file.</span></span> <span data-ttu-id="03904-133">데이터베이스 저장소, OS 이벤트 로그, 기타 문서 저장소 등에 기록될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-133">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="03904-134">또한 다양한 시나리오에서 사용될 수 있는 출력의 조합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-134">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="03904-135">메시지를 콘솔 및 파일에 기록하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-135">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="03904-136">대리자 기반 디자인은 뛰어난 유연성을 제공하며 나중에 추가할 수 있는 저장소 메커니즘을 지원하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-136">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="03904-137">이 디자인에서 기본 로그 구성 요소는 비가상이며 sealed 클래스일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-137">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="03904-138">모든 대리자 집합을 연결하여 다양한 저장소 미디어에 메시지를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-138">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="03904-139">멀티캐스트 대리자에 대한 기본 제공 지원을 통해 메시지가 여러 위치(파일 및 콘솔)에 기록되어야 하는 시나리오를 쉽게 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-139">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="03904-140">첫 번째 구현</span><span class="sxs-lookup"><span data-stu-id="03904-140">A First Implementation</span></span>

<span data-ttu-id="03904-141">작은 규모로 시작해 보겠습니다. 초기 구현에서는 새 메시지를 수락하고 연결된 대리자를 사용하여 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-141">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="03904-142">메시지를 콘솔에 기록하는 대리자에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-142">You can start with one delegate that writes messages to the console.</span></span>

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(string msg)
    {
        WriteMessage(msg);
    }
}
```

<span data-ttu-id="03904-143">위의 정적 클래스는 사용할 수 있는 가장 간단한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-143">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="03904-144">메시지를 콘솔에 기록하는 메서드에 대한 단일 구현을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-144">We need to write the single implementation for the method that writes messages to the console:</span></span> 

```csharp
public static void LogToConsole(string message)
{
    Console.Error.WriteLine(message);
}
```

<span data-ttu-id="03904-145">마지막으로 로거에 선언된 WriteMessage 대리자에 대리자를 연결함으로써 대리자를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-145">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

```csharp
Logger.WriteMessage += LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="03904-146">사례</span><span class="sxs-lookup"><span data-stu-id="03904-146">Practices</span></span>

<span data-ttu-id="03904-147">지금까지 샘플은 매우 간단하지만 대리자 관련 디자인에 대한 몇 가지 중요한 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03904-147">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="03904-148">Core Framework에 정의된 대리자 형식을 사용하면 사용자가 대리자를 사용하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-148">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="03904-149">새 형식을 정의할 필요가 없으며, 라이브러리를 사용하는 개발자는 특수화된 새 대리자 형식을 배울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-149">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="03904-150">사용되는 인터페이스는 최대한 최소화되고 유연합니다. 새 출력 로거를 만들려면 메서드 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-150">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="03904-151">이 메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-151">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="03904-152">모든 액세스 권한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-152">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="03904-153">출력 서식 지정</span><span class="sxs-lookup"><span data-stu-id="03904-153">Formatting Output</span></span>

<span data-ttu-id="03904-154">이 첫 번째 버전을 약간 더 강력하게 만든 후 다른 로깅 메커니즘을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-154">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="03904-155">다음으로 로그 클래스에서 보다 구조적인 메시지를 만들도록 `LogMessage()` 메서드에 몇 가지 인수를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-155">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

```csharp
// Logger implementation two
public enum Severity
{
    Verbose,
    Trace,
    Information,
    Warning,
    Error,
    Critical
}

public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```

<span data-ttu-id="03904-156">그런 다음 해당 `Severity` 인수를 사용하여 로그의 출력으로 전송되는 메시지를 필터링해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-156">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static Severity LogLevel {get;set;} = Severity.Warning;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        if (s < LogLevel)
            return;
            
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```
## <a name="practices"></a><span data-ttu-id="03904-157">사례</span><span class="sxs-lookup"><span data-stu-id="03904-157">Practices</span></span>

<span data-ttu-id="03904-158">로깅 인프라에 새 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-158">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="03904-159">로거 구성 요소는 모든 출력 메커니즘에 매우 느슨하게 결합되므로 로거 대리자를 구현하는 코드에 영향을 주지 않고 이러한 새 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-159">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="03904-160">계속 구축하면 이 느슨한 결합을 통해 다른 위치를 변경하지 않고 사이트의 일부를 업데이트할 때 유연성을 향상시킬 수 있는 방법에 대한 예제가 더 많이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-160">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="03904-161">실제로 더 큰 응용 프로그램에서는 로거 출력 클래스가 다른 어셈블리에 있을 수 있으며 심지어 다시 작성할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-161">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="03904-162">두 번째 출력 엔진 구축</span><span class="sxs-lookup"><span data-stu-id="03904-162">Building a Second Output Engine</span></span>

<span data-ttu-id="03904-163">로그 구성 요소가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-163">The Log component is coming along well.</span></span> <span data-ttu-id="03904-164">메시지를 파일에 기록하는 출력 엔진을 하나 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-164">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="03904-165">그러면 약간 더 복잡한 출력 엔진이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-165">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="03904-166">이 엔진은 파일 작업을 캡슐화하는 클래스가 되고 기록할 때마다 파일이 항상 닫히도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-166">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="03904-167">또한 각 메시지가 생성된 후 모든 데이터가 디스크로 플러시되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-167">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="03904-168">다음 해당 파일 기반 로거입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-168">Here is that file based logger:</span></span>

```csharp
public class FileLogger
{
    private readonly string logPath;
    public FileLogger(string path)
    {
        logPath = path;
        Logger.WriteMessage += LogMessage;
    }
    
    public void DetachLog() => Logger.WriteMessage -= LogMessage;

    // make sure this can't throw.
    private void LogMessage(string msg)
    {
        try {
            using (var log = File.AppendText(logPath))
            {
                log.WriteLine(msg);
                log.Flush();
            }
        } catch (Exception e)
        {
            // Hmm. Not sure what to do.
            // Logging is failing...
        }
    }
}
```

<span data-ttu-id="03904-169">이 클래스를 만들었으면 인스턴스화하고 해당 LogMessage 메서드를 로거 구성 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-169">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

```csharp
var file = new FileLogger("log.txt");
```

<span data-ttu-id="03904-170">이러한 두 메서드는 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-170">These two are not mutually exclusive.</span></span> <span data-ttu-id="03904-171">두 로그 메서드를 연결하고 메시지를 콘솔 및 파일에 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-171">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="03904-172">나중에 시스템에 문제를 발생시키지 않고 동일한 응용 프로그램에서도 대리자 중 하나를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-172">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="03904-173">사례</span><span class="sxs-lookup"><span data-stu-id="03904-173">Practices</span></span>

<span data-ttu-id="03904-174">이제 로깅 하위 시스템에 대한 두 번째 출력 처리기를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-174">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="03904-175">파일 시스템을 올바르게 지원하려면 조금 더 많은 인프라가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-175">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="03904-176">대리자는 인스턴스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-176">The delegate is an instance method.</span></span> <span data-ttu-id="03904-177">전용 메서드이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-177">It's also a private method.</span></span>
<span data-ttu-id="03904-178">대리자 인프라는 대리자를 연결할 수 있기 때문에 더 큰 액세스 가능성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-178">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="03904-179">두 번째로 대리자 기반 디자인에서는 코드를 추가하지 않고도 여러 출력 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-179">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="03904-180">따라서 여러 출력 메서드를 지원하기 위해 추가 인프라를 구축하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-180">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="03904-181">이러한 메서드는 호출 목록에서 또 다른 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-181">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="03904-182">파일 로깅 출력 메서드의 코드에 특별히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-182">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="03904-183">예외를 throw하지 않도록 이 코드를 코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-183">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="03904-184">이는 항상 엄격한 요건은 아니지만 종종 좋은 사례가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-184">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="03904-185">대리자 메서드 중 하나가 예외를 throw하는 경우 호출 목록에 있는 나머지 대리자가 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-185">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="03904-186">마지막으로 파일 로거는 각 로그 메시지에서 파일을 열고 닫아 해당 리소스를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-186">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="03904-187">파일을 열어 두고 작업이 완료되면 IDisposable을 구현하여 파일을 닫도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-187">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="03904-188">두 메서드에는 장점과 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-188">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="03904-189">둘 다 클래스 간 결합을 약간 더 많이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03904-189">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="03904-190">두 시나리오를 지원하기 위해 로거 클래스의 코드를 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-190">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="03904-191">Null 대리자 처리</span><span class="sxs-lookup"><span data-stu-id="03904-191">Handling Null Delegates</span></span>

<span data-ttu-id="03904-192">마지막으로 출력 메커니즘을 선택하지 않은 경우에 보다 강력하도록 LogMessage 메서드를 업데이트해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-192">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="03904-193">`WriteMessage` 대리자에 연결된 호출 목록이 없는 경우 현재 구현에서는 `NullReferenceException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-193">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="03904-194">메서드가 연결되지 않은 경우에도 자동으로 계속되는 디자인을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-194">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="03904-195">`Delegate.Invoke()` 메서드와 결합된 null 조건부 연산자를 사용하면 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-195">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="03904-196">왼쪽 피연산자(이 경우 `WriteMessage`)가 null이면 null 조건부 연산자(`?.`)가 단락됩니다. 즉, 메시지를 기록하려고 시도하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-196">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="03904-197">`System.Delegate` 또는 `System.MulticastDelegate`에 대한 설명서에 나열된 `Invoke()` 메서드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-197">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="03904-198">컴파일러는 선언된 모든 대리자 형식에 대해 형식이 안전한 `Invoke` 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-198">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="03904-199">따라서 이 예제에서 `Invoke`는 단일 `string` 인수를 사용하고 void 반환 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-199">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="03904-200">사례의 요약</span><span class="sxs-lookup"><span data-stu-id="03904-200">Summary of Practices</span></span>

<span data-ttu-id="03904-201">다른 기록기 및 다른 기능으로 확장할 수 있는 로그 구성 요소의 시작 부분을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-201">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="03904-202">디자인에서 대리자를 사용하면 서로 다른 구성 요소가 매우 느슨하게 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-202">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="03904-203">그러면 여러 가지 장점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-203">This provides several advantages.</span></span> <span data-ttu-id="03904-204">새 출력 메커니즘을 만들어 시스템에 연결하기가 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-204">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="03904-205">이러한 다른 메커니즘에는 로그 메시지를 기록하는 메서드 하나만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03904-205">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="03904-206">이 디자인은 새 기능을 추가할 때 매우 복원력이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-206">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="03904-207">모든 기록기에 필요한 계약은 하나의 메서드를 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03904-207">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="03904-208">해당 메서드는 정적 메서드이거나 인스턴스 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-208">That method could be a static or instance method.</span></span> <span data-ttu-id="03904-209">공용, 개인 또는 기타 법적 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-209">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="03904-210">로거 클래스는 새로운 변경 사항 없이 원하는 대로 기능 향상 또는 변경을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-210">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="03904-211">모든 클래스와 마찬가지로 새로운 변경 위험이 없으면 공용 API를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-211">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="03904-212">그러나 로거와 모든 출력 엔진 간 결합은 대리자를 통해서만 가능하므로 다른 형식(예: 인터페이스 또는 기본 클래스)이 관련되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03904-212">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="03904-213">결합은 최대한 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03904-213">The coupling is as small as possible.</span></span>

[<span data-ttu-id="03904-214">다음</span><span class="sxs-lookup"><span data-stu-id="03904-214">Next</span></span>](events-overview.md)


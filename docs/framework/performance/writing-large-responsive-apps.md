---
title: 대형 응답성 .NET Framework 응용 프로그램 작성
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 846d41c31687df98b019f103e42cf586a23d8ff1
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457570"
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="14218-102">대형 응답성 .NET Framework 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="14218-102">Writing Large, Responsive .NET Framework Apps</span></span>
<span data-ttu-id="14218-103">이 문서에서는 규모가 큰 .NET Framework 앱이나 파일 또는 데이터베이스와 같이 많은 양의 데이터를 처리하는 앱의 성능을 향상시키기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-103">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="14218-104">이러한 팁은 C# 및 Visual Basic 컴파일러를 관리 코드로 다시 작성하면서 수집되었으며, C# 컴파일러의 실제 몇 가지 예를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-104">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span>  
  
 <span data-ttu-id="14218-105">.NET Framework는 앱을 빌드하는 생산성이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="14218-105">The .NET Framework is highly productive for building apps.</span></span>  <span data-ttu-id="14218-106">강력하고 안전한 언어와 풍부한 라이브러리 컬렉션이 앱 빌드의 생산성을 높여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-106">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span>  <span data-ttu-id="14218-107">그러나 우수한 생산성에는 책임이 따르기 마련입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-107">However, with great productivity comes responsibility.</span></span>  <span data-ttu-id="14218-108">.NET Framework의 모든 기능을 사용하되, 필요한 경우 코드의 성능을 조정할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-108">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span>  
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="14218-109">새 컴파일러 성능을 앱에 적용하는 이유</span><span class="sxs-lookup"><span data-stu-id="14218-109">Why the new compiler performance applies to your app</span></span>  
 <span data-ttu-id="14218-110">.NET 컴파일러 플랫폼("Roslyn") 팀은 Visual Studio에서 코드를 모델링 및 분석하고, 도구를 빌드하며, 보다 풍부한 코드 인식 환경을 가능하게 해주는 새로운 API를 제공하기 위해 C# 및 Visual Basic 컴파일러를 관리 코드로 다시 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-110">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span>  <span data-ttu-id="14218-111">컴파일러를 다시 작성하고 새 컴파일러에서 Visual Studio 환경을 빌드한 결과, 규모가 큰 모든 .NET Framework 앱 또는 많은 데이터를 처리하는 모든 앱에 적용 가능한 유용한 성능 분석 정보가 드러났습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-111">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span>  <span data-ttu-id="14218-112">C# 컴파일러의 분석 정보 및 예를 활용하기 위해 컴파일러에 대해 알 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-112">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span>  
  
 <span data-ttu-id="14218-113">Visual Studio에서는 컴파일러 API를 사용하여 식별자 및 키워드 색 지정, 구문 완성 목록, 오류를 나타내는 물결선, 매개 변수 팁, 코드 문제, 코드 동작 등 사용자가 선호하는 모든 IntelliSense 기능을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-113">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span>  <span data-ttu-id="14218-114">Visual Studio는 개발자가 코드를 입력하고 변경하는 동안 이 도움말을 제공하며, Visual Studio는 컴파일러가 개발자가 편집한 코드를 지속적으로 모델링하는 동안 응답성을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-114">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span>  
  
 <span data-ttu-id="14218-115">최종 사용자는 앱과 상호 작용할 때 앱이 응답성을 유지할 것을 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-115">When your end users interact with your app, they expect it to be responsive.</span></span>  <span data-ttu-id="14218-116">입력이나 명령 처리가 차단되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-116">Typing or command handling should never be blocked.</span></span>  <span data-ttu-id="14218-117">사용자가 입력을 계속하면 도움말은 신속하게 나타나거나 표시되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-117">Help should pop up quickly or give up if the user continues typing.</span></span>  <span data-ttu-id="14218-118">앱은 앱이 느리다고 느끼게 하는 오랜 계산으로 UI 스레드를 차단하는 것을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-118">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span>  
  
 <span data-ttu-id="14218-119">Roslyn 컴파일러에 대 한 자세한 내용은 참조는 [dotnet/roslyn](https://github.com/dotnet/roslyn) GitHub의 리포지토리 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-119">For more information about Roslyn compilers, visit the [dotnet/roslyn](https://github.com/dotnet/roslyn) repo on GitHub.</span></span>
 <!-- TODO: replace with link to Roslyn conceptual docs once that's published -->
  
## <a name="just-the-facts"></a><span data-ttu-id="14218-120">팩트</span><span class="sxs-lookup"><span data-stu-id="14218-120">Just the Facts</span></span>  
 <span data-ttu-id="14218-121">성능을 조정하고 응답성 있는 .NET Framework 앱을 만들 때는 다음 팩트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="14218-121">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span>  
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="14218-122">팩트 1: 너무 이르게 최적화하지 말 것</span><span class="sxs-lookup"><span data-stu-id="14218-122">Fact 1: Don’t prematurely optimize</span></span>  
 <span data-ttu-id="14218-123">필요 이상으로 복잡한 코드를 작성하면 유지 관리, 디버깅 및 개선 비용이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-123">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span>  <span data-ttu-id="14218-124">숙련된 프로그래머는 코딩 문제를 해결하는 방법에 대한 직관적인 감각을 지니고 있으며 보다 효율적인 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-124">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span>  <span data-ttu-id="14218-125">그러나 때로는 코드를 너무 이르게 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-125">However, they sometimes prematurely optimize their code.</span></span>  <span data-ttu-id="14218-126">예를 들어, 단순 배열이면 충분한 경우에 해시 테이블을 사용하거나 단순히 값을 다시 계산하는 대신 메모리를 누수시킬 수 있는 복잡한 캐싱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-126">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span>  <span data-ttu-id="14218-127">숙련된 프로그래머라 하더라도 성능에 대해 테스트하고 문제를 발견할 경우 코드를 분석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-127">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span>  
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="14218-128">팩트 2: 측정하는 것이 아니라면 추측하는 것일 뿐임</span><span class="sxs-lookup"><span data-stu-id="14218-128">Fact 2: If you’re not measuring, you’re guessing</span></span>  
 <span data-ttu-id="14218-129">프로필과 측정값은 거짓말하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-129">Profiles and measurements don’t lie.</span></span>  <span data-ttu-id="14218-130">프로필은 CPU가 완전히 로드되었는지 여부나 사용자가 디스크 I/O에서 차단되었는지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-130">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span>  <span data-ttu-id="14218-131">프로필을 보면 할당하는 메모리의 종류와 양을 알 수 있을 뿐만 아니라 CPU가 GC([가비지 수집](../../../docs/standard/garbage-collection/index.md))에 많은 시간을 소비하고 있는지 여부도 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-131">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../../docs/standard/garbage-collection/index.md) (GC).</span></span>  
  
 <span data-ttu-id="14218-132">앱의 핵심 사용자 환경 또는 시나리오에 대한 성능 목표를 설정하고 성능을 측정하기 위한 테스트를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-132">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span>  <span data-ttu-id="14218-133">과학적인 방법을 적용하여 실패 테스트를 조사합니다. 즉, 프로필을 사용하여 사용자를 안내하고, 문제가 무엇일지 가설을 세우고, 실험이나 코드 변경으로 가설을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-133">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span>  <span data-ttu-id="14218-134">정기 테스트로 시간의 흐름에 따른 기준 성능 측정값을 설정하여 성능 저하를 일으키는 변경 내용을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-134">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span>  <span data-ttu-id="14218-135">엄격한 방식으로 성능 작업에 접근하면 불필요한 코드 업데이트로 시간을 낭비하는 일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-135">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span>  
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="14218-136">팩트 3: 좋은 도구가 모든 차별화를 이뤄냄</span><span class="sxs-lookup"><span data-stu-id="14218-136">Fact 3: Good tools make all the difference</span></span>  
 <span data-ttu-id="14218-137">좋은 도구를 사용하면 가장 큰 성능 문제(CPU, 메모리 또는 디스크)에 신속하게 파고들어 해당 병목 현상을 일으키는 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-137">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span>  <span data-ttu-id="14218-138">Microsoft는 [Visual Studio 프로파일러](/visualstudio/profiling/beginners-guide-to-performance-profiling), [Windows Phone 분석 도구](http://msdn.microsoft.com/library/e67e3199-ea43-4d14-ab7e-f7f19266253f) 및 [PerfView](http://www.microsoft.com/download/details.aspx?id=28567)와 같은 다양한 성능 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-138">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling), [Windows Phone Analysis Tool](http://msdn.microsoft.com/library/e67e3199-ea43-4d14-ab7e-f7f19266253f), and [PerfView](http://www.microsoft.com/download/details.aspx?id=28567).</span></span>  
  
 <span data-ttu-id="14218-139">PerfView는 디스크 I/O, GC 이벤트 및 메모리와 같은 깊이 있는 문제에 집중하는 데 도움을 주는 놀랄 만큼 강력한 도구로서 무료입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-139">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span>  <span data-ttu-id="14218-140">성능 관련 ETW([Windows용 이벤트 추적](../../../docs/framework/wcf/samples/etw-tracing.md)) 이벤트를 캡처하여 앱, 프로세스, 스택 및 스레드 단위 정보를 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-140">You can capture performance-related [Event Tracing for Windows](../../../docs/framework/wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span>  <span data-ttu-id="14218-141">PerfView는 앱에서 할당하는 메모리의 양과 종류뿐만 아니라 함수 또는 호출 스택으로 인해 메모리가 할당되는 양이 어느 정도인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-141">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="14218-142">자세한 내용은 도구에 포함된 다양한 도움말 항목, 데모 및 비디오(예: Channel 9의 [PerfView 자습서](http://channel9.msdn.com/Series/PerfView-Tutorial))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14218-142">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](http://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span>  
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="14218-143">팩트 4: 결국은 모두 할당에 관련된 문제임</span><span class="sxs-lookup"><span data-stu-id="14218-143">Fact 4: It’s all about allocations</span></span>  
 <span data-ttu-id="14218-144">응답성 있는 .NET Framework 앱을 빌드하는 것은 거품 정렬 대신 빠른 정렬을 사용하는 등 알고리즘에 대한 문제라고 생각할 수 있지만 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-144">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span>  <span data-ttu-id="14218-145">응답성 있는 앱을 빌드하는 데 있어서 가장 큰 요인은 메모리를 할당하는 것이며, 특히 앱의 규모가 매우 크거나 앱이 많은 양의 데이터를 처리하는 경우에 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-145">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span>  
  
 <span data-ttu-id="14218-146">새 컴파일러 API를 사용하여 응답성 있는 IDE 환경을 빌드하는 작업의 거의 전부는 할당을 피하고 캐싱 전략을 관리하는 것에 관련되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-146">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span>  <span data-ttu-id="14218-147">PerfView 추적은 새 C# 및 Visual Basic 컴파일러의 성능이 거의 CPU 바인딩이 아니라는 사실을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-147">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span>  <span data-ttu-id="14218-148">이러한 새 컴파일러는 수십만 또는 수백만 개의 코드 줄을 읽고 메타데이터를 읽거나 생성된 코드를 내보낼 때 I/O 바인딩일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-148">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span>  <span data-ttu-id="14218-149">UI 스레드 지연은 거의 전부 가비지 수집 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-149">The UI thread delays are nearly all due to garbage collection.</span></span>  <span data-ttu-id="14218-150">.NET Framework GC는 성능을 위해 많이 조정되었고 앱 코드가 실행되는 동안 해당 작업의 많은 부분을 동시에 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-150">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span>  <span data-ttu-id="14218-151">그러나 한 번의 할당으로 많은 비용이 드는 [gen2](../../../docs/standard/garbage-collection/fundamentals.md) 컬렉션이 트리거되어 모든 스레드가 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-151">However, a single allocation can trigger an expensive [gen2](../../../docs/standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span>  
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="14218-152">일반 할당 및 예제</span><span class="sxs-lookup"><span data-stu-id="14218-152">Common allocations and examples</span></span>  
 <span data-ttu-id="14218-153">이 섹션의 예제 식에는 작게 보이는 할당이 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-153">The example expressions in this section have hidden allocations that appear small.</span></span>  <span data-ttu-id="14218-154">그러나 규모가 큰 앱이 식을 충분한 횟수로 실행하면 수백 MB 심지어 GB의 할당이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-154">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span>  <span data-ttu-id="14218-155">예를 들어, 편집기에서 개발자의 입력을 시뮬레이션한 1분간의 테스트 결과 GB 메모리가 할당되어 성능 팀이 입력 시나리오에 집중하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-155">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span>  
  
### <a name="boxing"></a><span data-ttu-id="14218-156">boxing</span><span class="sxs-lookup"><span data-stu-id="14218-156">Boxing</span></span>  
 <span data-ttu-id="14218-157">[Boxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md)은 일반적으로 스택 또는 데이터 구조에 있는 값 형식이 개체에 래핑되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-157">[Boxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span>  <span data-ttu-id="14218-158">즉, 데이터를 유지하기 위한 개체를 할당한 다음 개체에 대한 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-158">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span>  <span data-ttu-id="14218-159">.NET Framework는 경우에 따라 메서드 시그니처 또는 저장소 위치 형식 때문에 값을 boxing합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-159">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span>  <span data-ttu-id="14218-160">값 형식을 개체에 래핑하면 메모리 할당이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-160">Wrapping a value type in an object causes memory allocation.</span></span>  <span data-ttu-id="14218-161">boxing 작업이 많으면 앱에 대한 MB 또는 GB의 메모리 할당이 발생할 수 있습니다. 즉, 앱으로 인해 많은 GC가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-161">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="14218-162">.NET Framework 및 언어 컴파일러는 가능한 한 boxing을 피하지만, 경우에 따라 전혀 예기치 않게 boxing이 발생하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-162">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span>  
  
 <span data-ttu-id="14218-163">PerfView에서 boxing을 보려면 추적을 열고 앱의 프로세스 이름 아래에서 GC Heap Alloc Stacks를 검토합니다(PerfView는 모든 프로세스에 대해 보고한다는 사실에 주의).</span><span class="sxs-lookup"><span data-stu-id="14218-163">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span>  <span data-ttu-id="14218-164">할당 아래에 <xref:System.Int32?displayProperty=nameWithType> 및 <xref:System.Char?displayProperty=nameWithType>과 같은 형식이 보이면 값 형식을 boxing하고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-164">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span>  <span data-ttu-id="14218-165">이러한 형식 중 하나를 선택하면 해당 형식이 boxing된 스택 및 함수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-165">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span>  
  
 <span data-ttu-id="14218-166">**예제 1: 문자열 메서드 및 값 형식 인수**</span><span class="sxs-lookup"><span data-stu-id="14218-166">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="14218-167">이 샘플 코드는 잠재적으로 불필요하고 과도한 boxing을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-167">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="14218-168">이 코드는 로깅 기능을 제공하므로 앱이 `Log` 함수를 자주 호출할 수 있으며 심지어 수백만 번 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-168">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span>  <span data-ttu-id="14218-169">문제는 `string.Format`에 대한 호출이 <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> 오버로드 확인으로 이어진다는 사실입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-169">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span>  
  
 <span data-ttu-id="14218-170">이 오버로드가 수행되려면 .NET Framework가 `int` 값을 개체에 boxing하여 이 메서드 호출에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-170">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span>  <span data-ttu-id="14218-171">부분적인 해결 방법은 `id.ToString()` 및 `size.ToString()`을 호출하고 모든 문자열(개체임)을 `string.Format` 호출에 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-171">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span>  <span data-ttu-id="14218-172">`ToString()`을 호출하면 문자열이 할당되지만 해당 할당은 어쨌든 `string.Format` 내부에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-172">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span>  
  
 <span data-ttu-id="14218-173">`string.Format`에 대한 이 기본 호출을 단순한 문자열 연결이라고 간주할 수 있으므로 대신 이 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-173">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="14218-174">그러나 코드의 해당 줄은 <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>로 컴파일되므로 boxing 할당이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-174">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span>  <span data-ttu-id="14218-175">.NET Framework는 문자 리터럴을 boxing하여 `Concat`을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-175">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="14218-176">**예제 1에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-176">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="14218-177">전체 해결 방법은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-177">The complete fix is simple.</span></span>  <span data-ttu-id="14218-178">문자 리터럴을 문자열 리터럴로 바꾸기만 하면 됩니다. 그러면 문자열이 이미 개체이기 때문에 boxing이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-178">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="14218-179">**예제 2: 열거형 boxing**</span><span class="sxs-lookup"><span data-stu-id="14218-179">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="14218-180">이 예제에서는 열거형 형식을 자주 사용해서(특히, 사전 조회 작업에서) 새 C# 및 Visual Basic 컴파일러에서 엄청난 양의 할당이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-180">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span>  
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="14218-181">이 문제는 매우 미묘합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-181">This problem is very subtle.</span></span>  <span data-ttu-id="14218-182">PerfView는 이를 <xref:System.Enum.GetHashCode> boxing으로 보고하는데, 메서드가 구현상의 이유로 열거형 형식의 기본 표현을 boxing하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-182">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span>  <span data-ttu-id="14218-183">PerfView에서 자세히 보면 <xref:System.Enum.GetHashCode>에 대한 호출마다 두 개의 boxing 할당을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-183">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span>   <span data-ttu-id="14218-184">컴파일러가 boxing 하나를 삽입하고 .NET Framework가 나머지 boxing을 삽입하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-184">The compiler inserts one, and the .NET Framework inserts the other.</span></span>  
  
 <span data-ttu-id="14218-185">**예제 2에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-185">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="14218-186"><xref:System.Enum.GetHashCode>를 호출하기 전에 기본 표현으로 캐스팅하여 두 할당을 모두 쉽게 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-186">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="14218-187">열거형 형식에 대한 boxing의 또 다른 일반적인 소스는 <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-187">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="14218-188"><xref:System.Enum.HasFlag%28System.Enum%29>으로 전달된 인수는 boxing되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-188">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span>  <span data-ttu-id="14218-189">대부분의 경우 <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>에 대한 호출을 비트 테스트로 바꾸면 보다 간단하고 할당도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-189">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span>  
  
 <span data-ttu-id="14218-190">첫 번째 성능 팩트를 염두에 두고(즉, 너무 이르게 최적화하지 말 것) 서둘러 이 방식으로 모든 코드를 다시 작성하려고는 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="14218-190">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span>    <span data-ttu-id="14218-191">이러한 boxing 비용에 주의하되 앱을 프로파일링하고 핫 스폿을 찾은 다음에만 코드를 변경하세요.</span><span class="sxs-lookup"><span data-stu-id="14218-191">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span>  
  
### <a name="strings"></a><span data-ttu-id="14218-192">문자열</span><span class="sxs-lookup"><span data-stu-id="14218-192">Strings</span></span>  
 <span data-ttu-id="14218-193">문자열 조작은 할당이 발생하는 가장 큰 원인 중 몇 가지를 차지하며, PerfView에서 흔히 상위 5가지 할당을 차지하곤 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-193">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span>  <span data-ttu-id="14218-194">프로그램에서는 serialization, JSON 및 REST API에 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-194">Programs use strings for serialization, JSON, and REST APIs.</span></span>  <span data-ttu-id="14218-195">열거형 형식을 사용할 수 없을 때 시스템과 상호 작용하기 위한 프로그램 상수로 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-195">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span>  <span data-ttu-id="14218-196">프로파일링에 문자열이 성능에 많은 영향을 미치고 있다고 표시되는 경우 <xref:System.String>, <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A> 등과 같은 <xref:System.String.Substring%2A> 메서드에 대한 호출을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-196">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span>  <span data-ttu-id="14218-197"><xref:System.Text.StringBuilder>를 사용하여 많은 조각에서 하나의 문자열을 만드는 비용을 방지하는 것도 유용하지만 <xref:System.Text.StringBuilder> 개체를 할당하는 것조차 관리해야 하는 병목 현상이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-197">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span>  
  
 <span data-ttu-id="14218-198">**예제 3: 문자열 작업**</span><span class="sxs-lookup"><span data-stu-id="14218-198">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="14218-199">C# 컴파일러에는 서식이 지정된 XML 문서 주석의 텍스트를 쓰는 이 코드가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-199">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="14218-200">이 코드가 많은 문자열 조작을 수행하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-200">You can see that this code does a lot of string manipulation.</span></span>  <span data-ttu-id="14218-201">이 코드에서는 라이브러리 메서드를 사용하여 줄을 별도의 문자열로 분할하고, 공백을 잘라내며, `text` 인수가 XML 문서 주석인지 확인하고, 줄에서 부분 문자열을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-201">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span>  
  
 <span data-ttu-id="14218-202">`WriteFormattedDocComment` 내의 첫 번째 줄에서 `text.Split` 호출은 호출될 때마다 요소가 3개인 새 배열을 인수로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-202">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span>  <span data-ttu-id="14218-203">컴파일러는 이 배열을 할당할 때마다 코드를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-203">The compiler has to emit code to allocate this array each time.</span></span>  <span data-ttu-id="14218-204">그 이유는 컴파일러가 <xref:System.String.Split%2A>이 배열을 다른 코드에 의해 배열이 수정(그러면 `WriteFormattedDocComment`에 대한 후속 호출에 영향을 미치게 됨)될 수 있는 어딘가에 저장하는지 여부를 알 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-204">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span>  <span data-ttu-id="14218-205">또한 <xref:System.String.Split%2A>에 대한 호출은 `text`의 모든 줄에 대해 문자열 하나를 할당하고 작업을 수행하기 위해 다른 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-205">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span>  
  
 <span data-ttu-id="14218-206">`WriteFormattedDocComment`에는 <xref:System.String.TrimStart%2A> 메서드에 대한 세 개의 호출이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-206">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span>  <span data-ttu-id="14218-207">두 개의 호출은 작업 및 할당을 중복하는 안쪽 루프에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-207">Two are in inner loops that duplicate work and allocations.</span></span>  <span data-ttu-id="14218-208">설상가상으로 인수 없이 <xref:System.String.TrimStart%2A> 메서드를 호출하면 문자열 결과 외에 빈 배열(`params` 매개 변수에 대한)이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-208">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span>  
  
 <span data-ttu-id="14218-209">마지막으로, 일반적으로 새 문자열을 할당하는 <xref:System.String.Substring%2A> 메서드에 대한 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-209">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span>  
  
 <span data-ttu-id="14218-210">**예제 3에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-210">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="14218-211">앞의 예제와 달리, 약간의 편집으로 이러한 할당을 해결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-211">Unlike the earlier examples, small edits cannot fix these allocations.</span></span>  <span data-ttu-id="14218-212">한 걸음 물러나 문제를 살펴보고 다르게 접근해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-212">You need to step back, look at the problem, and approach it differently.</span></span>  <span data-ttu-id="14218-213">예를 들어, `WriteFormattedDocComment()`에 대한 인수는 메서드에 필요한 모든 정보가 포함된 문자열이므로 코드는 많은 부분 문자열을 할당하는 대신 더 많은 인덱싱을 수행할 수 있다는 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-213">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span>  
  
 <span data-ttu-id="14218-214">컴파일러의 성능 팀은 다음과 같은 코드로 이러한 모든 할당을 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-214">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...  
```  
  
 <span data-ttu-id="14218-215">`WriteFormattedDocComment()`의 첫 번째 버전에서는 배열, 여러 부분 문자열 및 잘라낸 부분 문자열과 함께 빈 `params` 배열을 할당했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-215">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span>  <span data-ttu-id="14218-216">또한 첫 번째 버전에서는 `"///"`를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-216">It also checked for `"///"`.</span></span>  <span data-ttu-id="14218-217">수정된 코드에서는 인덱싱만 사용하며 아무것도 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-217">The revised code uses only indexing and allocates nothing.</span></span>  <span data-ttu-id="14218-218">수정된 코드에서는 공백이 아닌 첫 번째 문자를 찾은 다음, 문자를 한 자씩 확인하여 문자열이 `"///"`로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-218">It finds the first character that is not white space, and then checks character by character to see if the string starts with `"///"`.</span></span>  <span data-ttu-id="14218-219">새 코드에서는 `IndexOfFirstNonWhiteSpaceChar` 대신 <xref:System.String.TrimStart%2A>을 사용하여 공백이 아닌 문자가 있는 첫 번째 인덱스(지정된 시작 인덱스 뒤)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-219">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-whitespace character occurs.</span></span>  <span data-ttu-id="14218-220">해결 방법이 완벽하지는 않지만 완벽한 솔루션을 위해 유사한 해결 방법을 적용하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-220">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span>  <span data-ttu-id="14218-221">코드 전체에 이 접근 방식을 적용하여 `WriteFormattedDocComment()`에서 모든 할당을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-221">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span>  
  
 <span data-ttu-id="14218-222">**예제 4: StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="14218-222">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="14218-223">이 예제에서는 <xref:System.Text.StringBuilder> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-223">This example uses a <xref:System.Text.StringBuilder> object.</span></span>  <span data-ttu-id="14218-224">다음 함수에서는 제네릭 형식의 전체 형식 이름을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-224">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="14218-225">초점은 새 <xref:System.Text.StringBuilder> 인스턴스를 만드는 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-225">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span>  <span data-ttu-id="14218-226">이 코드에서는 `sb.ToString()`에 대한 할당과 <xref:System.Text.StringBuilder> 구현 내의 내부 할당이 발생하지만 문자열 결과를 원하는 경우 해당 할당을 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-226">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span>  
  
 <span data-ttu-id="14218-227">**예제 4에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-227">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="14218-228">`StringBuilder` 개체 할당을 해결하려면 개체를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-228">To fix the `StringBuilder` object allocation, cache the  object.</span></span>  <span data-ttu-id="14218-229">throw될 수 있는 단일 인스턴스를 캐시하는 것만으로도 성능을 현저히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-229">Even caching a single instance that might get thrown away can improve performance significantly.</span></span>  <span data-ttu-id="14218-230">다음은 함수의 새 구현이며, 여기에는 새로운 첫 번째 줄과 마지막 줄을 제외한 모든 코드가 생략되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-230">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="14218-231">핵심 부분은 새 `AcquireBuilder()` 및 `GetStringAndReleaseBuilder()` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-231">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="14218-232">새 컴파일러는 스레딩을 사용하므로 이러한 구현에서는 Thread 정적 필드(<xref:System.ThreadStaticAttribute> 특성)를 사용하여 <xref:System.Text.StringBuilder>를 캐시하고 사용자는 `ThreadStatic` 선언을 포기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-232">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span>  <span data-ttu-id="14218-233">Thread 정적 필드는 이 코드를 실행하는 각 스레드에 대해 고유한 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-233">The thread-static field holds a unique value for each thread that executes this code.</span></span>  
  
 <span data-ttu-id="14218-234">`AcquireBuilder()`는 캐시된 <xref:System.Text.StringBuilder> 인스턴스가 있는 경우 이를 지우고 필드 또는 캐시를 null로 설정한 후 해당 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-234">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span>  <span data-ttu-id="14218-235">그러지 않으면 `AcquireBuilder()`는 새 인스턴스를 만들어 반환하고 null로 설정된 필드 또는 캐시를 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="14218-235">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span>  
  
 <span data-ttu-id="14218-236"><xref:System.Text.StringBuilder>에 대한 작업을 완료했으면 `GetStringAndReleaseBuilder()`를 호출하여 문자열 결과를 가져오고 필드 또는 캐시에 <xref:System.Text.StringBuilder> 인스턴스를 저장한 다음 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-236">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span>  <span data-ttu-id="14218-237">드물게 발생하기는 하지만 실행이 이 코드에 다시 들어가서 여러 <xref:System.Text.StringBuilder> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-237">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span>  <span data-ttu-id="14218-238">코드는 나중에 사용하기 위해 마지막으로 해제된 <xref:System.Text.StringBuilder> 인스턴스만 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-238">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span>  <span data-ttu-id="14218-239">이 간단한 캐싱 전략 덕분에 새 컴파일러에서 할당이 현저히 감소했습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-239">This simple caching strategy significantly reduced allocations in the new compilers.</span></span>  <span data-ttu-id="14218-240">.NET Framework 및 MSBuild(“MSBuild”) 부분에서는 비슷한 기법을 사용하여 성능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-240">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span>  
  
 <span data-ttu-id="14218-241">이 간단한 캐싱 전략은 크기 한도를 포함하므로 좋은 캐시 디자인을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-241">This simple caching strategy adheres to good cache design because it has a size cap.</span></span>  <span data-ttu-id="14218-242">그러나 이제는 원본보다 코드가 많아져 유지 관리 비용이 더 듭니다.</span><span class="sxs-lookup"><span data-stu-id="14218-242">However, there is more code now than in the original, which means more maintenance costs.</span></span>  <span data-ttu-id="14218-243">성능 문제를 발견한 경우에만 캐싱 전략을 채택해야 하며, PerfView에 <xref:System.Text.StringBuilder> 할당이 중요한 기여 요소라는 사실이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-243">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span>  
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="14218-244">LINQ 및 람다</span><span class="sxs-lookup"><span data-stu-id="14218-244">LINQ and lambdas</span></span>  
 <span data-ttu-id="14218-245">LINQ(Language-Integrated Query) 및 람다 식을 사용하는 것은 나중에 코드가 성능에 중요한 영향을 미치는 경우 다시 작성해야 하는 생산성 기능 사용의 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-245">Using Language-Integrated Query (LINQ) and lambda expressions is a great example of using productive features that you might later find you need to rewrite if the code becomes a significant impact on performance.</span></span>  
  
 <span data-ttu-id="14218-246">**예제 5: 람다, List\<T> 및 IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="14218-246">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="14218-247">이 예제에서는 이름 문자열이 제공될 경우 [LINQ 및 기능 스타일 코드](http://blogs.msdn.com/b/charlie/archive/2007/01/26/anders-hejlsberg-on-linq-and-functional-programming.aspx)를 사용하여 컴파일러 모델에서 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-247">This example uses [LINQ and functional style code](http://blogs.msdn.com/b/charlie/archive/2007/01/26/anders-hejlsberg-on-linq-and-functional-programming.aspx) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="14218-248">새 컴파일러와 새 컴파일러에서 빌드된 IDE 환경에서는 `FindMatchingSymbol()`을 매우 자주 호출하며, 이 함수의 코드 한 줄에는 숨겨진 할당이 여러 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-248">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span>  <span data-ttu-id="14218-249">해당 할당을 검토하려면 먼저 함수의 코드 한 줄을 두 줄로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-249">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="14218-250">첫 번째 줄에서 [람다 식](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)`s => s.Name == name`[은 ](http://blogs.msdn.com/b/ericlippert/archive/2003/09/17/53028.aspx)지역 변수 `name`을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-250">In the first line, the [lambda expression](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)`s => s.Name == name`[closes over](http://blogs.msdn.com/b/ericlippert/archive/2003/09/17/53028.aspx) the local variable `name`.</span></span>  <span data-ttu-id="14218-251">즉, 이 코드에서는 `predicate`를 유지하는 [대리자](~/docs/csharp/language-reference/keywords/delegate.md)에 대한 개체를 할당할 뿐만 아니라 `name`의 값을 캡처하는 환경을 유지하기 위한 정적 클래스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-251">This means that in addition to allocating an object for the [delegate](~/docs/csharp/language-reference/keywords/delegate.md) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span>  <span data-ttu-id="14218-252">컴파일러는 다음과 같은 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-252">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="14218-253">이제 두 `new` 할당(환경 클래스에 대한 할당 하나와 대리자에 대한 할당 하나)은 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-253">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span>  
  
 <span data-ttu-id="14218-254">이제 `FirstOrDefault`에 대한 호출을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="14218-254">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="14218-255"><xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 형식에 대한 이 확장 메서드는 할당도 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="14218-255">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span>  <span data-ttu-id="14218-256">`FirstOrDefault`는 해당 첫 번째 인수로 <xref:System.Collections.Generic.IEnumerable%601> 개체를 사용하기 때문에 다음 코드에 대한 호출을 확장할 수 있습니다(설명을 위해 약간 단순화되어 있음).</span><span class="sxs-lookup"><span data-stu-id="14218-256">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...  
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="14218-257">`symbols` 변수의 형식은 <xref:System.Collections.Generic.List%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-257">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span>  <span data-ttu-id="14218-258"><xref:System.Collections.Generic.List%601> 컬렉션 형식은 <xref:System.Collections.Generic.IEnumerable%601>를 구현하고 <xref:System.Collections.Generic.IEnumerator%601>가 <xref:System.Collections.Generic.List%601>로 구현하는 열거자(`struct` 인터페이스)를 영리하게 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-258">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span>  <span data-ttu-id="14218-259">클래스 대신 구조를 사용하면 일반적으로 힙 할당을 피하게 되어 가비지 수집 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-259">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span>  <span data-ttu-id="14218-260">일반적으로 열거자는 호출 스택에서 반환됨에 따라 열거자 구조를 사용하는 언어의 `foreach` 루프와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-260">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span>  <span data-ttu-id="14218-261">개체에 대한 공간을 마련하기 위해 호출 스택 포인터를 증분하는 것은 힙 할당에서 수행하는 방식과 관련하여 GC에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-261">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span>  
  
 <span data-ttu-id="14218-262">확장된 `FirstOrDefault` 호출의 경우 코드에서는 `GetEnumerator()`에 대해 <xref:System.Collections.Generic.IEnumerable%601>를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-262">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  <span data-ttu-id="14218-263">`symbols` 형식의 `enumerable` 변수에 `IEnumerable<Symbol>`를 할당하면 실제 개체가 <xref:System.Collections.Generic.List%601>라는 정보가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-263">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span>  <span data-ttu-id="14218-264">즉, 코드에서 `enumerable.GetEnumerator()`로 열거자를 페치하면 .NET Framework가 반환된 구조를 boxing하여 열거자를 `enumerator` 변수에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-264">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span>  
  
 <span data-ttu-id="14218-265">**예제 5에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-265">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="14218-266">해결 방법은 다음과 같이 `FindMatchingSymbol`을 다시 작성하여 해당 코드 한 줄을 여전히 간결하고, 읽고 이해하기 쉬우며, 유지 관리하기 쉬운 6줄의 코드로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-266">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="14218-267">이 코드에서는 LINQ 확장 메서드, 람다 또는 열거자를 사용하지 않으며 할당도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-267">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span>  <span data-ttu-id="14218-268">컴파일러가 `symbols` 컬렉션이 <xref:System.Collections.Generic.List%601>이고, boxing을 피하기 위한 올바른 형식을 사용하여 결과 열거자(구조)를 로컬 변수에 바인딩할 수 있다는 사실을 알 수 있기 때문에 할당이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-268">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span>  <span data-ttu-id="14218-269">이 함수의 원래 버전은 C#의 표현 기능과 .NET Framework의 생산성을 보여 주는 좋은 예였습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-269">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span>  <span data-ttu-id="14218-270">보다 효율적인 이 새 버전은 유지 관리할 복잡할 코드를 추가하지 않고 이러한 품질을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-270">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span>  
  
### <a name="async-method-caching"></a><span data-ttu-id="14218-271">비동기 메서드 캐싱</span><span class="sxs-lookup"><span data-stu-id="14218-271">Async method caching</span></span>  
 <span data-ttu-id="14218-272">다음 예제에서는 [async](http://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7) 메서드에 캐시된 결과를 사용하려고 할 때 발생하는 일반적인 문제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14218-272">The next example shows a common problem when you try to use cached results in an [async](http://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7) method.</span></span>  
  
 <span data-ttu-id="14218-273">**예제 6: 비동기 메서드의 캐싱**</span><span class="sxs-lookup"><span data-stu-id="14218-273">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="14218-274">새 C# 및 Visual Basic 컴파일러에 빌드된 Visual Studio IDE 기능은 구문 트리를 자주 가져오고, 컴파일러는 Visual Studio의 응답성을 유지하기 위해 이렇게 할 때 비동기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-274">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span>  <span data-ttu-id="14218-275">다음은 구문 트리를 가져오기 위해 작성할 수 있는 코드의 첫 번째 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-275">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="14218-276">`GetSyntaxTreeAsync()`를 호출하면 `Parser`가 인스턴스화되고 코드가 구문 분석된 다음 <xref:System.Threading.Tasks.Task> 개체인 `Task<SyntaxTree>`가 반환된다는 사실을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-276">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span>  <span data-ttu-id="14218-277">비용이 많이 드는 부분은 `Parser` 인스턴스를 할당하고 코드를 구문 분석하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-277">The expensive part is allocating the `Parser` instance and parsing the code.</span></span>  <span data-ttu-id="14218-278">함수는 호출자가 구문 분석 작업을 기다리고, 사용자 입력에 대한 응답성을 유지하도록 UI 스레드를 해제할 수 있도록 <xref:System.Threading.Tasks.Task>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-278">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span>  
  
 <span data-ttu-id="14218-279">몇 가지 Visual Studio 기능에서는 동일한 구문 트리를 가져오려고 할 수 있으므로, 구문 분석 결과를 캐시하는 다음과 같은 코드를 작성하여 시간을 절약하고 할당을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-279">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span>  <span data-ttu-id="14218-280">그러나 이 코드에서는 할당이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-280">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="14218-281">캐싱이 포함된 새 코드에 `SyntaxTree`라는 `cachedResult` 필드가 있는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-281">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span>  <span data-ttu-id="14218-282">이 필드가 null이면 `GetSyntaxTreeAsync()`가 작동하고 결과를 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-282">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span>  <span data-ttu-id="14218-283">`GetSyntaxTreeAsync()`에서 `SyntaxTree` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-283">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span>  <span data-ttu-id="14218-284">문제는 `async` 형식의 `Task<SyntaxTree>` 함수가 있고 `SyntaxTree` 형식의 값을 반환하는 경우 컴파일러가 결과를 유지하기 위해 Task를 할당하는 코드를 내보낸다는 점입니다(`Task<SyntaxTree>.FromResult()` 사용).</span><span class="sxs-lookup"><span data-stu-id="14218-284">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span>  <span data-ttu-id="14218-285">Task는 완료됨으로 표시되고 결과는 즉시 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-285">The Task is marked as completed, and the result is immediately available.</span></span>  <span data-ttu-id="14218-286">새 컴파일러 코드에서 이미 완료된 <xref:System.Threading.Tasks.Task> 개체가 너무 자주 발생했는데, 이러한 할당을 해결함으로써 응답성이 현저히 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-286">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span>  
  
 <span data-ttu-id="14218-287">**예제 6에 대한 해결 방법**</span><span class="sxs-lookup"><span data-stu-id="14218-287">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="14218-288">완료 된 제거 하려면 <xref:System.Threading.Tasks.Task> 할당을 완료 된 결과로 Task 개체를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-288">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??   
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="14218-289">이 코드에서는 `cachedResult`의 형식이 `Task<SyntaxTree>`로 변경되고 `async`의 원래 코드를 유지하는 `GetSyntaxTreeAsync()` 도우미 함수가 채택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-289">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span>  <span data-ttu-id="14218-290">이제 `GetSyntaxTreeAsync()`는 `cachedResult`가 null이 아닌 경우 이를 반환하기 위해 [null 병합 연산자](../../csharp/language-reference/operators/null-coalescing-operator.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-290">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span>  <span data-ttu-id="14218-291">`cachedResult`가 null인 경우 `GetSyntaxTreeAsync()`는 `GetSyntaxTreeUncachedAsync()`를 호출하고 결과를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-291">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span>  <span data-ttu-id="14218-292">일반적으로 코드가 그러는 것처럼 `GetSyntaxTreeAsync()`는 `GetSyntaxTreeUncachedAsync()`에 대한 호출을 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-292">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span>  <span data-ttu-id="14218-293">await를 사용하지 않는다는 말은 `GetSyntaxTreeUncachedAsync()`에서 해당 <xref:System.Threading.Tasks.Task> 개체를 반환할 때 `GetSyntaxTreeAsync()`가 즉시 <xref:System.Threading.Tasks.Task>를 반환한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-293">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span>  <span data-ttu-id="14218-294">이제 캐시된 결과가 <xref:System.Threading.Tasks.Task>이므로 캐시된 결과를 반환하기 위한 할당이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-294">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="14218-295">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="14218-295">Additional considerations</span></span>  
 <span data-ttu-id="14218-296">다음은 규모가 큰 앱이나 많은 데이터를 처리하는 앱에서 발생할 수 있는 잠재적 문제에 대한 몇 가지 추가 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-296">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span>  
  
 <span data-ttu-id="14218-297">**사전**</span><span class="sxs-lookup"><span data-stu-id="14218-297">**Dictionaries**</span></span>  
  
 <span data-ttu-id="14218-298">사전은 많은 프로그램에서 보편적으로 사용되며 매우 편리하고 본질적으로 효율적이기는 하지만,</span><span class="sxs-lookup"><span data-stu-id="14218-298">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span>  <span data-ttu-id="14218-299">빈번히 부적절하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-299">However, they’re often used inappropriately.</span></span>  <span data-ttu-id="14218-300">Visual Studio 및 새 컴파일러에서 분석에는 단일 요소를 포함했거나 비어 있는 사전이 많이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-300">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span>  <span data-ttu-id="14218-301">빈 <xref:System.Collections.Generic.Dictionary%602>에는 10개의 필드가 포함되어 있고 이는 x86 컴퓨터의 힙에서 48바이트를 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-301">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span>  <span data-ttu-id="14218-302">매핑 또는 결합형 데이터 구조와 일정 시간 조회 기능이 필요한 경우 사전은 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-302">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span>  <span data-ttu-id="14218-303">그러나 보유한 요소가 몇 개 되지 않는 경우 사전을 사용하면 많은 공간을 낭비하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14218-303">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span>  <span data-ttu-id="14218-304">대신, 예를 들어 `List<KeyValuePair\<K,V>>`를 반복적으로 검토할 수 있으며 이는 원래 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="14218-304">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span>  <span data-ttu-id="14218-305">데이터가 포함된 사전을 로드한 다음 이 사전에서 읽기 위한 용도로만 사전을 사용하는 경우(매우 일반적인 패턴), 정렬된 배열과 함께 N(log(N)) 조회 기능을 사용하는 것이 거의 더 빠를 것입니다(사용 중인 요소 수에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="14218-305">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span>  
  
 <span data-ttu-id="14218-306">**클래스 및 구조체**</span><span class="sxs-lookup"><span data-stu-id="14218-306">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="14218-307">어떤 면에서는 클래스와 구조가 앱을 조정하는 것과 관련하여 전통적인 공간/시간 절충 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-307">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span>  <span data-ttu-id="14218-308">클래스는 필드를 포함하지 않는 경우에도 x86 컴퓨터에서 12바이트의 오버헤드를 발생시키지만, 클래스 인스턴스를 나타내는 포인터만 사용하므로 전달 비용이 별로 들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-308">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span>  <span data-ttu-id="14218-309">구조는 boxing되지 않은 경우 힙 할당을 발생시키지 않지만, 큰 구조를 함수 인수 또는 반환 값으로 전달하면 구조의 모든 데이터 멤버를 원자적으로 복사하기 위한 CPU 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="14218-309">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span>  <span data-ttu-id="14218-310">구조를 반환하는 속성에 대한 반복 호출을 감시하고, 해당 속성 값을 로컬 변수에 캐시하여 과도한 데이터 복사를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-310">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span>  
  
 <span data-ttu-id="14218-311">**캐시**</span><span class="sxs-lookup"><span data-stu-id="14218-311">**Caches**</span></span>  
  
 <span data-ttu-id="14218-312">일반적인 성능 트릭은 결과를 캐시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-312">A common performance trick is to cache results.</span></span>  <span data-ttu-id="14218-313">그러나 크기 한도 또는 삭제 정책이 없는 캐시는 메모리 누수가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-313">However, a cache without a size cap or disposal policy can be a memory leak.</span></span>  <span data-ttu-id="14218-314">많은 양의 데이터를 처리할 때 많은 메모리를 캐시에 유지하면 캐시된 조회의 이점을 무력화시킬 만큼의 가비지 수집이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-314">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span>  
  
 <span data-ttu-id="14218-315">이 문서에서는 앱의 응답성에 영향을 미칠 수 있는 성능 병목 현상 증상을 어떻게 알 수 있어야 하는지에 대해 설명했습니다(특히, 대규모 시스템이나 많은 양의 데이터를 처리하는 시스템의 경우).</span><span class="sxs-lookup"><span data-stu-id="14218-315">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="14218-316">일반적인 원인으로는 boxing, 문자열 조작, LINQ 및 람다, 비동기 메서드의 캐싱, 크기 제한 또는 삭제 정책이 없는 캐싱, 부적절한 사전 사용 및 구조 전달이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14218-316">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span>  <span data-ttu-id="14218-317">앱을 조정할 때는 다음과 같은 4가지 팩트에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="14218-317">Keep in mind the four facts for tuning your apps:</span></span>  
  
-   <span data-ttu-id="14218-318">너무 이르게 최적화하지 말 것 – 문제를 찾을 때는 생산성을 유지하고 앱을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="14218-318">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span>  
  
-   <span data-ttu-id="14218-319">프로필은 거짓말하지 않음 – 측정하는 것이 아니라면 추측하는 것일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-319">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span>  
  
-   <span data-ttu-id="14218-320">좋은 도구가 모든 차별화를 이뤄냄 – PerfView를 다운로드하여 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="14218-320">Good tools make all the difference – download PerfView and try it out.</span></span>  
  
-   <span data-ttu-id="14218-321">결국은 모두 할당에 관련된 문제임 – 이 부분이 바로 컴파일러 플랫폼 팀이 새 컴파일러의 성능을 향상시키기 위해 대부분의 시간을 사용하는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="14218-321">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14218-322">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14218-322">See Also</span></span>  
 [<span data-ttu-id="14218-323">이 항목의 표현의 비디오</span><span class="sxs-lookup"><span data-stu-id="14218-323">Video of presentation of this topic</span></span>](http://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)  
 [<span data-ttu-id="14218-324">초보자를 위한 성능 프로파일링 지침</span><span class="sxs-lookup"><span data-stu-id="14218-324">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)  
 [<span data-ttu-id="14218-325">성능</span><span class="sxs-lookup"><span data-stu-id="14218-325">Performance</span></span>](../../../docs/framework/performance/index.md)  
 [<span data-ttu-id="14218-326">.NET 성능 팁</span><span class="sxs-lookup"><span data-stu-id="14218-326">.NET Performance Tips</span></span>](http://msdn.microsoft.com/library/ms973839.aspx)  
 [<span data-ttu-id="14218-327">Windows Phone 성능 분석 도구</span><span class="sxs-lookup"><span data-stu-id="14218-327">Windows Phone Performance Analysis Tool</span></span>](http://msdn.microsoft.com/magazine/hh781024.aspx)  
 [<span data-ttu-id="14218-328">Visual Studio 프로파일러를 사용한 응용 프로그램 병목 지점 찾기</span><span class="sxs-lookup"><span data-stu-id="14218-328">Find Application Bottlenecks with Visual Studio Profiler</span></span>](http://msdn.microsoft.com/magazine/cc337887.aspx)  
 [<span data-ttu-id="14218-329">채널 9 PerfView 자습서</span><span class="sxs-lookup"><span data-stu-id="14218-329">Channel 9 PerfView tutorials</span></span>](http://channel9.msdn.com/Series/PerfView-Tutorial)  
 [<span data-ttu-id="14218-330">상위 수준 성능 팁</span><span class="sxs-lookup"><span data-stu-id="14218-330">High-level Performance Tips</span></span>](http://curah.microsoft.com/4604/improving-your-net-apps-startup-performance)  
 [<span data-ttu-id="14218-331">GitHub의 리포지토리 dotnet/roslyn</span><span class="sxs-lookup"><span data-stu-id="14218-331">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)

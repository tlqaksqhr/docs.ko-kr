---
title: 비동기 프로그래밍 패턴
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42298bc8e3101b03f6c3e03fec453b72cd959efb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="89036-102">비동기 프로그래밍 패턴</span><span class="sxs-lookup"><span data-stu-id="89036-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="89036-103">.NET Framework에서는 비동기 작업을 수행하기 위한 세 가지 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="89036-104"><xref:System.IAsyncResult> 패턴이라고도 하는 APM(비동기 프로그래밍 모델) 패턴. 이 패턴에서는 비동기 작업을 수행하려면 `Begin` 및 `End` 메서드가 필요합니다. 예를 들어 비동기 쓰기 작업의 경우에는 `BeginWrite` 및 `EndWrite` 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="89036-105">신규 개발에서는 이 패턴을 더 이상 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="89036-106">자세한 내용은 [APM(비동기 프로그래밍 모델)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89036-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="89036-107">EAP(이벤트 기반 비동기 패턴). 이 패턴에서는 `Async` 접미사가 있는 메서드가 필요하며 하나 이상의 이벤트, 이벤트 처리기 대리가 형식 및 `EventArg`에서 파생된 형식도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="89036-108">EAP는 .NET Framework 2.0에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="89036-109">이 패턴 역시 신규 개발에서는 더 이상 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="89036-110">자세한 내용은 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89036-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="89036-111">단일 메서드를 사용하여 비동기 작업 시작과 완료를 나타내는 TAP(작업 기반 비동기 패턴).</span><span class="sxs-lookup"><span data-stu-id="89036-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="89036-112">TAP는 .NET Framework 4에 도입되었으며, .NET Framework에서 비동기 프로그래밍을 수행할 때는 이 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="89036-113">C#의 [async](~/docs/csharp/language-reference/keywords/async.md) 및 [await](~/docs/csharp/language-reference/keywords/await.md) 키워드와 Visual Basic 언어의 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 및 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 연산자는 TAP에 대한 언어 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="89036-114">자세한 내용은 [TAP(작업 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89036-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="89036-115">패턴 비교</span><span class="sxs-lookup"><span data-stu-id="89036-115">Comparing Patterns</span></span>  

<span data-ttu-id="89036-116">위의 세 가지 패턴 모델이 비동기 작업을 수행하는 방법을 빠르게 비교하려는 경우 지정한 오프셋에서부터 지정된 양의 데이터를 제공된 버퍼로 읽어 들이는 `Read` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="89036-117">이 메서드에 해당하는 APM 코드는 `BeginRead` 및 `EndRead` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="89036-118">그리고 이 메서드에 해당하는 EAP 코드는 다음 형식 및 멤버 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="89036-119">TAP에 해당하는 코드는 다음의 단일 `ReadAsync` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="89036-120">TAP, APM 및 EAP에 대한 포괄적인 설명은 다음 섹션에 나와 있는 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89036-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="89036-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="89036-121">Related topics</span></span>

| <span data-ttu-id="89036-122">제목</span><span class="sxs-lookup"><span data-stu-id="89036-122">Title</span></span> | <span data-ttu-id="89036-123">설명</span><span class="sxs-lookup"><span data-stu-id="89036-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="89036-124">APM(비동기 프로그래밍 모델)</span><span class="sxs-lookup"><span data-stu-id="89036-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="89036-125"><xref:System.IAsyncResult> 인터페이스를 사용하여 비동기 동작을 제공하는 레거시 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="89036-126">신규 개발에서는 이 모델을 더 이상 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="89036-127">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="89036-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="89036-128">비동기 동작을 제공하기 위한 이벤트 기반 레거시 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="89036-129">신규 개발에서는 이 모델을 더 이상 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="89036-130">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="89036-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="89036-131"><xref:System.Threading.Tasks> 네임스페이스를 기반으로 하는 새 비동기 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89036-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="89036-132">.NET Framework 4 이상 버전에서 비동기 프로그래밍을 수행할 때는 이 모델을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89036-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="89036-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89036-133">See also</span></span>

<span data-ttu-id="89036-134">[C#의 비동기 프로그래밍](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="89036-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="89036-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) (F#의 비동기 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="89036-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="89036-136">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89036-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)

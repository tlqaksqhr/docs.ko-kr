---
title: 이벤트 소개
description: 이 개요에서는 .NET Core의 이벤트와 이벤트에 대한 언어 디자인 목표를 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: 2a2230ea5fba1b0cd5b13319677965e7a776549e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33213476"
---
# <a name="introduction-to-events"></a><span data-ttu-id="267ff-103">이벤트 소개</span><span class="sxs-lookup"><span data-stu-id="267ff-103">Introduction to Events</span></span>

[<span data-ttu-id="267ff-104">이전</span><span class="sxs-lookup"><span data-stu-id="267ff-104">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="267ff-105">대리자와 같은 이벤트는 *런타임에 바인딩* 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-105">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="267ff-106">실제로 이벤트는 대리자에 대한 언어 지원을 기반으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-106">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="267ff-107">이벤트는 어떠한 문제가 발생했다는 사실을 개체가 시스템의 모든 관련 구성 요소에 브로드캐스트하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-107">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="267ff-108">다른 모든 구성 요소는 이벤트를 구독하고 이벤트가 발생할 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-108">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="267ff-109">일부 프로그래밍에서 이벤트를 사용했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-109">You've probably used events in some of your programming.</span></span> <span data-ttu-id="267ff-110">많은 그래픽 시스템에는 사용자 조작을 보고하는 이벤트 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-110">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="267ff-111">이러한 이벤트는 마우스 이동, 단추 누름 등의 조작을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-111">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="267ff-112">가장 일반적인 시나리오이기는 하지만 이벤트가 사용되는 유일한 시나리오는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-112">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="267ff-113">클래스에 대해 발생해야 하는 이벤트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-113">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="267ff-114">이벤트로 작업할 때 한 가지 중요한 고려 사항은 특정 이벤트에 대해 등록된 개체가 없을 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-114">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="267ff-115">구성된 수신기가 없는 경우 이벤트를 발생시키지 않도록 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-115">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="267ff-116">이벤트를 구독하면 두 개체(이벤트 소스와 이벤트 싱크) 간 결합도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-116">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="267ff-117">더 이상 이벤트에 관심이 없는 경우 이벤트 싱크가 이벤트 소스를 구독 취소하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-117">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="267ff-118">이벤트 지원의 디자인 목표</span><span class="sxs-lookup"><span data-stu-id="267ff-118">Design Goals for Event Support</span></span>

<span data-ttu-id="267ff-119">이벤트에 대한 언어 디자인은 이러한 목표를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-119">The language design for events targets these goals.</span></span>

<span data-ttu-id="267ff-120">먼저 이벤트 소스와 이벤트 싱크 간에 최소 결합을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-120">First, enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="267ff-121">이러한 두 구성 요소는 동일한 조직에서 작성할 수 없으며 완전히 다른 일정으로 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-121">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

<span data-ttu-id="267ff-122">둘째로, 이벤트를 구독하고 동일한 이벤트를 구독 취소하는 작업은 매우 간단해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-122">Secondly, it should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

<span data-ttu-id="267ff-123">마지막으로 이벤트 소스는 여러 이벤트 구독자를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-123">And finally, event sources should support multiple event subscribers.</span></span> <span data-ttu-id="267ff-124">또한 연결된 이벤트 구독자가 없는 경우를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-124">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="267ff-125">이벤트의 목표가 대리자의 목표와 매우 유사하다는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-125">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="267ff-126">따라서 이벤트 언어 지원은 대리자 언어 지원을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-126">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="267ff-127">이벤트의 언어 지원</span><span class="sxs-lookup"><span data-stu-id="267ff-127">Language Support for Events</span></span>

<span data-ttu-id="267ff-128">이벤트를 정의하고 이벤트를 구독 또는 구독 취소하는 구문은 대리자에 대한 구문의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-128">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="267ff-129">`event` 키워드를 사용하는 이벤트를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="267ff-129">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="267ff-130">이벤트(이 예제의 경우 `EventHandler<FileListArgs>`)의 형식은 대리자 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-130">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="267ff-131">이벤트를 선언할 때 따라야 할 여러 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-131">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="267ff-132">일반적으로 이벤트 대리자 형식에는 void 반환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-132">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="267ff-133">이벤트 선언은 동사 또는 동사 구여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-133">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="267ff-134">발생된 어떤 문제를 보고할 때 이벤트는 이 예제에서처럼 과거 시제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-134">Use past tense (as in this example) when the event reports something that has happened.</span></span> <span data-ttu-id="267ff-135">발생하려고 하는 어떤 문제를 보고하려면 현재 시제 동사(예: `Closing`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-135">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="267ff-136">종종 현재 시제를 사용하여 클래스가 몇 가지 사용자 지정 동작을 지원함을 나타내기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-136">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="267ff-137">가장 일반적인 시나리오 중 하나는 취소를 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-137">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="267ff-138">예를 들어 `Closing` 이벤트에는 닫기 작업이 계속되어야 하는지 여부를 나타내는 인수가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-138">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="267ff-139">다른 시나리오를 통해 호출자는 이벤트 인수의 속성을 업데이트하여 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-139">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="267ff-140">알고리즘에서 수행하도록 제안된 다음 작업을 나타내는 이벤트를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-140">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="267ff-141">이벤트 처리기는 이벤트 인수의 속성을 수정하여 다른 작업을 강제로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-141">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="267ff-142">이벤트를 발생시키려면 대리자 호출 구문을 사용하여 이벤트 처리기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-142">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="267ff-143">[대리자](delegates-patterns.md)에 대한 섹션에서 설명한 대로 ?.</span><span class="sxs-lookup"><span data-stu-id="267ff-143">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="267ff-144">연산자를 사용하면 해당 이벤트에 대한 구독자가 없을 때 이벤트를 발생시키지 않도록 하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-144">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>
 
<span data-ttu-id="267ff-145">`+=` 연산자를 사용하여 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-145">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);
lister.Progress += OnProgress;
```

<span data-ttu-id="267ff-146">위에 표시된 대로 처리기 메서드는 일반적으로 접두사 'On'과 그다음에 오는 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-146">The handler method typically is the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="267ff-147">`-=` 연산자를 사용하여 구독 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-147">You unsubscribe using the `-=` operator:</span></span>

```csharp
lister.Progress -= onProgress;
```

<span data-ttu-id="267ff-148">이벤트 처리기를 나타내는 식에 대해 지역 변수를 선언했습니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-148">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="267ff-149">따라서 구독 취소하면 처리기가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-149">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="267ff-150">대신 람다 식의 본문을 사용한 경우 연결되지 않아 아무 작업도 수행하지 않는 처리기를 제거하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-150">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="267ff-151">다음 문서에서는 일반적인 이벤트 패턴 및 이 예제의 다양한 변형에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="267ff-151">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="267ff-152">다음</span><span class="sxs-lookup"><span data-stu-id="267ff-152">Next</span></span>](event-pattern.md)

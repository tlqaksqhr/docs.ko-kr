---
title: "스레드 만들기 및 시작할 때 데이터 전달"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="52b93-102">스레드 만들기 및 시작할 때 데이터 전달</span><span class="sxs-lookup"><span data-stu-id="52b93-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="52b93-103">운영 체제 프로세스를 만들면 운영 체제는 모든 원래 응용 프로그램 도메인을 포함 하 여 해당 프로세스에서 코드를 실행 하는 스레드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="52b93-104">해당 시점부터 응용 프로그램 도메인 만들고 사용할 수 있는 운영 체제 스레드 반드시를 만들거나 삭제 하지 않고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="52b93-105">실행 중인 코드가 관리 되는 경우 코드를 있는 <xref:System.Threading.Thread> 현재 응용 프로그램 도메인에서 실행 중인 스레드의 정적 검색 하 여 얻을 수 있습니다에 대 한 개체 <xref:System.Threading.Thread.CurrentThread%2A> 형식의 속성 <xref:System.Threading.Thread>합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="52b93-106">이 항목 스레드 만들기에 설명 하 고 데이터를 스레드 프로시저에 전달 하는 대체 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="52b93-107">스레드 만들기</span><span class="sxs-lookup"><span data-stu-id="52b93-107">Creating a Thread</span></span>  
 <span data-ttu-id="52b93-108">새 <xref:System.Threading.Thread> 개체는 관리 되는 새 스레드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="52b93-109"><xref:System.Threading.Thread> 클래스에 사용 하는 생성자는 <xref:System.Threading.ThreadStart> 위임 또는 <xref:System.Threading.ParameterizedThreadStart> 위임; 대리자 호출 하는 경우 새 스레드에 의해 호출 되는 메서드를 래핑합니다는 <xref:System.Threading.Thread.Start%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="52b93-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="52b93-110">호출 <xref:System.Threading.Thread.Start%2A> 두 번 이상 발생 한 <xref:System.Threading.ThreadStateException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="52b93-111"><xref:System.Threading.Thread.Start%2A> 새 스레드가 시작 실제로 전에 즉시, 종종 메서드에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="52b93-112">사용할 수는 <xref:System.Threading.Thread.ThreadState%2A> 및 <xref:System.Threading.Thread.IsAlive%2A> 속성을 모든 한 시점에서 스레드의 상태를 확인 하지만 이러한 속성 사용 하지 말아야 스레드 활동을 동기화 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52b93-113">에 대 한 참조를 유지할 필요가 없다는 스레드가 시작 되 면는 <xref:System.Threading.Thread> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="52b93-114">스레드 실행 스레드 프로시저가 종료 될 때까지 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="52b93-115">다음 코드 예제에서는 다른 개체에서 인스턴스 및 정적 메서드를 호출 하는 두 개의 새 스레드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="52b93-116">스레드에 데이터 전달 하 고 스레드의 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="52b93-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="52b93-117">.NET Framework 버전 2.0에에서는 <xref:System.Threading.ParameterizedThreadStart> 대리자를 호출 하는 경우 스레드에 대 한 데이터를 포함 하는 개체를 전달 하는 쉬운 방법을 제공는 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 메서드 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="52b93-118">코드 예는 <xref:System.Threading.ParameterizedThreadStart>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52b93-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="52b93-119">사용 하는 <xref:System.Threading.ParameterizedThreadStart> 때문에 대리자는 데이터를 전달 하는 형식이 안전한 방법을 아닙니다는 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 메서드 오버 로드는 모든 개체를 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="52b93-120">대신 스레드 프로시저와 도우미 클래스의 데이터를 캡슐화 하 고 사용 하는 고 <xref:System.Threading.ThreadStart> 스레드 프로시저를 실행할 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="52b93-121">이 기술은 나오는 두 코드 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="52b93-122">이러한 데이터는 비동기 호출에서 반환할 화면은 때문에 대리자에는 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="52b93-123">스레드 메서드의 결과 검색 하려면 두 번째 코드 예제에서와 같이 콜백 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="52b93-124">콜백 메서드를 사용 하 여 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="52b93-125">다음 예제에서는 스레드에서 데이터를 검색 하는 콜백 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="52b93-126">데이터와 스레드 메서드를 포함 하는 클래스에 대 한 생성자는 또한 콜백 메서드를 나타내는 대리자를 허용 스레드 메서드 종료 하기 전에 콜백 대리자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b93-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="52b93-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52b93-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="52b93-128">스레딩</span><span class="sxs-lookup"><span data-stu-id="52b93-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="52b93-129">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="52b93-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)

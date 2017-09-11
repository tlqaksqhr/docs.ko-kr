---
title: "방법: ConcurrentDictionary에서 항목 추가 및 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40291d424916c2f87a2070a9a8a6e49243ac083a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a><span data-ttu-id="9fefd-102">방법: ConcurrentDictionary에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="9fefd-102">How to: Add and Remove Items from a ConcurrentDictionary</span></span>
<span data-ttu-id="9fefd-103">이 예제는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>에서 항목을 추가, 검색, 업데이트 및 제거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-103">This example shows how to add, retrieve, update, and remove items from a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>.</span></span> <span data-ttu-id="9fefd-104">이 컬렉션 클래스는 스레드로부터 안전하게 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-104">This collection class is a thread-safe implementation.</span></span> <span data-ttu-id="9fefd-105">여러 스레드에서 컬렉션에 동시에 액세스할 수 있을 때는 언제든지 이 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-105">We recommend that you use it whenever multiple threads might be attempting to access the elements concurrently.</span></span>  
  
 <span data-ttu-id="9fefd-106"><xref:System.Collections.Concurrent.ConcurrentDictionary%602>에서는 추가하거나 제거하려고 시도하기 전에 키의 존재 여부를 먼저 확인하는 코드가 필요하지 않게 하는 편리한 몇 가지 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-106"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> provides several convenience methods that make it unnecessary for code to first check whether a key exists before it attempts to add or remove data.</span></span> <span data-ttu-id="9fefd-107">다음 표에서는 이처럼 편리한 메서드를 나열하고 해당 메서드가 사용되는 경우에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-107">The following table lists these convenience methods and describes when to use them.</span></span>  
  
|<span data-ttu-id="9fefd-108">메서드</span><span class="sxs-lookup"><span data-stu-id="9fefd-108">Method</span></span>|<span data-ttu-id="9fefd-109">사용 시기...</span><span class="sxs-lookup"><span data-stu-id="9fefd-109">Use when…</span></span>|  
|------------|---------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|<span data-ttu-id="9fefd-110">지정된 키의 새 값을 추가하려는 경우 및 이미 존재하는 키의 값을 바꾸려는 경우</span><span class="sxs-lookup"><span data-stu-id="9fefd-110">You want to add a new value for a specified key and, if the key already exists, you want to replace its value.</span></span>|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|<span data-ttu-id="9fefd-111">지정된 키의 기존 값을 검색하려는 경우 및 존재하지 않는 키/값 쌍을 지정하려는 경우</span><span class="sxs-lookup"><span data-stu-id="9fefd-111">You want to retrieve the existing value for a specified key and, if the key does not exist, you want to specify a key/value pair.</span></span>|  
|<span data-ttu-id="9fefd-112"><xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A></span><span class="sxs-lookup"><span data-stu-id="9fefd-112"><xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A></span></span>|<span data-ttu-id="9fefd-113">키/값 쌍 추가, 가져오기, 업데이트 또는 제거를 수행하려는 경우 및 어떤 이유로 인해 이러한 시도가 실패하거나 이미 키가 존재할 때 다른 작업을 대신 수행하려는 경우</span><span class="sxs-lookup"><span data-stu-id="9fefd-113">You want to add, get, update, or remove a key/value pair, and, if the key already exists or the attempt fails for any other reason, you want to take some alternative action.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9fefd-114">예제</span><span class="sxs-lookup"><span data-stu-id="9fefd-114">Example</span></span>  
 <span data-ttu-id="9fefd-115">다음 예제에서는 두 <xref:System.Threading.Tasks.Task> 인스턴스를 사용하여 일부 요소를 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>에 동시에 추가한 다음 모든 콘텐츠를 출력하여 해당 요소가 성공적으로 추가되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-115">The following example uses two <xref:System.Threading.Tasks.Task> instances to add some elements to a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> concurrently, and then outputs all of the contents to show that the elements were added successfully.</span></span> <span data-ttu-id="9fefd-116">또한 이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 메서드를 사용하여 컬렉션의 항목을 추가, 업데이트 및 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-116">The example also shows how to use the <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, and <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> methods to add, update, and retrieve  items from the collection.</span></span>  
  
 <span data-ttu-id="9fefd-117">[!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)] [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]</span><span class="sxs-lookup"><span data-stu-id="9fefd-117">[!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)] [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]</span></span>  
  
 <span data-ttu-id="9fefd-118"><xref:System.Collections.Concurrent.ConcurrentDictionary%602>는 다중 스레드 시나리오를 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-118"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> is designed for multithreaded scenarios.</span></span> <span data-ttu-id="9fefd-119">이 컬렉션에서 항목을 추가하거나 제거하기 위해 코드에 잠금을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-119">You do not have to use locks in your code to add or remove items from the collection.</span></span> <span data-ttu-id="9fefd-120">그러나 동일한 키에 새 값을 지정하여 한 스레드에서 값을 검색하고 다른 스레드에서 컬렉션을 바로 업데이트하는 것은 언제든지 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-120">However, it is always possible for one thread to retrieve a value, and another thread to immediately update the collection by giving the same key a new value.</span></span>  
  
 <span data-ttu-id="9fefd-121">또한 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>의 모든 메서드가 스레드로부터 안전하지만 모든 메서드, 특히 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>가 원자성 메서드인 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-121">Also, although all methods of <xref:System.Collections.Concurrent.ConcurrentDictionary%602> are thread-safe, not all methods are atomic, specifically <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.</span></span> <span data-ttu-id="9fefd-122">이러한 메서드에 전달되는 사용자 대리자는 사전의 내부 잠금 밖에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-122">The user delegate that is passed to these methods is invoked outside of the dictionary's internal lock.</span></span> <span data-ttu-id="9fefd-123">알려지지 않은 코드에서 모든 스레드를 차단하지 않도록 하기 위해 이렇게 합니다. 따라서 다음과 같은 이벤트 시퀀스가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-123">(This is done to prevent unknown code from blocking all threads.) Therefore it is possible for this sequence of events to occur:</span></span>  
  
 <span data-ttu-id="9fefd-124">1\) threadA에서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>를 호출하고, 항목을 찾지 못하면, valueFactory 대리자를 호출하여 Add에 새 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-124">1\) threadA calls <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, finds no item and creates a new item to Add by invoking the valueFactory delegate.</span></span>  
  
 <span data-ttu-id="9fefd-125">2\) threadB에서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>를 동시에 호출하고, 해당 valueFactory 대리자가 호출된 다음 threadA보다 먼저 내부 잠금에 도달하여 threadB의 새 키-값 쌍이 사전에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-125">2\) threadB calls <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> concurrently, its valueFactory delegate is invoked and it arrives at the internal lock before threadA, and so its new key-value pair is added to the dictionary.</span></span>  
  
 <span data-ttu-id="9fefd-126">3\) threadA의 사용자 대리자가 완료되고 스레드가 잠금에 도달하지만 이제는 해당 항목이 이미 존재하는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-126">3\) threadA's user delegate completes, and the thread arrives at the lock, but now sees that the item exists already</span></span>  
  
 <span data-ttu-id="9fefd-127">4\) threadA에서 "Get"을 수행하고 이전에 threadB에서 추가한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-127">4\) threadA performs a "Get", and returns the data that was previously added by threadB.</span></span>  
  
 <span data-ttu-id="9fefd-128">따라서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>에서 반환한 데이터가 스레드의 valueFactory에서 만든 것과 동일한 데이터라고 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-128">Therefore, it is not guaranteed that the data that is returned by <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> is the same data that was created by the thread's valueFactory.</span></span> <span data-ttu-id="9fefd-129"><xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>를 호출할 때에도 비슷한 이벤트 시퀀스가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fefd-129">A similar sequence of events can occur when <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fefd-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fefd-130">See Also</span></span>  
 <span data-ttu-id="9fefd-131"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9fefd-131"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="9fefd-132">스레드로부터 안전한 컬렉션</span><span class="sxs-lookup"><span data-stu-id="9fefd-132">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)


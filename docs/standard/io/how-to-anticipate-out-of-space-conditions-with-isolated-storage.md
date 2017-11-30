---
title: "방법: 격리된 저장소의 공간 부족 상태 예상"
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
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="e243b-102">방법: 격리된 저장소의 공간 부족 상태 예상</span><span class="sxs-lookup"><span data-stu-id="e243b-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>
<span data-ttu-id="e243b-103">격리 된 저장소를 사용 하는 코드에 의해 제한 되는 [할당량](../../../docs/standard/io/isolated-storage.md#quotas) 는 데이터 구획 격리 된 저장소 파일과 디렉터리가 존재에 대 한 최대 크기를 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="e243b-104">이 할당 한도는 보안 정책에서 정의하고 관리자가 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="e243b-105">데이터를 쓸 때 최대 허용 크기를 초과하면 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw되고 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="e243b-106">이렇게 하면 데이터 저장소가 꽉 차서은 요청을 거부 하도록 응용 프로그램을 일으킬 수 있는 악의적인 서비스 거부 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>  
  
 <span data-ttu-id="e243b-107">지정 된 쓰기 시도가 이러한 이유로 인해 실패할 수 인지를 결정할 수 있도록는 <xref:System.IO.IsolatedStorage.IsolatedStorage> 세 개의 읽기 전용 속성을 제공 하는 클래스: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, 및 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="e243b-108">이러한 속성을 사용하여 저장소에 쓰는 작업으로 인해 저장소의 최대 허용 크기가 초과되는지 여부를 판단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="e243b-109">격리된 저장소에 동시에 액세스할 수 있음을 명심하십시오. 따라서 남은 저장소 크기를 계산하는 경우 저장소에 쓰는 시간에 따라 저장소 공간이 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="e243b-110">그러나 사용 가능한 저장소의 상한값에 도달하는지 여부를 판단하기 위해 저장소의 최대 크기를 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>  
  
 <span data-ttu-id="e243b-111"><xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> 속성이 제대로 동작하려면 어셈블리에 대한 증명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="e243b-112">따라서 이 속성을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, 또는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> 메서드를 사용하여 만들어진 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> 개체에서만 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="e243b-113">다른 방법으로 만들어진 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체(예: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드에서 반환된 개체)는 정확한 최대 크기를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e243b-114">예제</span><span class="sxs-lookup"><span data-stu-id="e243b-114">Example</span></span>  
 <span data-ttu-id="e243b-115">다음 코드 예제에서는 격리 된 저장소를 가져오는 몇 가지 파일이 생성 하 고, 검색 된 <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="e243b-116">바이트에 남은 공간이 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e243b-116">The remaining space is reported in bytes.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="e243b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e243b-117">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="e243b-118">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="e243b-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="e243b-119">방법: 격리된 저장소의 저장소 가져오기</span><span class="sxs-lookup"><span data-stu-id="e243b-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)

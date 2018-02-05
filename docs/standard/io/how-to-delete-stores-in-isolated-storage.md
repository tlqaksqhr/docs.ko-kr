---
title: "방법: 격리된 저장소에서 저장소 삭제"
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
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ae04deeb8d23b496a9111b0d4b5b68e12ac1439
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-delete-stores-in-isolated-storage"></a><span data-ttu-id="1055f-102">방법: 격리된 저장소에서 저장소 삭제</span><span class="sxs-lookup"><span data-stu-id="1055f-102">How to: Delete Stores in Isolated Storage</span></span>
<span data-ttu-id="1055f-103"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 격리된 저장소 파일을 삭제하기 위해 다음과 같은 두 가지 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-103">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies two methods for deleting isolated storage files:</span></span>  
  
-   <span data-ttu-id="1055f-104">인스턴스 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> 는 인수를 사용하지 않으며 메서드를 호출하는 저장소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-104">The instance method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> does not take any arguments and deletes the store that calls it.</span></span> <span data-ttu-id="1055f-105">사용 권한이 없어도 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-105">No permissions are required for this operation.</span></span> <span data-ttu-id="1055f-106">저장소에 액세스할 수 있는 코드는 저장소 내의 데이터를 일부 또는 모두 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-106">Any code that can access the store can delete any or all the data inside it.</span></span>  
  
-   <span data-ttu-id="1055f-107">정적 메서드 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> 는 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 열거형 값을 사용하여 코드를 실행 중인 사용자의 모든 저장소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-107">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> takes the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> enumeration value, and deletes all the stores for the user who is running the code.</span></span> <span data-ttu-id="1055f-108">이 작업을 수행하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 값에 대한 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-108">This operation requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission for the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1055f-109">예제</span><span class="sxs-lookup"><span data-stu-id="1055f-109">Example</span></span>  
 <span data-ttu-id="1055f-110">다음 코드 예제에서는 정적 및 인스턴스 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-110">The following code example demonstrates the use of the static and instance <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> methods.</span></span> <span data-ttu-id="1055f-111">이 클래스는 사용자 및 어셈블리에 대해 격리된 저장소와 사용자, 도메인 및 어셈블리에 대해 격리된 저장소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-111">The class obtains two stores; one is isolated for user and assembly and the other is isolated for user, domain, and assembly.</span></span> <span data-ttu-id="1055f-112">그런 다음 격리된 저장소 파일 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> 의  `isoStore1`메서드를 호출하여 사용자, 도메인 및 어셈블리 저장소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-112">The user, domain, and assembly store is then deleted by calling the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> method of the isolated storage file  `isoStore1`.</span></span> <span data-ttu-id="1055f-113">마지막으로 정적 메서드인 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>를 호출하여 사용자에 대한 나머지 저장소를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1055f-113">Then, all remaining stores for the user are deleted by calling the static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1055f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1055f-114">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="1055f-115">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="1055f-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

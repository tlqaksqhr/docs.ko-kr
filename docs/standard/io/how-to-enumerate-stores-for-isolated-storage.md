---
title: '방법: 격리된 저장소의 저장소 열거'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77f6053cad85b5012a455a1fc020e0f559defdc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="5dc6c-102">방법: 격리된 저장소의 저장소 열거</span><span class="sxs-lookup"><span data-stu-id="5dc6c-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="5dc6c-103"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> 정적 메서드를 사용하여 현재 사용자에 대한 모든 격리된 저장소를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dc6c-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="5dc6c-104">이 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 값을 사용하여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc6c-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="5dc6c-105">저장소를 열거하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 값을 지정하는 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc6c-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="5dc6c-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 값을 사용하여 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 메서드를 호출하면 현재 사용자에 대해 정의된 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc6c-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc6c-107">예</span><span class="sxs-lookup"><span data-stu-id="5dc6c-107">Example</span></span>  
 <span data-ttu-id="5dc6c-108">다음 코드 예제에서는 사용자 및 어셈블리별로 격리된 저장소를 가져오고, 몇 개의 파일을 만든 다음, 이러한 파일을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드를 사용하여 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5dc6c-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5dc6c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5dc6c-109">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="5dc6c-110">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="5dc6c-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

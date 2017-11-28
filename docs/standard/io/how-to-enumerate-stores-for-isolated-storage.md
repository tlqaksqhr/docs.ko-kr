---
title: "방법: 격리된 저장소의 저장소 열거"
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
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>방법: 격리된 저장소의 저장소 열거
<xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> 정적 메서드를 사용하여 현재 사용자에 대한 모든 격리된 저장소를 열거할 수 있습니다. 이 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 값을 사용하여 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 열거자를 반환합니다. 저장소를 열거하려면 <xref:System.Security.Permissions.IsolatedStorageFilePermission> 값을 지정하는 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 권한이 있어야 합니다. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 값을 사용하여 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 메서드를 호출하면 현재 사용자에 대해 정의된 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 개체의 배열을 반환합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용자 및 어셈블리별로 격리된 저장소를 가져오고, 몇 개의 파일을 만든 다음, 이러한 파일을 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 메서드를 사용하여 검색합니다.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)

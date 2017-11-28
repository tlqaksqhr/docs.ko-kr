---
title: "방법: 격리된 저장소의 파일 읽기 및 쓰기"
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
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8d733efc3d70070dd12f55c651033e97d1792c38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="090a2-102">방법: 격리된 저장소의 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="090a2-102">How to: Read and Write to Files in Isolated Storage</span></span>
<span data-ttu-id="090a2-103">격리된 저장소에서 파일을 읽고 쓰기 위해, 스트림 판독기(<xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> 개체)를 가진 <xref:System.IO.StreamReader> 개체 또는 스트림 작성기(<xref:System.IO.StreamWriter> 개체)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="090a2-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="090a2-104">예제</span><span class="sxs-lookup"><span data-stu-id="090a2-104">Example</span></span>  
 <span data-ttu-id="090a2-105">다음 코드 예제에서는 격리된 저장소를 가져오고 저장소에 TestStore.txt라는 파일이 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="090a2-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="090a2-106">존재하지 않는 경우, 파일을 만들고 파일에 "Hello Isolated Storage"를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="090a2-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="090a2-107">TestStore.txt가 이미 있으면 예제 코드에서는 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="090a2-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="090a2-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="090a2-108">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [<span data-ttu-id="090a2-109">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="090a2-109">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="090a2-110">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="090a2-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

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
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>방법: 격리된 저장소의 파일 읽기 및 쓰기
격리된 저장소에서 파일을 읽고 쓰기 위해, 스트림 판독기(<xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> 개체)를 가진 <xref:System.IO.StreamReader> 개체 또는 스트림 작성기(<xref:System.IO.StreamWriter> 개체)를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 격리된 저장소를 가져오고 저장소에 TestStore.txt라는 파일이 있는지 여부를 확인합니다. 존재하지 않는 경우, 파일을 만들고 파일에 "Hello Isolated Storage"를 씁니다. TestStore.txt가 이미 있으면 예제 코드에서는 파일을 읽습니다.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)  
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)

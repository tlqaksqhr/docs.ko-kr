---
title: "방법: 격리된 저장소의 파일 및 디렉터리 삭제"
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
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>방법: 격리된 저장소의 파일 및 디렉터리 삭제
격리 된 저장소 파일 내에서 파일과 디렉터리를 삭제할 수 있습니다. 저장소 내에서 파일 및 디렉터리 이름은 운영 체제에 종속적이며 가상 파일 시스템의 루트와 관련하여 지정됩니다. Windows 운영 체제에서는 대/소문자를 구분하지 않습니다.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> 클래스는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>이라는 두 가지 메서드를 제공하여 디렉터리와 파일을 삭제합니다. 존재하지 않는 파일 또는 디렉터리를 삭제하려고 하면 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw됩니다. 이름에 와일드 카드 문자를 포함하는 경우 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>는 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외를 throw하고, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>은 <xref:System.ArgumentException> 예외를 throw합니다.  
  
 디렉터리에 파일 또는 하위 디렉터리가 포함된 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 메서드가 실패합니다. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> 메서드를 사용하여 기존 파일 및 디렉터리를 검색할 수 있습니다. 저장소의 가상 파일 시스템을 검색 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 격리 된 저장소의 기존 파일 찾기 및 디렉터리](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 만들고 몇 개의 디렉터리와 파일을 삭제 합니다.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [격리된 저장소](../../../docs/standard/io/isolated-storage.md)

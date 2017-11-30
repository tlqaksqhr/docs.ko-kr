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
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="963b5-102">방법: 격리된 저장소의 파일 및 디렉터리 삭제</span><span class="sxs-lookup"><span data-stu-id="963b5-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="963b5-103">격리 된 저장소 파일 내에서 파일과 디렉터리를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="963b5-104">저장소 내에서 파일 및 디렉터리 이름은 운영 체제에 종속적이며 가상 파일 시스템의 루트와 관련하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="963b5-105">Windows 운영 체제에서는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="963b5-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> 클래스는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>이라는 두 가지 메서드를 제공하여 디렉터리와 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="963b5-107">존재하지 않는 파일 또는 디렉터리를 삭제하려고 하면 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="963b5-108">이름에 와일드 카드 문자를 포함하는 경우 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>는 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외를 throw하고, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>은 <xref:System.ArgumentException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="963b5-109">디렉터리에 파일 또는 하위 디렉터리가 포함된 경우에는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> 메서드가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="963b5-110"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 및 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> 메서드를 사용하여 기존 파일 및 디렉터리를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="963b5-111">저장소의 가상 파일 시스템을 검색 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 격리 된 저장소의 기존 파일 찾기 및 디렉터리](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="963b5-112">예제</span><span class="sxs-lookup"><span data-stu-id="963b5-112">Example</span></span>  
 <span data-ttu-id="963b5-113">다음 코드 예제를 만들고 몇 개의 디렉터리와 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="963b5-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="963b5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="963b5-114">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [<span data-ttu-id="963b5-115">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="963b5-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

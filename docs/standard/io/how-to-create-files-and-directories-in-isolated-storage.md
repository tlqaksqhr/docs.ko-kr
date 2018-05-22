---
title: '방법: 격리된 저장소에 파일 및 디렉터리 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7fa96e4f28e92e0890acf6ffc105ca11a97d575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="248eb-102">방법: 격리된 저장소에 파일 및 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="248eb-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="248eb-103">격리된 저장소를 가져온 다음에는 데이터를 저장할 디렉터리와 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="248eb-104">저장소 내에서 파일 및 디렉터리 이름은 가상 파일 시스템의 루트와 관련하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="248eb-105">디렉터리를 만들려면 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> 인스턴스 메서드를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="248eb-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="248eb-106">존재하지 않는 디렉터리의 하위 디렉터리를 지정하면 두 디렉터리가 모두 만들어지고</span><span class="sxs-lookup"><span data-stu-id="248eb-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="248eb-107">이미 존재하는 디렉터리를 지정하면 메서드가 디렉터리를 만들지 않은 채 반환되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="248eb-108">그러나 잘못된 문자를 포함하는 디렉터리 이름을 지정하면 <xref:System.IO.IsolatedStorage.IsolatedStorageException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="248eb-109">파일을 만들려면 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="248eb-110">Windows 운영 체제에서 격리된 저장소 파일 및 디렉터리 이름은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="248eb-111">즉, `ThisFile.txt`라는 파일을 만든 다음 `THISFILE.TXT`라는 다른 파일을 만들면 한 파일만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="248eb-112">파일 이름은 표시를 위해 원래 대소문자를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="248eb-113">예</span><span class="sxs-lookup"><span data-stu-id="248eb-113">Example</span></span>  
 <span data-ttu-id="248eb-114">다음 코드 예제는 분리된 저장소에서 파일 및 디렉터리를 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="248eb-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="248eb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="248eb-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="248eb-116">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="248eb-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

---
title: '방법: 격리된 저장소의 기존 파일 및 디렉터리 찾기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 866be7970c43051dd7e2bf8d45ae779aca130a45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a><span data-ttu-id="25944-102">방법: 격리된 저장소의 기존 파일 및 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="25944-102">How to: Find Existing Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="25944-103">격리된 저장소에서 디렉터리를 검색하려면 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-103">To search for a directory in isolated storage, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="25944-104">이 메서드는 검색 패턴을 나타내는 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-104">This method takes a string that represents a search pattern.</span></span> <span data-ttu-id="25944-105">검색 패턴에서 단일 문자(?) 및 여러 문자(\*) 와일드카드 문자를 모두 사용할 수 있지만, 와일드카드 문자는 이름의 마지막 부분에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-105">You can use both single-character (?) and multi-character (\*) wildcard characters in the search pattern, but the wildcard characters must appear in the final portion of the name.</span></span> <span data-ttu-id="25944-106">예를 들어, `directory1/*ect*`는 올바른 검색 문자열이지만 `*ect*/directory2`는 잘못된 검색 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25944-106">For example, `directory1/*ect*` is a valid search string, but `*ect*/directory2` is not.</span></span>  
  
 <span data-ttu-id="25944-107">파일을 검색하려면 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-107">To search for a file, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="25944-108"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>에 적용되는 검색 문자열의 와일드카드 문자 제한 사항이 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>에도 똑같이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25944-108">The restriction for wildcard characters in search strings that applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> also applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span></span>  
  
 <span data-ttu-id="25944-109">이러한 메서드는 둘 다 재귀적입니다. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 클래스는 저장소의 모든 디렉터리 또는 파일을 열거하는 메서드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25944-109">Neither of these methods is recursive; the <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class does not supply any methods for listing all directories or files in your store.</span></span> <span data-ttu-id="25944-110">그러나 다음 코드 예제에서 재귀 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25944-110">However, recursive methods are shown in the following code example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25944-111">예</span><span class="sxs-lookup"><span data-stu-id="25944-111">Example</span></span>  
 <span data-ttu-id="25944-112">다음 코드 예제는 분리된 저장소에서 파일 및 디렉터리를 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="25944-112">The following code example illustrates how to create files and directories in an isolated store.</span></span> <span data-ttu-id="25944-113">먼저 사용자, 도메인 및 어셈블리별로 격리된 저장소를 검색하여 `isoStore` 변수에 대입합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-113">First, a store that is isolated for user, domain, and assembly is retrieved and placed in the `isoStore` variable.</span></span> <span data-ttu-id="25944-114"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> 메서드는 몇 개의 디렉터리를 설정하는 데 사용되고 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> 생성자는 이러한 디렉터리에 몇 개의 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25944-114">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> method is used to set up a few different directories, and the <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor creates some files in these directories.</span></span> <span data-ttu-id="25944-115">그런 다음 코드는 `GetAllDirectories` 메서드의 결과를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-115">The code then loops through the results of the `GetAllDirectories` method.</span></span> <span data-ttu-id="25944-116">이 메서드는 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>를 사용하여 현재 디렉터리에서 모든 디렉터리 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="25944-116">This method uses <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> to find all the directory names in the current directory.</span></span> <span data-ttu-id="25944-117">이러한 이름이 배열로 저장된 다음 `GetAllDirectories`는 찾은 각 디렉터리를 전달하기 위해 자신을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-117">These names are stored in an array, and then `GetAllDirectories` calls itself, passing in each directory it has found.</span></span> <span data-ttu-id="25944-118">결과적으로, 모든 디렉터리 이름은 배열에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="25944-118">As a result, all the directory names are returned in an array.</span></span> <span data-ttu-id="25944-119">다음으로 코드는 `GetAllFiles` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-119">Next, the code calls the `GetAllFiles` method.</span></span> <span data-ttu-id="25944-120">이 메서드는 `GetAllDirectories`를 호출하여 모든 디렉터리의 이름을 확인한 다음 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> 메서드를 사용하여 각 디렉터리를 검사하여 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="25944-120">This method calls `GetAllDirectories` to find out the names of all the directories, and then it checks each directory for files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> method.</span></span> <span data-ttu-id="25944-121">결과는 표시를 위해 배열로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="25944-121">The result is returned in an array for display.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="25944-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25944-122">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="25944-123">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="25944-123">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)

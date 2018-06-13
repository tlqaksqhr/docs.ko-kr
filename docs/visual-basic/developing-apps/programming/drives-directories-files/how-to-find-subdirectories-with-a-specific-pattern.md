---
title: '방법: Visual Basic에서 특정 패턴의 하위 디렉터리 찾기'
ms.date: 07/20/2015
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
ms.openlocfilehash: b3c80fccea06a48c78f37dc7d1c8dcc88e143de4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586440"
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="78393-102">방법: Visual Basic에서 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="78393-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="78393-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> 메서드는 디렉터리에 있는 하위 디렉터리의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78393-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="78393-104">`wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78393-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="78393-105">하위 디렉터리의 내용을 검색에 포함하려면 `searchType` 매개 변수를 `SearchOption.SearchAllSubDirectories`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78393-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="78393-106">지정한 패턴과 일치하는 디렉터리가 없으면 빈 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="78393-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="78393-107">특정 패턴의 하위 디렉터리를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="78393-107">To find subdirectories with a specific pattern</span></span>  
  
-   <span data-ttu-id="78393-108">검색하려는 디렉터리의 이름 및 경로를 제공하여 `GetDirectories` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78393-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="78393-109">다음 예제에서는 디렉터리 구조에서 이름에 "Logs" 단어가 포함된 모든 디렉터리를 반환하고 `ListBox1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78393-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="78393-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="78393-110">Robust Programming</span></span>  
 <span data-ttu-id="78393-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78393-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="78393-112">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="78393-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="78393-113">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="78393-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="78393-114">지정된 와일드카드 문자 중 하나 이상이 `Nothing` 또는 빈 문자열이거나 공백으로만 구성된 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="78393-114">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="78393-115">`directory`가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="78393-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="78393-116">`directory`가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="78393-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="78393-117">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="78393-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="78393-118">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="78393-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="78393-119">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="78393-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="78393-120">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="78393-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78393-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78393-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>  
 [<span data-ttu-id="78393-122">방법: 특정 패턴의 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="78393-122">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)

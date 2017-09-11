---
title: "방법: Visual Basic에서 특정 패턴의 하위 디렉터리 찾기"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3719c13c74b873927382d2ff3ca733e3fd8fe945
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="aa246-102">방법: Visual Basic에서 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="aa246-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="aa246-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> 메서드는 디렉터리에 있는 하위 디렉터리의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="aa246-104">`wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="aa246-105">하위 디렉터리의 내용을 검색에 포함하려면 `searchType` 매개 변수를 `SearchOption.SearchAllSubDirectories`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="aa246-106">지정한 패턴과 일치하는 디렉터리가 없으면 빈 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="aa246-107">특정 패턴의 하위 디렉터리를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="aa246-107">To find subdirectories with a specific pattern</span></span>  
  
-   <span data-ttu-id="aa246-108">검색하려는 디렉터리의 이름 및 경로를 제공하여 `GetDirectories` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="aa246-109">다음 예제에서는 디렉터리 구조에서 이름에 "Logs" 단어가 포함된 모든 디렉터리를 반환하고 `ListBox1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>  
  
     <span data-ttu-id="aa246-110">[!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="aa246-110">[!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-subdirectories-with-a-specific-pattern_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="aa246-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="aa246-111">Robust Programming</span></span>  
 <span data-ttu-id="aa246-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aa246-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="aa246-113">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="aa246-114">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="aa246-115">지정된 와일드카드 문자 중 하나 이상이 `Nothing` 또는 빈 문자열이거나 공백으로만 구성된 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-115">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="aa246-116">`directory`가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-116">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="aa246-117">`directory`가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-117">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="aa246-118">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="aa246-119">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="aa246-120">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-120">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="aa246-121">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="aa246-121">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa246-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa246-122">See Also</span></span>  
 <span data-ttu-id="aa246-123"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A></span><span class="sxs-lookup"><span data-stu-id="aa246-123"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A></span></span>   
 [<span data-ttu-id="aa246-124">방법: 특정 패턴의 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="aa246-124">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)


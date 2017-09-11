---
title: "방법: Visual Basic에서 파일 경로의 구문 분석"
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
- file names, parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6327d661c6f1fe7647cc64b56d7f72f1f3455467
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="818f6-102">방법: Visual Basic에서 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="818f6-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="818f6-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem> 개체는 파일 경로를 구문 분석할 때 유용한 메서드 여러 개를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
-   <span data-ttu-id="818f6-104"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> 메서드는 두 개의 경로를 가져와서 적절한 형식으로 조합된 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
-   <span data-ttu-id="818f6-105"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> 메서드는 제공된 경로의 상위에 대한 절대 경로를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
-   <span data-ttu-id="818f6-106"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 메서드는 <xref:System.IO.FileInfo> 개체를 반환합니다. 이 개체를 쿼리하여 파일의 이름 및 경로 등과 같은 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="818f6-107">파일 이름 확장명에 근거하여 파일 내용을 판단하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="818f6-108">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="818f6-109">파일의 이름 및 경로를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="818f6-109">To determine a file's name and path</span></span>  
  
-   <span data-ttu-id="818f6-110"><xref:System.IO.FileInfo.DirectoryName%2A> 개체의 <xref:System.IO.FileInfo.Name%2A> 및 <xref:System.IO.FileInfo> 속성을 사용하여 파일의 이름과 경로를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="818f6-111">이 예제에서는 이름과 경로를 확인하고 이를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-111">This example determines the name and path and displays them.</span></span>  
  
     <span data-ttu-id="818f6-112">[!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="818f6-112">[!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]</span></span>  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="818f6-113">파일의 이름과 디렉터리를 결합하여 전체 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="818f6-113">To combine a file's name and directory to create the full path</span></span>  
  
-   <span data-ttu-id="818f6-114">디렉터리와 이름을 제공하여 `CombinePath` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-114">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="818f6-115">이 예제에서는 이전 예제에서 만들어진 문자열 `folderPath` 와 `fileName` 을 가져와서 이를 결합한 다음 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="818f6-115">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     <span data-ttu-id="818f6-116">[!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="818f6-116">[!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818f6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="818f6-117">See Also</span></span>  
 <span data-ttu-id="818f6-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="818f6-118"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="818f6-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A></span><span class="sxs-lookup"><span data-stu-id="818f6-119"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A></span></span>   
 <span data-ttu-id="818f6-120"><xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="818f6-120"><xref:System.IO.FileInfo></span></span>   
 <span data-ttu-id="818f6-121"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A></span><span class="sxs-lookup"><span data-stu-id="818f6-121"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A></span></span>   
 [<span data-ttu-id="818f6-122">방법: 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="818f6-122">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)


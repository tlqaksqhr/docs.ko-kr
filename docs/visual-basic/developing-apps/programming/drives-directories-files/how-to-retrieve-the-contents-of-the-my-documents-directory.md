---
title: "방법: Visual Basic에서 내 문서 디렉터리의 내용 검색"
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
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
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
ms.openlocfilehash: afe236c4b9245ac256fbcbf6bf453de5d706b80f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="a8c74-102">방법: Visual Basic에서 내 문서 디렉터리의 내용 검색</span><span class="sxs-lookup"><span data-stu-id="a8c74-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="a8c74-103"><xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> 개체를 사용하여 **내 문서**, **바탕 화면** 등의 많은 **모든 사용자** 디렉터리에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c74-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="a8c74-104">내 문서 폴더에서 읽으려면</span><span class="sxs-lookup"><span data-stu-id="a8c74-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="a8c74-105">`ReadAllText` 메서드를 사용하여 특정 디렉터리에 있는 각 파일에서 텍스트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a8c74-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="a8c74-106">다음 코드에서는 디렉터리와 파일을 지정한 다음 `ReadAllText`를 사용하여 `patients`라는 문자열로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8c74-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     <span data-ttu-id="a8c74-107">[!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8c74-107">[!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c74-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8c74-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>


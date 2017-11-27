---
title: "인코딩은 Nothing으로 설정할 수 없음"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa3567e47f170c64b45cbb9e49d7fa0026b8903
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="46c92-102">인코딩은 Nothing으로 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="46c92-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="46c92-103">`encoding` 매개 변수가 `Nothing` 으로 설정되었지만 유효한 값이 필요하기 때문에 파일에서 읽거나 쓰려는 시도가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="46c92-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="46c92-104"><xref:System.Text.Encoding> 은 파일에 쓸 때 사용할 인코딩을 결정하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46c92-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="46c92-105">기본값은 UTF-8입니다.</span><span class="sxs-lookup"><span data-stu-id="46c92-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46c92-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="46c92-106">To correct this error</span></span>  
  
-   <span data-ttu-id="46c92-107">`encoding` 매개 변수에 대한 유효한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46c92-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c92-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46c92-108">See Also</span></span>  
 [<span data-ttu-id="46c92-109">파일 인코딩</span><span class="sxs-lookup"><span data-stu-id="46c92-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [<span data-ttu-id="46c92-110">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="46c92-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="46c92-111">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="46c92-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [<span data-ttu-id="46c92-112">My.Computer.FileSystem.ReadAllText 메서드</span><span class="sxs-lookup"><span data-stu-id="46c92-112">My.Computer.FileSystem.ReadAllText Method</span></span>](http://msdn.microsoft.com/en-us/3a7ac8be-fb1d-4087-bc65-167d6754d57f)  
 [<span data-ttu-id="46c92-113">My.Computer.FileSystem.WriteAllText 메서드</span><span class="sxs-lookup"><span data-stu-id="46c92-113">My.Computer.FileSystem.WriteAllText Method</span></span>](http://msdn.microsoft.com/en-us/f507460c-87d9-4504-b74f-3ff825c7d5c4)

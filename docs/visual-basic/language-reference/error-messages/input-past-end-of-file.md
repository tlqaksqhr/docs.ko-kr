---
title: 입력(값)이 파일의 끝을 넘습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="5219f-102">입력(값)이 파일의 끝을 넘습니다.</span><span class="sxs-lookup"><span data-stu-id="5219f-102">Input past end of file</span></span>
<span data-ttu-id="5219f-103">중 하나는 `Input` 문에서 비어 있는 파일 또는 모든 데이터를 사용 하거나 사용에서 읽고는 `EOF` 파일 함수 이진 액세스를 위해 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="5219f-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5219f-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5219f-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="5219f-105">사용 하 여는 `EOF` 직전 함수는 `Input` 문을 파일의 끝을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5219f-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="5219f-106">이진 액세스에 대 한 파일을 열면를 사용 하 여 `Seek` 및 `Loc`합니다.</span><span class="sxs-lookup"><span data-stu-id="5219f-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5219f-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5219f-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>

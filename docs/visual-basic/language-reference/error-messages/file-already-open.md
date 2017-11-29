---
title: "파일이 이미 열려 있습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="4b6e0-102">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6e0-102">File already open</span></span>
<span data-ttu-id="4b6e0-103">경우에 따라 파일을 닫아야 다른 것 보다 먼저 `FileOpen` 또는 기타 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6e0-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="4b6e0-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="4b6e0-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="4b6e0-105">순차적 출력 모드 `FileOpen` 이미 열려 있는 파일에 대 한 작업을 실행 했습니다</span><span class="sxs-lookup"><span data-stu-id="4b6e0-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="4b6e0-106">문에서 열려 있는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b6e0-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b6e0-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4b6e0-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="4b6e0-108">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4b6e0-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6e0-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b6e0-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

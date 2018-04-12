---
title: 사용 권한이 거부되었습니다(Visual Basic).
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5d7965ebd42cb3e56d66966d035be9ba3d3957c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="a2eaa-102">사용 권한이 거부되었습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a2eaa-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="a2eaa-103">쓰기 금지 되어 디스크에 쓸 수 또는 잠긴된 파일에 액세스 하도록 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eaa-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2eaa-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a2eaa-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="a2eaa-105">쓰기 가능한 파일을 열려면 파일의 쓰기 금지 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eaa-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="a2eaa-106">다른 프로세스에서 파일을 잠 궜 하지 있는지 확인 하 고 다른 프로세스에서 해제 될 때까지 파일을 열 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a2eaa-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="a2eaa-107">레지스트리를 액세스 하려면 사용자 권한을 레지스트리 액세스의이 유형이 포함 되어 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eaa-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2eaa-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2eaa-108">See Also</span></span>  
 [<span data-ttu-id="a2eaa-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="a2eaa-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)

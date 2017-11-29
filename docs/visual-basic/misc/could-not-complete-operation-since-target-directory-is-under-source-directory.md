---
title: "대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 429d679157d25655ca73afef14ecd642f7cac37f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="5e13a-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e13a-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="5e13a-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e13a-103">A cyclic operation has failed.</span></span> <span data-ttu-id="5e13a-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e13a-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="5e13a-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e13a-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e13a-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5e13a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5e13a-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e13a-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e13a-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e13a-108">See Also</span></span>  
 [<span data-ttu-id="5e13a-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="5e13a-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="5e13a-110">디버깅 기본 사항: 중단점</span><span class="sxs-lookup"><span data-stu-id="5e13a-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

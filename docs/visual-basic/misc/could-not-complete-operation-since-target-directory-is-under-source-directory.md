---
title: 대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 68217023a980891200c18b5536ef902574d36257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638514"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="16849-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16849-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="16849-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="16849-103">A cyclic operation has failed.</span></span> <span data-ttu-id="16849-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16849-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="16849-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="16849-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16849-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="16849-106">To correct this error</span></span>  
  
-   <span data-ttu-id="16849-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16849-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16849-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16849-108">See Also</span></span>  
 [<span data-ttu-id="16849-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="16849-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="16849-110">디버깅 기본 사항: 중단점</span><span class="sxs-lookup"><span data-stu-id="16849-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

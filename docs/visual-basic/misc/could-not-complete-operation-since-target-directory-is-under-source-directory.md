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
ms.openlocfilehash: 0a17877b2335ee010a97f0b522bd4c399867cd7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="f2796-102">대상 디렉터리가 소스 디렉터리 아래에 있기 때문에 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2796-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="f2796-103">순환 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2796-103">A cyclic operation has failed.</span></span> <span data-ttu-id="f2796-104">순환 작업이 계속 실행되므로 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2796-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="f2796-105">예를 들어 개체 A는 개체 B에서 상속하려고 하고 개체 B는 개체 A에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2796-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2796-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f2796-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f2796-107">상속 시 순환 참조가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2796-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2796-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2796-108">See Also</span></span>  
 [<span data-ttu-id="f2796-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="f2796-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="f2796-110">디버깅 기본 사항: 중단점</span><span class="sxs-lookup"><span data-stu-id="f2796-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

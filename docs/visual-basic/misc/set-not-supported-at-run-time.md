---
title: Set은 런타임에 지원되지 않습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c10691abf13ea00cc4eaea961b5ca6fd59a2be8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="1bd38-102">Set은 런타임에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd38-102">Set not supported at run time</span></span>
<span data-ttu-id="1bd38-103">디자인 타임에만 값을 설정할 수 있는 속성을 설정하거나 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd38-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1bd38-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1bd38-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="1bd38-105">사용자 코드에서 속성에 대한 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd38-105">Remove the reference to the property from your code.</span></span>  
  
2.  <span data-ttu-id="1bd38-106">런타임에만 속성의 값을 반환하도록 참조를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd38-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd38-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bd38-107">See Also</span></span>  
 [<span data-ttu-id="1bd38-108">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="1bd38-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

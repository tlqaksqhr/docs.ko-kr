---
title: '&#39;Dir&#39; 함수는 처음으로 호출 된 &#39;PathName&#39; 인수'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585462"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="98e2d-102">&#39;Dir&#39; 함수는 처음으로 호출 된 &#39;PathName&#39; 인수</span><span class="sxs-lookup"><span data-stu-id="98e2d-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="98e2d-103">에 대 한 초기 호출에서 `Dir` 함수 포함 되지 않습니다는 `PathName` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="98e2d-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="98e2d-104">첫 번째 호출 `Dir` 포함 되어야 합니다는 `PathName`, 하지만 후속 호출을 `Dir` 다음 항목을 검색 하는 매개 변수를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98e2d-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98e2d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="98e2d-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="98e2d-106">제공 된 `PathName` 함수 호출의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="98e2d-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e2d-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98e2d-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

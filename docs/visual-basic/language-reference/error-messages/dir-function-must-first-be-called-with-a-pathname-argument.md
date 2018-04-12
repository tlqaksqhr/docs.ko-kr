---
title: '&#39; Dir &#39; 함수는 처음으로 호출는 &#39; 경로 이름 &#39; 인수'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="9cdfc-102">&#39; Dir &#39; 함수는 처음으로 호출는 &#39; 경로 이름 &#39; 인수</span><span class="sxs-lookup"><span data-stu-id="9cdfc-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="9cdfc-103">에 대 한 초기 호출에서 `Dir` 함수 포함 되지 않습니다는 `PathName` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="9cdfc-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="9cdfc-104">첫 번째 호출 `Dir` 포함 되어야 합니다는 `PathName`, 하지만 후속 호출을 `Dir` 다음 항목을 검색 하는 매개 변수를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cdfc-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9cdfc-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9cdfc-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="9cdfc-106">제공 된 `PathName` 함수 호출의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="9cdfc-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cdfc-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cdfc-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

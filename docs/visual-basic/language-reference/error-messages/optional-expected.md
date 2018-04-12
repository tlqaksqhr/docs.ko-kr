---
title: '&#39; 선택 사항 &#39; 필요합니다.'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e84371935fdd2d558e6828c05fa952b9cc4cf4f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="39optional39-expected"></a><span data-ttu-id="21f10-102">&#39; 선택 사항 &#39; 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21f10-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="21f10-103">프로시저 선언에서 선택적 인수는 필수 인수에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="21f10-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="21f10-104">모든 인수는 선택적 인수 뒤에 선택적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f10-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="21f10-105">**오류 ID:** BC30202</span><span class="sxs-lookup"><span data-stu-id="21f10-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="21f10-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="21f10-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="21f10-107">인수가 필요할 수 하려는 경우에 인수 목록에 첫 번째 선택적 인수를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f10-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="21f10-108">선택적 인수는 의도 한 경우 사용 하 여는 `Optional` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="21f10-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f10-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21f10-109">See Also</span></span>  
 [<span data-ttu-id="21f10-110">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="21f10-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)

---
title: "오버플로가 발생했습니다(Visual Basic 런타임 오류)."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="4c972-102">오버플로가 발생했습니다(Visual Basic 런타임 오류).</span><span class="sxs-lookup"><span data-stu-id="4c972-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="4c972-103">할당 대상의 한계를 초과 하 여 할당 하려고 할 때 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4c972-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c972-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4c972-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4c972-105">결과가 너무 커서 변수 값의 해당 형식에 대 한 범위에서 나타낼 수 없는 변환과 형식 변수에 값 할당 할당, 계산 및 데이터 형식 값의 더 큰 범위를 수용할 수 있는지 확인 필요한 경우.</span><span class="sxs-lookup"><span data-stu-id="4c972-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="4c972-106">속성에 할당 맞게 수행 되는 속성의 범위에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c972-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="4c972-107">정수도 강제 변환 하는 계산에 사용 되는 번호 정수 보다 큰 결과 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c972-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c972-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c972-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="4c972-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4c972-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="4c972-110">오류 형식</span><span class="sxs-lookup"><span data-stu-id="4c972-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)

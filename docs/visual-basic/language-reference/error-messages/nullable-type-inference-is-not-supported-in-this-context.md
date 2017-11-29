---
title: "이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords: BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a><span data-ttu-id="58bba-102">이 컨텍스트에서는 nullable 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58bba-102">Nullable type inference is not supported in this context</span></span>
<span data-ttu-id="58bba-103">값 형식 및 구조는 null을 허용 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58bba-103">Value types and structures can be declared nullable.</span></span>  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 <span data-ttu-id="58bba-104">그러나 nullable 선언 형식 유추와 함께에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58bba-104">However, you cannot use the nullable declaration in combination with type inference.</span></span> <span data-ttu-id="58bba-105">다음 예에서는이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="58bba-105">The following examples cause this error.</span></span>  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 <span data-ttu-id="58bba-106">**오류 ID:** BC36629</span><span class="sxs-lookup"><span data-stu-id="58bba-106">**Error ID:** BC36629</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58bba-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="58bba-107">To correct this error</span></span>  
  
-   <span data-ttu-id="58bba-108">사용 하 여 프로그램 `As` 절 null 허용으로 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bba-108">Use an `As` clause to declare the variable as nullable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bba-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58bba-109">See Also</span></span>  
 [<span data-ttu-id="58bba-110">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="58bba-110">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="58bba-111">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="58bba-111">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

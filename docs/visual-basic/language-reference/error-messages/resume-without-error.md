---
title: 오류 없이 계속됩니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a><span data-ttu-id="03f2e-102">오류 없이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="03f2e-102">Resume without error</span></span>
<span data-ttu-id="03f2e-103">A `Resume` 문의 오류 처리 코드 외부에 있거나 오류가 있습니다. 경우에 오류 처리기로 코드 점프 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f2e-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03f2e-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="03f2e-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="03f2e-105">이동의 `Resume` 오류 처리기로 문의 하거나, 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f2e-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="03f2e-106">프로시저에 대 한 오류 처리기를 식별 하는 레이블 검색 레이블로 이동할 때 프로시저를 통해 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03f2e-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="03f2e-107">대상으로 지정 된 중복 레이블과 경우는 `GoTo` 문이 아닌는 `On Error GoTo` 문, 원하는 대상에 대 한 동의를 줄 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f2e-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f2e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03f2e-108">See Also</span></span>  
 [<span data-ttu-id="03f2e-109">Resume 문</span><span class="sxs-lookup"><span data-stu-id="03f2e-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="03f2e-110">On Error 문</span><span class="sxs-lookup"><span data-stu-id="03f2e-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)

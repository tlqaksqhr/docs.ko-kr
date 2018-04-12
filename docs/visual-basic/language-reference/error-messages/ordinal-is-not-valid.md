---
title: 서수가 잘못되었습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="a471e-102">서수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-102">Ordinal is not valid</span></span>
<span data-ttu-id="a471e-103">프로시저 이름 대신 숫자를 사용 하는 동적 연결 라이브러리 (DLL)를 호출 하 여 표시를 사용 하는 `#num` 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="a471e-104">이 오류는 다음과 같은 가능한 원인을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="a471e-105">변환할 수는 `#num` 식 실패 하는 서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="a471e-106">`#num` 지정 된 DLL의 함수를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="a471e-107">형식 라이브러리에 잘못 된 서 수의 내부 사용에 잘못 된 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a471e-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a471e-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a471e-109">식이 올바른 숫자를 나타내는 있는지 확인 하거나 이름별으로 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="a471e-110">확인 `#num` DLL의 올바른 함수를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="a471e-111">코드를 주석 처리 문제를 발생 시키는 프로시저 호출을 격리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="a471e-112">작성 한 `Declare` 프로시저와 보고서 문제를 형식 라이브러리 공급 업체에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a471e-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a471e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a471e-113">See Also</span></span>  
 [<span data-ttu-id="a471e-114">Declare 문</span><span class="sxs-lookup"><span data-stu-id="a471e-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

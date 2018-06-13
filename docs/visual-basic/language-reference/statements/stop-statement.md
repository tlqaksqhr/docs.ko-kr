---
title: Stop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599137"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="19929-102">Stop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19929-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="19929-103">실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="19929-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19929-104">구문</span><span class="sxs-lookup"><span data-stu-id="19929-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="19929-105">설명</span><span class="sxs-lookup"><span data-stu-id="19929-105">Remarks</span></span>  
 <span data-ttu-id="19929-106">배치할 수 `Stop` 실행이 일시 중단 하는 절차에는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="19929-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="19929-107">사용 하 여 `Stop` 문이 코드에 중단점을 설정 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="19929-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="19929-108">`Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에서 발생 하지 않는 모든 변수를 선택 취소 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19929-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19929-109">경우는 `Stop` (IDE) 통합된 개발 환경 외부에서 실행 되는 코드에서 문이 실행 될, 디버거가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19929-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="19929-110">이 일반 정품 또는 디버그 모드에서 컴파일된 코드 여부에 관계 없이 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="19929-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19929-111">예제</span><span class="sxs-lookup"><span data-stu-id="19929-111">Example</span></span>  
 <span data-ttu-id="19929-112">사용 하 여이 예제는 `Stop` 문을 통해 반복 실행을 일시 중지는 `For...Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="19929-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="19929-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19929-113">See Also</span></span>  
 [<span data-ttu-id="19929-114">End 문</span><span class="sxs-lookup"><span data-stu-id="19929-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)

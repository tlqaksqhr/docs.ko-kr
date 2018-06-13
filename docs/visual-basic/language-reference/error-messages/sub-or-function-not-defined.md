---
title: Sub 또는 Function이 정의되지 않았습니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 58e90d769d5a7f2d88b5c27d1ec7d0d28c8d7b03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593703"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="20a14-102">Sub 또는 Function이 정의되지 않았습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="20a14-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="20a14-103">A `Sub` 또는 `Function` 호출 되려면 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="20a14-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="20a14-105">프로시저 이름의 철자가 틀린 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="20a14-106">다른 프로젝트에서 명시적으로 해당 프로젝트에 대 한 참조를 추가 하지 않고 프로시저를 호출 하는 **참조** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="20a14-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="20a14-107">호출 하는 프로시저로 표시 되지 않는 프로시저를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="20a14-108">Windows 동적 연결 라이브러리 (DLL) 루틴 또는 지정된 된 라이브러리 또는 코드 리소스에 있지 않은 Macintosh 코드 리소스 루틴을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="20a14-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="20a14-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="20a14-110">프로시저 이름을 제대로 입력 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="20a14-111">호출 하려는 프로시저를 포함 하는 프로젝트의 이름 찾기는 **참조** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="20a14-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="20a14-112">표시 되지 않으면 클릭는 **찾아보기** 단추를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="20a14-113">프로젝트 이름의 왼쪽에 있는 확인란을 선택 하 고 클릭 한 다음 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="20a14-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="20a14-114">루틴의 이름을 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="20a14-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a14-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20a14-115">See Also</span></span>  
 [<span data-ttu-id="20a14-116">오류 형식</span><span class="sxs-lookup"><span data-stu-id="20a14-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="20a14-117">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="20a14-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="20a14-118">Sub 문</span><span class="sxs-lookup"><span data-stu-id="20a14-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="20a14-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="20a14-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

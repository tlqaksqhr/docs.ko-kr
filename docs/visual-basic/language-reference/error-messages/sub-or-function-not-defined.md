---
title: "Sub 또는 Function이 정의 되어 있지 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 837beec039e1fb8f8a796b2781d93de6d4cfb33a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="47bad-102">Sub 또는 Function이 정의되지 않았습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="47bad-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="47bad-103">A `Sub` 또는 `Function` 호출 하기 위해 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="47bad-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="47bad-105">프로시저 이름 철자가 틀린 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="47bad-106">해당 프로젝트에 대 한 참조를 명시적으로 추가 하지 않고 다른 프로젝트에서 프로시저를 호출 하 려는 **참조** 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="47bad-107">호출 프로시저에 표시 되지 않는 프로시저를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="47bad-108">Windows 동적 연결 라이브러리 (DLL) 루틴 또는 지정된 된 라이브러리 또는 코드 리소스에 없는 Macintosh 코드 리소스 루틴을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47bad-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="47bad-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="47bad-110">프로시저 이름의 철자가 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="47bad-111">호출 하려는 프로시저를 포함 하는 프로젝트의 이름 찾기는 **참조** 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="47bad-112">표시 되지 않으면 클릭는 **찾아보기** 단추를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="47bad-113">프로젝트 이름 왼쪽에 있는 확인란을 선택 하 고 클릭 한 다음 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="47bad-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="47bad-114">루틴의 이름을 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="47bad-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bad-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47bad-115">See Also</span></span>  
 <span data-ttu-id="47bad-116">[오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="47bad-116">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="47bad-117"> [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="47bad-117"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="47bad-118"> [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="47bad-118"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="47bad-119"> [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)</span><span class="sxs-lookup"><span data-stu-id="47bad-119"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)</span></span>

---
title: "&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식 배열의 또는 배열 매개 변수 형식의 차수만 다른 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
dev_langs:
- VB
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
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
ms.openlocfilehash: d106f59e3faa317f67ee92ddcec8416eeff745d4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="a113b-102">&lt;proceduresignature1&gt; 는 오버 로드 하므로 CLS 규격이 아닙니다 &lt;proceduresignature2&gt; 에서 배열 매개 변수 형식 배열의 또는 배열 매개 변수 형식의 차수만 다른</span><span class="sxs-lookup"><span data-stu-id="a113b-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="a113b-103">프로시저 또는 속성으로 표시 되어 `<CLSCompliant(True)>` 때 다른 프로시저 또는 속성을 재정의 하 고 매개 변수 목록은 간의 유일한 차이점은 가변 배열의 중첩 수준 또는 배열의 차수입니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="a113b-104">두 번째 및 세 번째 선언 다음 선언에이 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="a113b-105">원래&1; 차원 매개 변수를 변경 하는 두 번째 선언 `arrayParam` 배열의 배열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="a113b-106">세 번째 선언 변경 내용 `arrayParam` 를 2 차원 배열 (순위 2).</span><span class="sxs-lookup"><span data-stu-id="a113b-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="a113b-107">Visual Basic만 달라 서는 이러한 변경 중 하나를 오버 로드를 허용 하는 동안 이러한 오버 로드와 호환 되지 않는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="a113b-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="a113b-108">적용 하는 경우는 <xref:System.CLSCompliantAttribute>특성의 프로그래밍 요소에 설정한 `isCompliant` 매개 변수를 `True` 또는 `False` 준수 여부를 나타냅니다.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="a113b-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a113b-109">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a113b-110">적용 되지 않은 경우는 <xref:System.CLSCompliantAttribute>요소에 비호환 상태로 간주 됩니다.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="a113b-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a113b-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-111">By default, this message is a warning.</span></span> <span data-ttu-id="a113b-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a113b-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a113b-113">**오류 ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="a113b-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a113b-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a113b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a113b-115">CLS 규격을 필요한 경우이 도움말 페이지에 언급 된 변경만 보다 많은 방법으로 서로 다를 오버 로드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a113b-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="a113b-116">오버 로드 다를 사용 해야 하는 경우이 도움말에 언급 된 변경만 하 여 페이지에서 제거 된 <xref:System.CLSCompliantAttribute>해당 정의에서 표시 하거나 `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="a113b-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a113b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a113b-117">See Also</span></span>  
 <span data-ttu-id="a113b-118">[\<통해 PAVE > CLS 규격 코드 작성](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span><span class="sxs-lookup"><span data-stu-id="a113b-118">[\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span></span>  
<span data-ttu-id="a113b-119"> [프로시저 오버 로드](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="a113b-119"> [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span></span>  
<span data-ttu-id="a113b-120"> [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="a113b-120"> [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>

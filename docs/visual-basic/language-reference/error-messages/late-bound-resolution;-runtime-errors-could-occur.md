---
title: 런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: af027b7752fdf13f1540010a8ddb681182c1b23c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588781"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="8304c-102">런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="8304c-103">개체도 선언 된 변수에 할당 되는 [Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="8304c-104">변수를 선언할 때 `Object`, 컴파일러에서 수행 해야 *런타임에 바인딩*, 런타임에 추가 작업이 필요 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="8304c-105">또한 응용 프로그램이 잠재적인 런타임 오류에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="8304c-106">예를 들어, 할당 하는 경우는 <xref:System.Windows.Forms.Form> 에 `Object` 변수에 액세스 하려고 하는 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> 속성, 런타임에서 throw 한 <xref:System.MemberAccessException> 때문에 <xref:System.Windows.Forms.Form> 클래스를 노출 하지 않습니다는 `NameTable` 속성.</span><span class="sxs-lookup"><span data-stu-id="8304c-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="8304c-107">특정 형식으로 변수를 선언 하면 컴파일러가 수행할 수 *초기 바인딩* 컴파일 타임에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="8304c-108">이 인해 성능 향상된, 특정 형식의 멤버 및 코드의 가독성을 높이기에 액세스를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="8304c-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-109">By default, this message is a warning.</span></span> <span data-ttu-id="8304c-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8304c-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="8304c-111">**오류 ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="8304c-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8304c-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8304c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="8304c-113">가능한 경우 특정 형식으로 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8304c-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8304c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8304c-114">See Also</span></span>  
 [<span data-ttu-id="8304c-115">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="8304c-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="8304c-116">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="8304c-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)

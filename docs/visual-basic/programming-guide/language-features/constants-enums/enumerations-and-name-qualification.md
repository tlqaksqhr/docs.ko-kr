---
title: 열거형 및 이름 한정(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: eb1f5653d968e81168833cd57813219e8f049b70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648582"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="cb0b0-102">열거형 및 이름 한정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb0b0-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="cb0b0-103">일반적으로 열거형의 멤버를 참조할 때 멤버 이름을 열거형 이름으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="cb0b0-104">예를 들어, 참조 하는 `Sunday` 소속 프로그램 `Days` 열거형에서 다음 구문을 사용:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="cb0b0-105">Imports 문 사용</span><span class="sxs-lookup"><span data-stu-id="cb0b0-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="cb0b0-106">추가 하 여 정규화 된 이름을 사용 하 여 방지할 수 있습니다는 `Imports` 문을 다음 예제와 같이 코드의 네임 스페이스 선언 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 <span data-ttu-id="cb0b0-107">`Imports` 문 내에서 또는 참조 된 프로젝트 및 어셈블리에서 네임 스페이스 이름을 가져옵니다 문이 표시 되는 모듈과 동일한 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="cb0b0-108">이 문이 추가 되 면 다음 예제와 같이 한정 하지 않고 열거형 멤버를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 <span data-ttu-id="cb0b0-109">열거형에 관련 된 상수 집합을 구성 하 여 다양 한 상황에서 상수 동일한 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="cb0b0-110">예를 들어에서 weekday 상수에 같은 이름을 사용할 수 있습니다는 `Days` 및 `WorkDays` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="cb0b0-111">사용 하는 경우는 `Imports` 열거형 문을 주의 해야 참조가 모호해 지지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="cb0b0-112">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 <span data-ttu-id="cb0b0-113">있다고 가정할 경우 `Monday` 둘 다의 구성원은 `Days` 열거형 및 `Workdays` 열거형이이 코드는 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="cb0b0-114">각 상수를 참조할 때 참조가 모호해 지지 않도록, 상수 이름을 해당 열거형으로 한정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="cb0b0-115">다음 코드를 참조 하는 `Saturday` 의 상수는 `Days` 및 `WorkDays` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cb0b0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb0b0-116">See Also</span></span>  
 [<span data-ttu-id="cb0b0-117">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="cb0b0-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="cb0b0-118">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="cb0b0-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="cb0b0-119">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="cb0b0-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="cb0b0-120">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="cb0b0-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="cb0b0-121">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="cb0b0-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="cb0b0-122">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="cb0b0-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="cb0b0-123">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cb0b0-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="cb0b0-124">Enum 문</span><span class="sxs-lookup"><span data-stu-id="cb0b0-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="cb0b0-125">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="cb0b0-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="cb0b0-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cb0b0-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)

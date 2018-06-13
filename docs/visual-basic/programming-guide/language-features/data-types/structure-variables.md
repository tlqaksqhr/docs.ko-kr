---
title: 구조체 변수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 0dad7bdcac5428753e252f3b26ca0a127c293a7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648501"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="2da5e-102">구조체 변수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da5e-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="2da5e-103">구조를 만든 후에 해당 형식으로 프로시저 수준 및 모듈 수준 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="2da5e-104">예를 들어 컴퓨터 시스템에 대 한 정보를 기록 하는 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="2da5e-105">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="2da5e-106">해당 형식의 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-106">You can now declare variables of that type.</span></span> <span data-ttu-id="2da5e-107">다음 선언은이입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="2da5e-108">클래스와 모듈에서 선언 된 구조체를 사용 하 여 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="2da5e-109">구조체를 전용으로 지정 하려는 경우 사용 하 여 선언 있는지 확인은 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="2da5e-110">구조 값에 대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="2da5e-110">Access to Structure Values</span></span>  
 <span data-ttu-id="2da5e-111">지정 하 고 구조체 변수의 요소에서 값을 검색을 설정 하 고 개체에서 속성을 사용 하 여 동일한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="2da5e-112">멤버 액세스 연산자를 배치 (`.`) 구조 변수 이름 사이 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="2da5e-113">다음 예제에서는 액세스 요소 형식으로 이전에 선언 된 변수의 `systemInfo`합니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="2da5e-114">구조체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="2da5e-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="2da5e-115">둘 다 동일한 구조체 형식 경우 다른 하나의 변수를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="2da5e-116">이 다른의 해당 요소를 한 구조체의 모든 요소를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="2da5e-117">다음 선언은이입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="2da5e-118">구조 요소 인지 참조 형식이 같은 `String`, `Object`, 또는 데이터에 대 한 포인터 배열에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="2da5e-119">이전 예제의 경우 `systemInfo` 앞의 예제에서 포인터 복사 하는 다음 개체 변수에 포함 된 `mySystem` 를 `yourSystem`, 및 액세스할 때 한 구조를 통해 개체의 데이터의 변경 내용이 적용 됩니다 통해 다른 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="2da5e-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da5e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2da5e-120">See Also</span></span>  
 [<span data-ttu-id="2da5e-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2da5e-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="2da5e-122">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2da5e-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="2da5e-123">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2da5e-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="2da5e-124">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="2da5e-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="2da5e-125">구조체</span><span class="sxs-lookup"><span data-stu-id="2da5e-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="2da5e-126">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2da5e-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="2da5e-127">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="2da5e-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="2da5e-128">구조체 및 기타 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="2da5e-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="2da5e-129">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="2da5e-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="2da5e-130">Structure 문</span><span class="sxs-lookup"><span data-stu-id="2da5e-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)

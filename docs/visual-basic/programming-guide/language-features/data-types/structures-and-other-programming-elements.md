---
title: 구조체 및 기타 프로그래밍 요소(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 7b375c5a45998fc0bd06f7c075f23a30dd377295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652027"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="dc145-102">구조체 및 기타 프로그래밍 요소(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc145-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="dc145-103">배열, 개체 및 프로시저 및 상호 함께 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="dc145-104">이러한 요소를 개별적으로 사용 하는 대로 동일한 구문을 사용 하는 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc145-105">구조체 선언에서 구조체 요소를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="dc145-106">구조 형식으로 선언 된 변수는 요소에만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="dc145-107">구조체 및 배열을</span><span class="sxs-lookup"><span data-stu-id="dc145-107">Structures and Arrays</span></span>  
 <span data-ttu-id="dc145-108">구조체의 요소가 하나 이상으로 배열을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="dc145-109">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="dc145-110">구조 내에서 배열 값에는 개체에 속성에 액세스 하는 동일한 방식으로 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="dc145-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="dc145-112">구조체의 배열을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-112">You can also declare an array of structures.</span></span> <span data-ttu-id="dc145-113">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="dc145-114">이 데이터 아키텍처의 구성 요소에 액세스 하려면 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="dc145-115">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="dc145-116">구조 및 개체</span><span class="sxs-lookup"><span data-stu-id="dc145-116">Structures and Objects</span></span>  
 <span data-ttu-id="dc145-117">구조체의 요소가 하나 이상으로 개체를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="dc145-118">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="dc145-119">이러한 선언에는 특정 개체 클래스를 사용 해야 대신 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="dc145-120">구조 및 프로시저</span><span class="sxs-lookup"><span data-stu-id="dc145-120">Structures and Procedures</span></span>  
 <span data-ttu-id="dc145-121">프로시저 인수로 구조체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="dc145-122">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="dc145-123">위 예제 전달 구조 *참조에 의해*, 호출 코드에서 변경 내용이 적용 되도록 해당 요소를 수정 하는 절차를 허용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="dc145-124">이러한 수정 으로부터 구조를 보호 하려는 값으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="dc145-125">구조체를 반환할 수도 있습니다는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="dc145-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="dc145-127">구조체 내에서 구조</span><span class="sxs-lookup"><span data-stu-id="dc145-127">Structures Within Structures</span></span>  
 <span data-ttu-id="dc145-128">구조체는 다른 구조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-128">Structures can contain other structures.</span></span> <span data-ttu-id="dc145-129">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="dc145-130">다른 모듈에 정의 된 구조 내에서 한 개의 모듈에 정의 된 구조체를 캡슐화 하이 기술을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="dc145-131">구조를 중첩 다른 구조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc145-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc145-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc145-132">See Also</span></span>  
 [<span data-ttu-id="dc145-133">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dc145-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="dc145-134">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dc145-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="dc145-135">복합 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dc145-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="dc145-136">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="dc145-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="dc145-137">구조체</span><span class="sxs-lookup"><span data-stu-id="dc145-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="dc145-138">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dc145-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="dc145-139">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="dc145-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="dc145-140">구조체 변수</span><span class="sxs-lookup"><span data-stu-id="dc145-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [<span data-ttu-id="dc145-141">구조체와 클래스</span><span class="sxs-lookup"><span data-stu-id="dc145-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="dc145-142">Structure 문</span><span class="sxs-lookup"><span data-stu-id="dc145-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)

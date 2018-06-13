---
title: 사용자 정의 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 07f04fb111863ca18d4966a7f0f967f11719aeec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590677"
---
# <a name="user-defined-data-type"></a><span data-ttu-id="8cf42-102">사용자 정의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8cf42-102">User-Defined Data Type</span></span>
<span data-ttu-id="8cf42-103">사용자가 정의한 형식에서 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-103">Holds data in a format you define.</span></span> <span data-ttu-id="8cf42-104">`Structure` 문으로 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-104">The `Structure` statement defines the format.</span></span>  
  
 <span data-ttu-id="8cf42-105">이전 버전의 Visual Basic 사용자 정의 형식 (UDT)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-105">Previous versions of Visual Basic support the user-defined type (UDT).</span></span> <span data-ttu-id="8cf42-106">현재 버전에는 UDT를 확장 한 *구조*합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-106">The current version expands the UDT to a *structure*.</span></span> <span data-ttu-id="8cf42-107">구조체는 하나 이상의 연결 *멤버* 다양 한 데이터 형식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-107">A structure is a concatenation of one or more *members* of various data types.</span></span> <span data-ttu-id="8cf42-108">Visual Basic의 멤버를 개별적으로 액세스할 수도 수는 있지만 단일 단위로 구조를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-108">Visual Basic treats a structure as a single unit, although you can also access its members individually.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cf42-109">설명</span><span class="sxs-lookup"><span data-stu-id="8cf42-109">Remarks</span></span>  
 <span data-ttu-id="8cf42-110">정의 하 고 다양 한 데이터 형식, 단일 단위로 결합 해야 하거나 기본 데이터 형식 중 용도 때 구조 데이터 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-110">Define and use a structure data type when you need to combine various data types into a single unit, or when none of the elementary data types serve your needs.</span></span>  
  
 <span data-ttu-id="8cf42-111">구조 데이터 형식의 기본값 각 해당 멤버의 기본 값의 조합으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-111">The default value of a structure data type consists of the combination of the default values of each of its members.</span></span>  
  
## <a name="declaration-format"></a><span data-ttu-id="8cf42-112">선언 형식</span><span class="sxs-lookup"><span data-stu-id="8cf42-112">Declaration Format</span></span>  
 <span data-ttu-id="8cf42-113">구조체 선언으로 시작는 [Structure 문을](../../../visual-basic/language-reference/statements/structure-statement.md) 종료는 `End``Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="8cf42-113">A structure declaration starts with the [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) and ends with the `End``Structure` statement.</span></span> <span data-ttu-id="8cf42-114">`Structure` 문은 구조체가 정의 하는 데이터 형식의 식별자 이기도 구조의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-114">The `Structure` statement supplies the name of the structure, which is also the identifier of the data type the structure is defining.</span></span> <span data-ttu-id="8cf42-115">코드의 다른 부분 변수, 매개 변수 및 함수 반환 값이이 구조체의 데이터 형식이 되도록 선언에이 식별자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-115">Other parts of the code can use this identifier to declare variables, parameters, and function return values to be of this structure's data type.</span></span>  
  
 <span data-ttu-id="8cf42-116">사이의 선언은 `Structure` 및 `End``Structure` 문을 구조체의 멤버를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-116">The declarations between the `Structure` and `End``Structure` statements define the members of the structure.</span></span>  
  
## <a name="member-access-levels"></a><span data-ttu-id="8cf42-117">멤버 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8cf42-117">Member Access Levels</span></span>  
 <span data-ttu-id="8cf42-118">사용 하 여 모든 멤버를 선언 해야는 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) 또는 같은 액세스 수준을 지정 하는 문 [공용](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../visual-basic/language-reference/modifiers/private.md).</span><span class="sxs-lookup"><span data-stu-id="8cf42-118">You must declare every member using a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) or a statement that specifies access level, such as [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="8cf42-119">사용 하는 경우는 `Dim` 문, 액세스 수준은 기본적으로 public입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-119">If you use a `Dim` statement, the access level defaults to public.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="8cf42-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="8cf42-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="8cf42-121">**메모리 소비 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf42-121">**Memory Consumption.**</span></span> <span data-ttu-id="8cf42-122">복합 데이터 형식을 모두와 마찬가지로 해당 멤버의 일반 저장소 할당량을 함께 추가 하 여 구조체의 총 메모리 사용량을 안전 하 게 계산할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-122">As with all composite data types, you cannot safely calculate the total memory consumption of a structure by adding together the nominal storage allocations of its members.</span></span> <span data-ttu-id="8cf42-123">또한 가정할 수 없습니다 메모리에는 저장소의 순서는 사용자의 선언 순서와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-123">Furthermore, you cannot safely assume that the order of storage in memory is the same as your order of declaration.</span></span> <span data-ttu-id="8cf42-124">구조체의 저장소 레이아웃을 제어 해야 하는 경우 적용할 수 있습니다는 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 `Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="8cf42-124">If you need to control the storage layout of a structure, you can apply the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute to the `Structure` statement.</span></span>  
  
-   <span data-ttu-id="8cf42-125">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf42-125">**Interop Considerations.**</span></span> <span data-ttu-id="8cf42-126">.NET Framework에 대해 작성 되지 않은 구성 요소와 조작 하는 예를 들어 Automation 또는 COM 개체를 다른 환경에서 사용자 정의 형식 Visual Basic과 호환 되는지에 유의 형식을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-126">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that user-defined types in other environments are not compatible with Visual Basic structure types.</span></span>  
  
-   <span data-ttu-id="8cf42-127">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf42-127">**Widening.**</span></span> <span data-ttu-id="8cf42-128">또는 구조 데이터 형식에서 자동 변환 작업 없이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-128">There is no automatic conversion to or from any structure data type.</span></span> <span data-ttu-id="8cf42-129">사용 하 여 구조체에서 변환 연산자를 정의할 수는 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md), 되도록 각 변환 연산자를 선언할 수 `Widening` 또는 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-129">You can define conversion operators on your structure using the [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), and you can declare each conversion operator to be `Widening` or `Narrowing`.</span></span>  
  
-   <span data-ttu-id="8cf42-130">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf42-130">**Type Characters.**</span></span> <span data-ttu-id="8cf42-131">데이터 형식 구조를가지고 있지 않습니다 리터럴 형식 문자를 식별자 형식 문자.</span><span class="sxs-lookup"><span data-stu-id="8cf42-131">Structure data types have no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="8cf42-132">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="8cf42-132">**Framework Type.**</span></span> <span data-ttu-id="8cf42-133">.NET Framework의 해당 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-133">There is no corresponding type in the .NET Framework.</span></span> <span data-ttu-id="8cf42-134">.NET Framework 클래스에서 상속 하는 모든 구조 <xref:System.ValueType?displayProperty=nameWithType>, 있지만에 해당 하는 개별 구조가 <xref:System.ValueType?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-134">All structures inherit from the .NET Framework class <xref:System.ValueType?displayProperty=nameWithType>, but no individual structure corresponds to <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cf42-135">예제</span><span class="sxs-lookup"><span data-stu-id="8cf42-135">Example</span></span>  
 <span data-ttu-id="8cf42-136">다음 패러다임 구조체 선언 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cf42-136">The following paradigm shows the outline of the declaration of a structure.</span></span>  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cf42-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cf42-137">See Also</span></span>  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [<span data-ttu-id="8cf42-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8cf42-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="8cf42-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="8cf42-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="8cf42-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="8cf42-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="8cf42-141">Structure 문</span><span class="sxs-lookup"><span data-stu-id="8cf42-141">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="8cf42-142">확장</span><span class="sxs-lookup"><span data-stu-id="8cf42-142">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="8cf42-143">Narrowing</span><span class="sxs-lookup"><span data-stu-id="8cf42-143">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="8cf42-144">구조체</span><span class="sxs-lookup"><span data-stu-id="8cf42-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="8cf42-145">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="8cf42-145">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

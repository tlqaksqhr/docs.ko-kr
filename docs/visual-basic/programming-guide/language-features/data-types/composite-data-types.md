---
title: "복합 데이터 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types
- composite data types
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures, composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
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
ms.openlocfilehash: 5f0c6215ce45d724a7b5c8c4f8e34ea27bce8fe4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="75d6a-102">복합 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75d6a-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="75d6a-103">기본 데이터 형식 외에도 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 공급 장치, 수 조합 하 여 만들려는 다른 형식의 항목 *복합 데이터 형식* 구조, 배열, 클래스 등입니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-103">In addition to the elementary data types [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="75d6a-104">복합 데이터 형식 및 다른 복합 형식의 기본 형식에서 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="75d6a-105">예를 들어 배열 구성원과 구조 요소를 배열 또는 구조를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="75d6a-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="75d6a-106">Data Types</span></span>  
 <span data-ttu-id="75d6a-107">복합 형식이 각 구성 요소의 데이터 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="75d6a-108">예를 들어 배열을 `Integer` 요소 아닙니다는 `Integer` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="75d6a-109">배열 데이터 형식은 요소 형식, 괄호 및 쉼표를 사용 하 여 필요에 따라 일반적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="75d6a-110">예를 들어&1; 차원 배열을 `String` 요소로 표시 됩니다 `String()`,&2; 차원 배열을 `Boolean` 요소로 표현 됩니다 `Boolean(,)`합니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="75d6a-111">구조체 형식</span><span class="sxs-lookup"><span data-stu-id="75d6a-111">Structure Types</span></span>  
 <span data-ttu-id="75d6a-112">모든 구조를 포함 하는 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="75d6a-113">대신, 구조체의 각 정의 두 개의 구조 순서 대로 동일한 요소를 정의 하는 경우에 고유한 데이터 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="75d6a-114">그러나 동일한 구조를 두 개 이상의 인스턴스를 만드는 경우, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식이 동일한 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-114">However, if you create two or more instances of the same structure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] considers them to be of the same data type.</span></span>  
  
## <a name="array-types"></a><span data-ttu-id="75d6a-115">배열 형식</span><span class="sxs-lookup"><span data-stu-id="75d6a-115">Array Types</span></span>  
 <span data-ttu-id="75d6a-116">모든 배열을 포함 하는 단일 데이터 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-116">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="75d6a-117">데이터 형식의 배열의 특정 인스턴스는 다음에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-117">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="75d6a-118">배열 이라는 사실</span><span class="sxs-lookup"><span data-stu-id="75d6a-118">The fact of being an array</span></span>  
  
-   <span data-ttu-id="75d6a-119">배열의 차수 (차원의 수)</span><span class="sxs-lookup"><span data-stu-id="75d6a-119">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="75d6a-120">배열의 요소 형식</span><span class="sxs-lookup"><span data-stu-id="75d6a-120">The element type of the array</span></span>  
  
 <span data-ttu-id="75d6a-121">특히, 주어진 차원의 길이 인스턴스의 데이터 형식의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-121">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="75d6a-122">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-122">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="75d6a-123">앞의 예제에서 배열 변수 `arrayA` 및 `arrayB` 동일한 데이터 형식으로 간주 됩니다- `Byte()` -길이가 다른 초기화 하는 경우에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-123">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="75d6a-124">변수 `arrayB` 및 `arrayC` 는 해당 요소 형식이 다른 동일한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-124">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="75d6a-125">변수 `arrayC` 및 `arrayD` 는 차수가 다른 동일한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-125">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="75d6a-126">변수 `arrayD` 및 `arrayE` 유형이 동일- `Short(,)` -같기 때문에 차수 및 요소 형식, 경우에 `arrayD` 아직 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-126">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="75d6a-127">배열에 대 한 자세한 내용은 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-127">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="75d6a-128">클래스 형식</span><span class="sxs-lookup"><span data-stu-id="75d6a-128">Class Types</span></span>  
 <span data-ttu-id="75d6a-129">모든 클래스를 포함 하는 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-129">There is no single data type comprising all classes.</span></span> <span data-ttu-id="75d6a-130">하나의 클래스가 다른 클래스에서 상속할 수 있지만 각각 별도 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-130">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="75d6a-131">동일한 클래스의 여러 인스턴스는 동일한 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-131">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="75d6a-132">다른 클래스 인스턴스 변수를 할당 하는 경우 뿐만 아니라 동일한 데이터 형식을 갖습니다, 그리고 메모리의 동일한 클래스 인스턴스를 가리키는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-132">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="75d6a-133">클래스에 대 한 자세한 내용은 참조 하십시오. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="75d6a-133">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d6a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75d6a-134">See Also</span></span>  
 <span data-ttu-id="75d6a-135">[데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-135">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="75d6a-136"> [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-136"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="75d6a-137"> [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-137"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="75d6a-138"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-138"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="75d6a-139"> [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-139"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="75d6a-140"> [구조](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-140"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="75d6a-141"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="75d6a-141"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="75d6a-142"> [방법: 변수에 두 개 이상의 값 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span><span class="sxs-lookup"><span data-stu-id="75d6a-142"> [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)</span></span>

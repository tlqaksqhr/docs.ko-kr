---
title: GetType 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603849"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="5a7e7-102">GetType 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a7e7-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="5a7e7-103">반환 된 <xref:System.Type> 지정된 된 형식에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="5a7e7-104"><xref:System.Type> 개체의 속성, 메서드 및 이벤트와 같은 형식에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a7e7-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a7e7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a7e7-106">Parameters</span></span>  
  
|<span data-ttu-id="5a7e7-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a7e7-107">Parameter</span></span>|<span data-ttu-id="5a7e7-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a7e7-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="5a7e7-109">정보 원하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a7e7-110">설명</span><span class="sxs-lookup"><span data-stu-id="5a7e7-110">Remarks</span></span>  
 <span data-ttu-id="5a7e7-111">`GetType` 연산자는 반환 된 <xref:System.Type> 지정 된 개체 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="5a7e7-112">에 정의 된 모든 형식의 이름을 전달할 수 있습니다 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="5a7e7-113">여기에는 다음과 같은 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="5a7e7-114">와 같은 모든 Visual Basic 데이터 형식 `Boolean` 또는 `Date`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="5a7e7-115">모든.NET Framework 클래스, 구조체, 모듈 또는 인터페이스와 같은 <xref:System.ArgumentException?displayProperty=nameWithType> 또는 <xref:System.Double?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="5a7e7-116">모든 클래스, 구조체, 모듈 또는 인터페이스 응용 프로그램에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="5a7e7-117">응용 프로그램에 정의 된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="5a7e7-118">응용 프로그램에서 정의 된 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="5a7e7-119">Visual Basic,.NET Framework 또는 응용 프로그램에 정의 된 모든 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="5a7e7-120">개체 변수의 형식 개체를 가져오려는 경우 사용 하 여는 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="5a7e7-121">`GetType` 연산자는 다음과 같은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="5a7e7-122">런타임 시 형식에 대 한 메타 데이터에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="5a7e7-123"><xref:System.Type> 개체 형식 멤버 및 배포 정보 등의 메타 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="5a7e7-124">해야이 예를 들어 어셈블리를 리플렉션 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="5a7e7-125">자세한 내용은 <xref:System.Reflection?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="5a7e7-126">두 개체 참조가 동일한 형식의 인스턴스를 참조 하는 경우를 확인 하려면 비교 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="5a7e7-127">그럴 경우 `GetType` 에 동일한 참조를 반환 <xref:System.Type> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a7e7-128">예제</span><span class="sxs-lookup"><span data-stu-id="5a7e7-128">Example</span></span>  
 <span data-ttu-id="5a7e7-129">다음 예제에 나온은 `GetType` 연산자를 사용에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7e7-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5a7e7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a7e7-130">See Also</span></span>  
 [<span data-ttu-id="5a7e7-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="5a7e7-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5a7e7-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="5a7e7-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5a7e7-133">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="5a7e7-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)

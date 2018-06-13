---
title: 멤버(F#)
description: 'F # 프로그래밍 언어의 개체 멤버에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 6dcdb1d7fa061fb838d4aa8f7a2912fd168c3781
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562209"
---
# <a name="members"></a><span data-ttu-id="ba729-103">멤버</span><span class="sxs-lookup"><span data-stu-id="ba729-103">Members</span></span>

<span data-ttu-id="ba729-104">이 섹션에서는 F# 개체 형식의 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-104">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="ba729-105">설명</span><span class="sxs-lookup"><span data-stu-id="ba729-105">Remarks</span></span>
<span data-ttu-id="ba729-106">*멤버*는 형식 정의의 일부인 기능이며 `member` 키워드로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-106">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="ba729-107">레코드, 클래스, 구분된 공용 구조체, 인터페이스, 구조체와 같은 F# 개체 형식에서는 멤버를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-107">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="ba729-108">자세한 내용은 [레코드](../records.md), [클래스](../classes.md), [구분된 공용 구조체](../discriminated-Unions.md), [인터페이스](../interfaces.md), 및 [구조체](../structures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba729-108">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="ba729-109">멤버는 일반적으로 특정 형식의 공용 인터페이스를 구성합니다. 이것이 달리 지정된 경우가 아니라면 멤버가 public인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-109">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="ba729-110">멤버는 private 또는 internal로 선언될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-110">Members can also be declared private or internal.</span></span> <span data-ttu-id="ba729-111">자세한 내용은 [액세스 제어](../access-Control.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba729-111">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="ba729-112">형식에 대한 시그니처는 특정 형식의 특정 멤버를 노출하거나 노출하지 않는 데에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-112">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="ba729-113">자세한 내용은 [시그니처](../signatures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba729-113">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="ba729-114">Private 필드 및 `do` 바인딩(클래스에만 사용됨)은 특정 형식의 공용 인터페이스의 일부가 아니며 `member` 키워드로 선언되지 않아서 실제 멤버가 아니지만 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-114">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ba729-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ba729-115">Related Topics</span></span>


|<span data-ttu-id="ba729-116">항목</span><span class="sxs-lookup"><span data-stu-id="ba729-116">Topic</span></span>|<span data-ttu-id="ba729-117">설명</span><span class="sxs-lookup"><span data-stu-id="ba729-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="ba729-118">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="ba729-118">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="ba729-119">클래스의 private 필드 및 함수에 대한 정의에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-119">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="ba729-120">클래스의 `do` 바인딩</span><span class="sxs-lookup"><span data-stu-id="ba729-120">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="ba729-121">개체 초기화 코드의 사양에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-121">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="ba729-122">속성</span><span class="sxs-lookup"><span data-stu-id="ba729-122">Properties</span></span>](properties.md)|<span data-ttu-id="ba729-123">클래스 및 기타 형식의 속성 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-123">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="ba729-124">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="ba729-124">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="ba729-125">기타 형식 및 클래스의 배열 형식의 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-125">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="ba729-126">메서드</span><span class="sxs-lookup"><span data-stu-id="ba729-126">Methods</span></span>](methods.md)|<span data-ttu-id="ba729-127">특정 형식의 멤버인 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-127">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="ba729-128">생성자</span><span class="sxs-lookup"><span data-stu-id="ba729-128">Constructors</span></span>](constructors.md)|<span data-ttu-id="ba729-129">특정 형식의 개체를 초기화하는 특수 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-129">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="ba729-130">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="ba729-130">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="ba729-131">형식에 대한 사용자 지정된 연산자 정의에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-131">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="ba729-132">이벤트</span><span class="sxs-lookup"><span data-stu-id="ba729-132">Events</span></span>](events.md)|<span data-ttu-id="ba729-133">F#의 이벤트 및 이벤트 처리 지원에 대한 정의에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-133">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="ba729-134">명시적 필드: `val` 키워드</span><span class="sxs-lookup"><span data-stu-id="ba729-134">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="ba729-135">특정 형식의 초기화되지 않은 필드에 대한 정의에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba729-135">Describes the definition of uninitialized fields in a type.</span></span>|

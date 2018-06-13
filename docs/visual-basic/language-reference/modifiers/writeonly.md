---
title: WriteOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599205"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="88f8f-102">WriteOnly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88f8f-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="88f8f-103">속성을 쓸 수는 있지만 읽을 수는 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88f8f-104">설명</span><span class="sxs-lookup"><span data-stu-id="88f8f-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="88f8f-105">규칙</span><span class="sxs-lookup"><span data-stu-id="88f8f-105">Rules</span></span>  
 <span data-ttu-id="88f8f-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-106">**Declaration Context.**</span></span> <span data-ttu-id="88f8f-107">`WriteOnly`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="88f8f-108">즉, 선언 컨텍스트는 `WriteOnly` 속성 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="88f8f-109">속성으로 선언할 수 있습니다 `WriteOnly`, 이나 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="88f8f-110">WriteOnly를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="88f8f-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="88f8f-111">값을 설정 하지만 무엇 인지를 검색 하지 못하도록 해야 사용 하는 코드는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="88f8f-112">예를 들어 소셜 등록 번호 또는 암호와 같은 중요 한 데이터를 설정 하지 않은 모든 구성 요소에 의해 액세스 로부터 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="88f8f-113">이러한 경우에 사용할 수 있습니다는 `WriteOnly` 속성 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88f8f-114">정의 하 고 사용 하 여 한 `WriteOnly` 속성을 다음과 같은 추가적인 보안 방법을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
-   <span data-ttu-id="88f8f-115">**오버 로드합니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-115">**Overriding.**</span></span> <span data-ttu-id="88f8f-116">클래스의 멤버 속성을 사용 하는 경우이 기본값으로 사용 하도록 허용 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)를 선언 하지 마십시오 하 고 `Overridable` 또는 `MustOverride`합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="88f8f-117">이 파생된 클래스 재정의 통해 원치 않는 액세스 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
-   <span data-ttu-id="88f8f-118">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-118">**Access Level.**</span></span> <span data-ttu-id="88f8f-119">하나 이상의 변수에서 속성의 중요 한 데이터를 보유 하는 경우 선언 [개인](../../../visual-basic/language-reference/modifiers/private.md) 다른 코드에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
-   <span data-ttu-id="88f8f-120">**암호화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-120">**Encryption.**</span></span> <span data-ttu-id="88f8f-121">일반 텍스트가 아닌 암호화 된 형식으로 모든 중요 한 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="88f8f-122">내리기 어려운 경우 어떻게 하 든 악성 코드에는 메모리의 해당 영역에 대 한 액세스 권한을 얻습니다, 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="88f8f-123">암호화는 중요 한 데이터를 serialize 해야 하는 경우 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
-   <span data-ttu-id="88f8f-124">**다시 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-124">**Resetting.**</span></span> <span data-ttu-id="88f8f-125">클래스, 구조체 또는 속성을 정의 하는 모듈 종료 될 때 의미 없는 다른 값 또는 기본 값으로 중요 한 데이터를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="88f8f-126">이 메모리의 해당 영역에 대 한 일반적인 액세스 해제 되었을 때 보다 효과적인 보호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
-   <span data-ttu-id="88f8f-127">**지 속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="88f8f-127">**Persistence.**</span></span> <span data-ttu-id="88f8f-128">예를 들어 디스크에서의 중요 한 데이터를 방지할 수 있습니다 지속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="88f8f-129">또한를 클립보드에 중요 한 데이터를 작성 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="88f8f-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="88f8f-130">`WriteOnly` 한정자는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f8f-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="88f8f-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="88f8f-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="88f8f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88f8f-132">See Also</span></span>  
 [<span data-ttu-id="88f8f-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="88f8f-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="88f8f-134">전용</span><span class="sxs-lookup"><span data-stu-id="88f8f-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="88f8f-135">키워드</span><span class="sxs-lookup"><span data-stu-id="88f8f-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)

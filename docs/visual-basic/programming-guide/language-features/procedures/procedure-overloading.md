---
title: "프로시저 오버로딩(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65fd5a6763752c616f13891bfa5acabff6115d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="572bc-102">프로시저 오버로딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="572bc-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="572bc-103">*오버 로드* 프로시저 이름은 같지만 다른 매개 변수 목록을 사용 하 여 여러 버전에서 정의 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="572bc-104">오버 로드의 목적은 이름을 다르게 필요 없이 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="572bc-105">매개 변수 목록을 변경 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="572bc-106">규칙 오버 로드</span><span class="sxs-lookup"><span data-stu-id="572bc-106">Overloading Rules</span></span>  
 <span data-ttu-id="572bc-107">프로시저를 오버 로드할 때는 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="572bc-108">**이름이 같은**합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-108">**Same Name**.</span></span> <span data-ttu-id="572bc-109">각 오버 로드 된 버전에는 동일한 프로시저 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="572bc-110">**다른 서명**합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-110">**Different Signature**.</span></span> <span data-ttu-id="572bc-111">다음 측면과 관련 하 여 하나 이상의 다른 모든 오버 로드 된 버전에서 각 오버 로드 된 버전 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="572bc-112">매개 변수 개수</span><span class="sxs-lookup"><span data-stu-id="572bc-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="572bc-113">매개 변수의 순서</span><span class="sxs-lookup"><span data-stu-id="572bc-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="572bc-114">매개 변수 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="572bc-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="572bc-115">형식 매개 변수 (제네릭 프로시저의 경우)의 수</span><span class="sxs-lookup"><span data-stu-id="572bc-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="572bc-116">반환 형식 (변환 연산자)에</span><span class="sxs-lookup"><span data-stu-id="572bc-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="572bc-117">위의 항목은 전체적으로 프로시저 이름과 함께 호출 된 *서명* 프로시저의 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="572bc-118">오버 로드 된 프로시저를 호출할 때 컴파일러는 서명을 사용 하 여 호출이 올바르게 정의 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="572bc-119">**서명 포함 되지 않는 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="572bc-120">서명을 변경 하지 않고 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="572bc-121">특히, 다음 항목 중 하나 이상의 변경 하 여 프로시저를 오버 로드할 수 없습니다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="572bc-122">프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및`Static`</span><span class="sxs-lookup"><span data-stu-id="572bc-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="572bc-123">매개 변수 또는 형식 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="572bc-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="572bc-124">형식 매개 변수 제약 조건 (제네릭 프로시저의 경우)</span><span class="sxs-lookup"><span data-stu-id="572bc-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="572bc-125">매개 변수 한정자 키워드와 같은 `ByRef` 및`Optional`</span><span class="sxs-lookup"><span data-stu-id="572bc-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="572bc-126">값을 반환 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="572bc-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="572bc-127">반환 값 (변환 연산자 제외)의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="572bc-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="572bc-128">앞의 목록에 항목 서명의 일부가 않습니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="572bc-129">사용할 수는 없지만 해당 오버 로드 된 버전을 구분할 수를 적절히 서명만 구분 되어 있는 오버 로드 버전에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="572bc-130">**런타임에 바인딩된 인수**합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="572bc-131">오버 로드 된 버전을 런타임에 바인딩된 개체 변수를 전달 하려는 경우으로 적절 한 매개 변수를 선언 해야 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="572bc-132">여러 버전의 프로시저</span><span class="sxs-lookup"><span data-stu-id="572bc-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="572bc-133">작성 하는 경우를 가정해 볼는 `Sub` 고객의 균형 및 수에 대 한 트랜잭션을 게시 하는 프로시저 이름으로 또는 계정 번호 고객에 게 참조 수 있게 되기를 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="572bc-134">이 위해 두 개의 다른 정의할 수 있습니다 `Sub` 다음 예제와 같이 프로시저:</span><span class="sxs-lookup"><span data-stu-id="572bc-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="572bc-135">오버 로드 된 버전</span><span class="sxs-lookup"><span data-stu-id="572bc-135">Overloaded Versions</span></span>  
 <span data-ttu-id="572bc-136">대신 단일 프로시저 이름을 오버 로드 되려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="572bc-137">사용할 수는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 각 매개 변수 목록에 대 한 프로시저의 버전을 다음과 같이 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="572bc-138">추가 오버 로드</span><span class="sxs-lookup"><span data-stu-id="572bc-138">Additional Overloads</span></span>  
 <span data-ttu-id="572bc-139">거래 금액을 적용 하려는 경우 `Decimal` 또는 `Single`, 추가로 오버 로드 하면 `post` 이 변형에 대해 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="572bc-140">동일한 작업을 수행 하는 경우 각 앞의 예제에서 오버 로드 해야 4 `Sub` 프로시저 이름이 같은 같지만 서로 다른 네 개의 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="572bc-141">오버 로드의 장점</span><span class="sxs-lookup"><span data-stu-id="572bc-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="572bc-142">프로시저 오버 로드의 장점은 호출의 유연성에서입니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="572bc-143">사용 하는 `post` 앞의 예제에서 선언 된 프로시저 호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 두 경우 모두에서 같은 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="572bc-144">다음 예제는 이러한 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="572bc-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="572bc-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="572bc-145">See Also</span></span>  
 [<span data-ttu-id="572bc-146">절차</span><span class="sxs-lookup"><span data-stu-id="572bc-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="572bc-147">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="572bc-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="572bc-148">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="572bc-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="572bc-149">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="572bc-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="572bc-150">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="572bc-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="572bc-151">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="572bc-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="572bc-152">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="572bc-152">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="572bc-153">오버로드</span><span class="sxs-lookup"><span data-stu-id="572bc-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="572bc-154">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="572bc-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

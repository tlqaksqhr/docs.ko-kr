---
title: "오버 로드 확인 (Visual Basic) | Microsoft 문서"
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
- Visual Basic code, procedures
- overload resolution
- procedures, overloading
- procedures, calling
- procedure overloading, overload resolution
- signatures, procedure
- overloads, resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
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
ms.openlocfilehash: a4f350af0f7d964df45974990991a2e94b26551e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="3ebcb-102">오버로드 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ebcb-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="3ebcb-103">경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서 몇 가지 오버 로드 된 버전에 정의 된 프로시저 호출을 발생, 컴파일러를 호출 하는 오버 로드 중 어떤 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-103">When the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="3ebcb-104">다음 단계를 수행 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="3ebcb-105">**액세스 가능성입니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-105">**Accessibility.**</span></span> <span data-ttu-id="3ebcb-106">호출 코드에서 메서드를 호출 하지 못하도록 하는 액세스 수준 사용 하 여 오버 로드를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="3ebcb-107">**매개 변수 개수입니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-107">**Number of Parameters.**</span></span> <span data-ttu-id="3ebcb-108">호출에서 제공 하는 다른 개수의 매개 변수를 정의 하는 오버 로드를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="3ebcb-109">**매개 변수 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-109">**Parameter Data Types.**</span></span> <span data-ttu-id="3ebcb-110">컴파일러는 확장 메서드를 통해 기본 설정 인스턴스 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="3ebcb-111">만 확장 되는 프로시저 호출에 맞게 변환 해야 하는 인스턴스 메서드 있으면 모든 확장 메서드를 삭제 하 고 컴파일러만는 인스턴스 메서드와 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="3ebcb-112">이러한 인스턴스 메서드가 있으면 인스턴스 및 확장 메서드를 모두 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="3ebcb-113">이 단계에서는 오버 로드를 호출 인수의 데이터 형식을 변환할 수 없습니다 오버 로드에 정의 된 매개 변수 형식을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="3ebcb-114">**축소 변환입니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="3ebcb-115">호출 인수 형식에서 축소 변환을 정의 된 매개 변수 형식에 필요한 오버 로드를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="3ebcb-116">이것이 사실이 여부 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="3ebcb-117">**최소 확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-117">**Least Widening.**</span></span> <span data-ttu-id="3ebcb-118">컴파일러가 쌍의 나머지 오버 로드를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="3ebcb-119">각 쌍에 대해 정의 된 매개 변수의 데이터 형식을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="3ebcb-120">다른 시그니처에 있는 해당 형식으로 모든 오버 로드 중 하나에 있는 형식을 확대 변환, 컴파일러는 후자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="3ebcb-121">즉, 최소한의 확대 되는 오버 로드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="3ebcb-122">**단일 후보입니다.**</span><span class="sxs-lookup"><span data-stu-id="3ebcb-122">**Single Candidate.**</span></span> <span data-ttu-id="3ebcb-123">오버 로드를 하나만 남을 때까지 쌍 오버 로드는 그대로 유지 하 고 해당 오버 로드에 대 한 호출을 확인 하는 검토를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="3ebcb-124">컴파일러는 오버 로드는 단일 후보를 줄일 수 없습니다., 경우에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="3ebcb-125">다음 그림에서는 호출 하는 오버 로드 된 버전의 집합 결정 하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="3ebcb-126">![오버 로드 확인 프로세스의 흐름도](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="3ebcb-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="3ebcb-127">오버 로드 된 버전에서 확인</span><span class="sxs-lookup"><span data-stu-id="3ebcb-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="3ebcb-128">다음 예제에서는이 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-128">The following example illustrates this overload resolution process.</span></span>  
  
 <span data-ttu-id="3ebcb-129">[!code-vb[VbVbcnProcedures #&62;](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ebcb-129">[!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span></span>  
  
 <span data-ttu-id="3ebcb-130">[!code-vb[VbVbcnProcedures #&63;](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ebcb-130">[!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span></span>  
  
 <span data-ttu-id="3ebcb-131">첫 번째 호출에서는 컴파일러가 첫 번째 오버 로드를 제거 하기 때문에 첫 번째 인수의 형식 (`Short`) 해당 매개 변수 형식으로 축소 변환 (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="3ebcb-131">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="3ebcb-132">두 번째 오버 로드의 각 인수 형식 때문에 다음 세 번째 오버 로드를 제거 (`Short` 및 `Single`) 세 번째 오버 로드에서 해당 형식으로 확장 되는지를 (`Integer` 및 `Single`).</span><span class="sxs-lookup"><span data-stu-id="3ebcb-132">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="3ebcb-133">두 번째 오버 로드는 덜 확대 해도 컴파일러 호출에 대 한 사용.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-133">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="3ebcb-134">두 번째 호출에서 컴파일러 축소 변환을 기반으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-134">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="3ebcb-135">인수 형식의 덜 확대 해도와 두 번째 오버 로드를 호출할 수 있으므로 첫 번째 호출에서와 같은 이유 때문에 세 번째 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-135">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="3ebcb-136">그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 간의 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-136">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="3ebcb-137">각에 해당 하는 형식에서 다른 확장 되는 하나의 정의 된 매개 변수 형식의 (`Byte` 를 `Short`, 하지만 `Single` 를 `Double`).</span><span class="sxs-lookup"><span data-stu-id="3ebcb-137">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="3ebcb-138">따라서 컴파일러는 오버 로드 확인 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-138">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="3ebcb-139">선택적 오버 로드 및 ParamArray 인수</span><span class="sxs-lookup"><span data-stu-id="3ebcb-139">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="3ebcb-140">마지막 매개 변수가 선언 된 점을 제외 하 고 프로시저의 두 개의 오버 로드가 시그니처가 같은 경우 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 하나 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 는 다른 컴파일러가 해당 프로시저 호출을 다음과 같이 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ebcb-140">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="3ebcb-141">호출으로 서의 마지막 인수를 제공 하는 경우</span><span class="sxs-lookup"><span data-stu-id="3ebcb-141">If the call supplies the last argument as</span></span>|<span data-ttu-id="3ebcb-142">컴파일러는 선언으로 마지막 인수는 오버 로드에 대 한 호출을 확인</span><span class="sxs-lookup"><span data-stu-id="3ebcb-142">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="3ebcb-143">값 없음 (인수를 생략)</span><span class="sxs-lookup"><span data-stu-id="3ebcb-143">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="3ebcb-144">단일 값</span><span class="sxs-lookup"><span data-stu-id="3ebcb-144">A single value</span></span>|`Optional`|  
|<span data-ttu-id="3ebcb-145">쉼표로 구분 된 목록에 두 개 이상의 값</span><span class="sxs-lookup"><span data-stu-id="3ebcb-145">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="3ebcb-146">(빈 배열 포함)는 임의 길이의 배열</span><span class="sxs-lookup"><span data-stu-id="3ebcb-146">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="3ebcb-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ebcb-147">See Also</span></span>  
 <span data-ttu-id="3ebcb-148">[선택적 매개 변수](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-148">[Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="3ebcb-149"> [매개 변수 배열](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-149"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="3ebcb-150"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-150"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="3ebcb-151"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-151"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="3ebcb-152"> [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-152"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="3ebcb-153"> [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-153"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="3ebcb-154"> [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-154"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="3ebcb-155"> [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-155"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="3ebcb-156"> [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-156"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="3ebcb-157"> [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="3ebcb-157"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="3ebcb-158"> [확장명 메서드](./extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="3ebcb-158"> [Extension Methods](./extension-methods.md)</span></span>

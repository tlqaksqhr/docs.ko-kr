---
title: "방법: 불특정 개수의 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드 | Microsoft 문서"
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
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
ms.openlocfilehash: 3e4ef81049f3b0d3ab1271fb709f07c37f274a88
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="88cae-102">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88cae-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="88cae-103">프로시저에 있는 경우는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를&1; 차원 배열을 매개 변수 배열에 대 한 오버 로드 된 버전을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="88cae-104">자세한 내용은 "암시적 오버 로드에 대 한 a ParamArray 매개 변수 참조"에서 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="88cae-105">가변 개수의 매개 변수를 사용 하는 프로시저 오버 로드 하려면</span><span class="sxs-lookup"><span data-stu-id="88cae-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="88cae-106">코드 논리 혜택이 호출 하는 프로시저 오버 로드 된 버전 이상에서 확인 한 `ParamArray` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="88cae-107">"오버 로드 및 ParamArrays" 참조 [프로시저를 오버 로드할 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="88cae-108">제공 된 값의 숫자는 매개 변수 목록의 변수 부분에서 프로시저를 허용 해야 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="88cae-109">이 값이 없는 경우 포함 하며 단일&1; 차원 배열의 경우 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="88cae-110">제공 된 값의 허용 가능한 각 번호에 대 한 쓰기는 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="88cae-111">사용 하지 않는 `Optional` 또는 `ParamArray` 이 오버 로드 된 버전의 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="88cae-112">각 선언 앞에 `Sub` 또는 `Function` 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="88cae-113">각각의 선언이 호출 코드에서 해당 선언 매개 변수 목록에 해당 하는 값을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="88cae-114">각 프로시저를 종료는 `End Sub` 또는 `End Function` 문을 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88cae-115">예제</span><span class="sxs-lookup"><span data-stu-id="88cae-115">Example</span></span>  
 <span data-ttu-id="88cae-116">다음 예제에서는 사용 하 여 정의 하는 프로시저는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 및 오버 로드 된 프로시저의 해당 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 <span data-ttu-id="88cae-117">[!code-vb[VbVbcnProcedures #&69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="88cae-117">[!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span></span>  
  
 <span data-ttu-id="88cae-118">[!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="88cae-118">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span></span>  
  
 <span data-ttu-id="88cae-119">매개 변수 배열에 대 한&1; 차원 배열을 사용 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-119">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="88cae-120">그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-120">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="88cae-121">다음과 같은 선언을 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-121">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="88cae-122">[!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="88cae-122">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span></span>  
  
 <span data-ttu-id="88cae-123">오버 로드 된 버전의에서 코드는 호출 코드에 대 한 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 매개 변수를 했다면 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-123">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="88cae-124">호출 인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-124"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88cae-125">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="88cae-125">Compiling the Code</span></span>  
 <span data-ttu-id="88cae-126">때문에 프로시저는 `ParamArray` 매개 변수는 오버 로드 된 버전의 집합, 이러한 암시적 오버 로드 중 하나에 해당 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-126">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="88cae-127">자세한 내용은 참조 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-127">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="88cae-128">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="88cae-128">.NET Framework Security</span></span>  
 <span data-ttu-id="88cae-129">무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 몇 가지 내부 용량에 오버런이 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-129">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="88cae-130">매개 변수 배열에 동의 하면 호출 코드에 전달 된 배열의 길이 대 한 테스트 하 고 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cae-130">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cae-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88cae-131">See Also</span></span>  
 <span data-ttu-id="88cae-132">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-132">[Procedures](./index.md) </span></span>  
<span data-ttu-id="88cae-133"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-133"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="88cae-134"> [선택적 매개 변수](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-134"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="88cae-135"> [매개 변수 배열](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-135"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="88cae-136"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="88cae-137"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="88cae-138"> [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-138"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="88cae-139"> [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-139"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="88cae-140"> [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="88cae-140"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="88cae-141"> [오버로드 확인](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="88cae-141"> [Overload Resolution](./overload-resolution.md)</span></span>

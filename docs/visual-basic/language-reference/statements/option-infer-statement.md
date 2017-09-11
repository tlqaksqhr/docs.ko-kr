---
title: "Option Infer 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement
- Infer keyword
- declaring variables, inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: 72
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
ms.openlocfilehash: 56c2813f0fcfc23c4eb4039ffbbb1d9deeccb72c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="option-infer-statement"></a><span data-ttu-id="80baa-102">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="80baa-102">Option Infer Statement</span></span>
<span data-ttu-id="80baa-103">변수를 선언할 때 지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80baa-104">구문</span><span class="sxs-lookup"><span data-stu-id="80baa-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="80baa-105">요소</span><span class="sxs-lookup"><span data-stu-id="80baa-105">Parts</span></span>  
  
|<span data-ttu-id="80baa-106">용어</span><span class="sxs-lookup"><span data-stu-id="80baa-106">Term</span></span>|<span data-ttu-id="80baa-107">정의</span><span class="sxs-lookup"><span data-stu-id="80baa-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="80baa-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-108">Optional.</span></span> <span data-ttu-id="80baa-109">지역 형식 유추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="80baa-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-110">Optional.</span></span> <span data-ttu-id="80baa-111">지역 형식 유추를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80baa-112">설명</span><span class="sxs-lookup"><span data-stu-id="80baa-112">Remarks</span></span>  
 <span data-ttu-id="80baa-113">파일에서 `Option Infer`를 설정하려면 파일 맨 위(기타 모든 소스 코드 앞)에 `Option Infer On` 또는 `Option Infer Off`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="80baa-114">파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="80baa-115">`Option Infer`를 `On`으로 설정하면 데이터 형식을 명시적으로 설명하지 않고 로컬 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="80baa-116">컴파일러는 초기화 식의 형식에서 변수의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="80baa-117">다음 그림에서는 `Option Infer`가 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="80baa-118">`Dim someVar = 2` 선언의 변수는 형식 유추에 의해 정수로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="80baa-119">![선언의 IntelliSense 보기](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="80baa-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="80baa-120">Option Infer가 설정된 경우의 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="80baa-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="80baa-121">다음 그림에서는 `Option Infer`가 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="80baa-122">`Dim someVar = 2` 선언의 변수는 형식 유추에 의해 `Object`로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="80baa-123">이 예제는 **Option Strict** 로 설정 되어 **오프** 에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="80baa-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="80baa-124">![선언의 IntelliSense 보기](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="80baa-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="80baa-125">Option Infer가 해제된 경우의 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="80baa-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80baa-126">변수가 `Object`로 선언되면 프로그램을 실행하는 동안 런타임 형식이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="80baa-127">작업을 수행 *boxing* 및 *unboxing* 간을 변환 하는 `Object` 와 값 형식 하므로 실행 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="80baa-128">Boxing 및 unboxing에 대 한 내용은 참조는 [Visual Basic 언어 사양](../../../visual-basic/reference/language-specification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
 <span data-ttu-id="80baa-129">형식 유추는 프로시저 수준에서 적용되며 클래스, 구조체, 모듈 또는 인터페이스의 프로시저 외부에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="80baa-130">자세한 내용은 참조 [로컬 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="80baa-131">Option Infer 문이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="80baa-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="80baa-132">소스 코드에 없는 경우는 `Option Infer` 문는 **Option Infer** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="80baa-133">명령줄 컴파일러를 사용 하는 경우는 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="80baa-134">IDE에서 Option Infer를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="80baa-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="80baa-135">**솔루션 탐색기**, 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="80baa-136">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="80baa-137">자세한 내용은 참조 [NIB: 프로젝트 디자이너를 사용 하 여 프로젝트 속성 관리](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="80baa-138">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="80baa-139">값을 설정 된 **Option infer** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="80baa-140">새 프로젝트를 만들 때는 **Option Infer** 에 설정 된 **컴파일** 로 설정 되는 **Option Infer** 에서 설정는 **VB 기본값** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="80baa-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="80baa-141">에 액세스 하려면는 **VB 기본값** 대화 상자의 **도구** 메뉴를 클릭 하 여 **옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="80baa-142">에 **옵션** 대화 상자에서 **프로젝트 및 솔루션**를 클릭 하 고 **VB 기본값**합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="80baa-143">초기 기본 설정은 **VB 기본값** 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="80baa-144">명령줄에서 Option Infer를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="80baa-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="80baa-145">포함은 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) 컴파일러 옵션에는 **vbc** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="80baa-146">기본 데이터 형식 및 값</span><span class="sxs-lookup"><span data-stu-id="80baa-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="80baa-147">다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="80baa-148">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="80baa-148">Data type specified?</span></span>|<span data-ttu-id="80baa-149">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="80baa-149">Initializer specified?</span></span>|<span data-ttu-id="80baa-150">예제</span><span class="sxs-lookup"><span data-stu-id="80baa-150">Example</span></span>|<span data-ttu-id="80baa-151">결과</span><span class="sxs-lookup"><span data-stu-id="80baa-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="80baa-152">아니요</span><span class="sxs-lookup"><span data-stu-id="80baa-152">No</span></span>|<span data-ttu-id="80baa-153">아니요</span><span class="sxs-lookup"><span data-stu-id="80baa-153">No</span></span>|`Dim qty`|<span data-ttu-id="80baa-154">
          `Option Strict`가 off(기본값)이면 변수는 `Nothing`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="80baa-155">`Option Strict`가 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="80baa-156">아니요</span><span class="sxs-lookup"><span data-stu-id="80baa-156">No</span></span>|<span data-ttu-id="80baa-157">예</span><span class="sxs-lookup"><span data-stu-id="80baa-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="80baa-158">`Option Infer`가 on(기본값)이면 변수가 이니셜라이저의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="80baa-159">참조 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="80baa-160">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="80baa-161">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="80baa-162">예</span><span class="sxs-lookup"><span data-stu-id="80baa-162">Yes</span></span>|<span data-ttu-id="80baa-163">아니요</span><span class="sxs-lookup"><span data-stu-id="80baa-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="80baa-164">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="80baa-165">자세한 내용은 참조 [Dim](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="80baa-166">예</span><span class="sxs-lookup"><span data-stu-id="80baa-166">Yes</span></span>|<span data-ttu-id="80baa-167">예</span><span class="sxs-lookup"><span data-stu-id="80baa-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="80baa-168">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80baa-169">예제</span><span class="sxs-lookup"><span data-stu-id="80baa-169">Example</span></span>  
 <span data-ttu-id="80baa-170">다음 예제에서는 `Option Infer` 문이 지역 형식 유추를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 <span data-ttu-id="80baa-171">[!code-vb[VbVbalrTypeInference #&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="80baa-171">[!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="80baa-172">예제</span><span class="sxs-lookup"><span data-stu-id="80baa-172">Example</span></span>  
 <span data-ttu-id="80baa-173">다음 예제에서는 변수가 `Object`로 식별되는 경우 런타임 형식이 달라질 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80baa-173">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 <span data-ttu-id="80baa-174">[!code-vb[VbVbalrTypeInference #&11;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="80baa-174">[!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80baa-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80baa-175">See Also</span></span>  
 <span data-ttu-id="80baa-176">[Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-176">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="80baa-177"> [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-177"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="80baa-178"> [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-178"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="80baa-179"> [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-179"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="80baa-180"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-180"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="80baa-181"> [Visual Basic 프로젝트의 경우 옵션 대화 상자, 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="80baa-181"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="80baa-182"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="80baa-182"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="80baa-183"> [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)</span><span class="sxs-lookup"><span data-stu-id="80baa-183"> [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)</span></span>

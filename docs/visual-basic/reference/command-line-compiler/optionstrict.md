---
title: -optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2ff7d13fcb3e224ee76cdb42f3974a4eddb042f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-optionstrict"></a><span data-ttu-id="07968-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="07968-102">-optionstrict</span></span>
<span data-ttu-id="07968-103">암시적 형식 변환을 제한 하는 엄격한 형식 의미 체계를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07968-104">구문</span><span class="sxs-lookup"><span data-stu-id="07968-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="07968-105">인수</span><span class="sxs-lookup"><span data-stu-id="07968-105">Arguments</span></span>  
 <span data-ttu-id="07968-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="07968-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="07968-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="07968-107">Optional.</span></span> <span data-ttu-id="07968-108">`-optionstrict+` 옵션 암시적 형식 변환을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="07968-109">이 옵션의 기본값은 `-optionstrict-`합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="07968-110">`-optionstrict+` 옵션은 동일 `-optionstrict`합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="07968-111">관대 한 형식 의미 체계를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07968-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="07968-112">필수.</span><span class="sxs-lookup"><span data-stu-id="07968-112">Required.</span></span> <span data-ttu-id="07968-113">엄격한 언어 의미 체계를 준수 하지 않을 때 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07968-114">설명</span><span class="sxs-lookup"><span data-stu-id="07968-114">Remarks</span></span>  
 <span data-ttu-id="07968-115">때 `-optionstrict+` 가 적용 된 경우 확장 유형 변환만 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07968-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="07968-116">할당 하는 등의 형식 변환에 축소 변환을 암시적는 `Decimal` 형식 개체는 정수 형식 개체를, 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07968-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="07968-117">암시적 축소 형식 변환에 대 한 경고를 생성 하려면 사용 `-optionstrict:custom`합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="07968-118">사용 하 여 `-nowarn:numberlist` 특정 경고를 무시 하 고 `-warnaserror:numberlist` 특정 경고를 오류로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="07968-119">-Optionstrict Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="07968-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="07968-120">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="07968-121">에 **프로젝트** 메뉴를 클릭 하 여 **속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="07968-121">On the **Project** menu, click **Properties.**</span></span>   
  
2.  <span data-ttu-id="07968-122">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-122">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="07968-123">값을 수정 된 **Option Strict** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="07968-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="07968-124">-Optionstrict를 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="07968-124">To set -optionstrict programmatically</span></span>  
  
-   <span data-ttu-id="07968-125">참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07968-126">예제</span><span class="sxs-lookup"><span data-stu-id="07968-126">Example</span></span>  
 <span data-ttu-id="07968-127">다음 코드에서는 `Test.vb` 엄격한 형식 의미 체계를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="07968-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="07968-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07968-128">See Also</span></span>  
 [<span data-ttu-id="07968-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="07968-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="07968-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="07968-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="07968-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="07968-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="07968-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="07968-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="07968-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="07968-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [<span data-ttu-id="07968-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07968-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [<span data-ttu-id="07968-135">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="07968-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="07968-136">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="07968-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="07968-137">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="07968-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

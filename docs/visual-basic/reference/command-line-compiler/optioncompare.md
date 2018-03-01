---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62a9a4bf3428f3ee731e7ecc63be51dbf3076ee4
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="optioncompare"></a><span data-ttu-id="bcfd8-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="bcfd8-102">/optioncompare</span></span>
<span data-ttu-id="bcfd8-103">문자열 비교 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfd8-104">구문</span><span class="sxs-lookup"><span data-stu-id="bcfd8-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="bcfd8-105">설명</span><span class="sxs-lookup"><span data-stu-id="bcfd8-105">Remarks</span></span>  
 <span data-ttu-id="bcfd8-106">지정할 수 있습니다 `/optioncompare` 두 형식 중 하나로: `/optioncompare:binary` 이진 문자열 비교를 사용 하도록 및 `/optioncompare:text` 텍스트 문자열 비교를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="bcfd8-107">기본적으로 컴파일러는 다음과 같이 사용 됩니다. `/optioncompare:binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="bcfd8-108">Microsoft Windows 코드 페이지를 사용 하 고 이진 정렬 순서를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="bcfd8-109">일반적인 이진 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="bcfd8-110">텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정 하는 대/소문자 구분 텍스트 정렬 순서를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="bcfd8-111">일반 텍스트 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="bcfd8-112">/Optioncompare Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bcfd8-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="bcfd8-113">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bcfd8-114">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-114">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="bcfd8-115">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-115">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="bcfd8-116">값을 수정 된 **Option Compare** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-116">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="bcfd8-117">/Optioncompare를 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bcfd8-117">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="bcfd8-118">참조 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcfd8-119">예</span><span class="sxs-lookup"><span data-stu-id="bcfd8-119">Example</span></span>  
 <span data-ttu-id="bcfd8-120">다음 코드에서는 `ProjFile.vb` 컴파일하고 이진 문자열 비교를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd8-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcfd8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfd8-121">See Also</span></span>  
 [<span data-ttu-id="bcfd8-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="bcfd8-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bcfd8-123">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="bcfd8-123">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="bcfd8-124">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="bcfd8-124">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="bcfd8-125">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="bcfd8-125">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="bcfd8-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="bcfd8-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="bcfd8-127">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="bcfd8-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="bcfd8-128">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="bcfd8-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

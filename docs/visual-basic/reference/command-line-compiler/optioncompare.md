---
title: "/optioncompare | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
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
ms.openlocfilehash: c9512427cda0b6a3bcb0c1fe338b47ff9f779d19
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="optioncompare"></a><span data-ttu-id="0c8a8-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="0c8a8-102">/optioncompare</span></span>
<span data-ttu-id="0c8a8-103">문자열 비교 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c8a8-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c8a8-105">주의</span><span class="sxs-lookup"><span data-stu-id="0c8a8-105">Remarks</span></span>  
 <span data-ttu-id="0c8a8-106">지정할 수 있습니다 `/optioncompare` 두 가지 형태 중 하나: `/optioncompare:binary` 이진 문자열 비교를 사용 하 여 및 `/optioncompare:text` 텍스트 문자열 비교를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="0c8a8-107">기본적으로 컴파일러는 다음과 같이 사용 됩니다. `/optioncompare:binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="0c8a8-108">Microsoft Windows에서 사용 되는 코드 페이지는 이진 정렬 순서를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="0c8a8-109">일반적인 이진 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="0c8a8-110">텍스트 기반 문자열 비교는 시스템의 로캘에 따라 결정 되는 대/소문자 구분 텍스트 정렬 순서를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="0c8a8-111">일반적인 텍스트 정렬 순서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="0c8a8-112">Visual Studio IDE에서 /optioncompare를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0c8a8-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="0c8a8-113">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0c8a8-114">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="0c8a8-115">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="0c8a8-116">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="0c8a8-117">값을 수정 된 **Option Compare** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="0c8a8-118">/Optioncompare를 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0c8a8-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="0c8a8-119">참조 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8a8-120">예제</span><span class="sxs-lookup"><span data-stu-id="0c8a8-120">Example</span></span>  
 <span data-ttu-id="0c8a8-121">다음 코드에서는 P를 컴파일하여`rojFile.vb` 컴파일하고 이진 문자열 비교를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8a8-121">The following code compiles P`rojFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c8a8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c8a8-122">See Also</span></span>  
 <span data-ttu-id="0c8a8-123">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="0c8a8-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="0c8a8-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="0c8a8-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="0c8a8-127"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="0c8a8-128"> [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0c8a8-128"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="0c8a8-129"> [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="0c8a8-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>

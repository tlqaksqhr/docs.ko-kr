---
title: "/removeintchecks | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 25f67774238c6e9a6b3a2c50b3702e43d5a6374c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="removeintchecks"></a><span data-ttu-id="1026e-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="1026e-102">/removeintchecks</span></span>
<span data-ttu-id="1026e-103">오버플로 오류 또는 해제 하는 정수 연산에 대 한 검사를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1026e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1026e-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1026e-105">인수</span><span class="sxs-lookup"><span data-stu-id="1026e-105">Arguments</span></span>  
  
|<span data-ttu-id="1026e-106">용어</span><span class="sxs-lookup"><span data-stu-id="1026e-106">Term</span></span>|<span data-ttu-id="1026e-107">정의</span><span class="sxs-lookup"><span data-stu-id="1026e-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1026e-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1026e-108">`+` &#124; `-`</span></span>|<span data-ttu-id="1026e-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="1026e-109">Optional.</span></span> <span data-ttu-id="1026e-110">`/removeintchecks-` 옵션을 사용 하면 모든 정수 연산 오버플로 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="1026e-111">기본값은 `/removeintchecks-`입니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="1026e-112">지정 `/removeintchecks` 또는 `/removeintchecks+` 오류 검사를 차단 하 고 정수 계산을 더욱 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="1026e-113">그러나 오류 검사 없이 및 잘못 된 결과 데이터 형식 용량을 오버플로 하는 경우 오류를 일으키지 않고 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="1026e-114">Visual Studio에서 /removeintchecks를 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="1026e-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1026e-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1026e-116">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1026e-117">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1026e-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="1026e-118">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1026e-119">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="1026e-120">4.  값을 수정 된 **정수 오버플로 검사 해제** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1026e-121">예제</span><span class="sxs-lookup"><span data-stu-id="1026e-121">Example</span></span>  
 <span data-ttu-id="1026e-122">다음 코드에서는 `Test.vb` 정수 오버플로 오류 검사를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="1026e-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1026e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1026e-123">See Also</span></span>  
 <span data-ttu-id="1026e-124">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="1026e-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="1026e-125"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="1026e-125"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

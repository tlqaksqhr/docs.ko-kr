---
title: "/libpath | Microsoft 문서"
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
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
ms.openlocfilehash: 7f24dd7707645f45677dcf7009e1adc64afaaa7c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="libpath"></a><span data-ttu-id="45139-102">/libpath</span><span class="sxs-lookup"><span data-stu-id="45139-102">/libpath</span></span>
<span data-ttu-id="45139-103">참조 된 어셈블리의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45139-104">구문</span><span class="sxs-lookup"><span data-stu-id="45139-104">Syntax</span></span>  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="45139-105">인수</span><span class="sxs-lookup"><span data-stu-id="45139-105">Arguments</span></span>  
  
|<span data-ttu-id="45139-106">용어</span><span class="sxs-lookup"><span data-stu-id="45139-106">Term</span></span>|<span data-ttu-id="45139-107">정의</span><span class="sxs-lookup"><span data-stu-id="45139-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="45139-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="45139-108">Required.</span></span> <span data-ttu-id="45139-109">컴파일러의 경우에는 참조 된 어셈블리를 확인 하는 디렉터리의 세미콜론으로 구분 된 목록에 없는 중 하나는 현재 작업 디렉터리 (컴파일러를 호출 하는 디렉터리) 또는 공용 언어 런타임의 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="45139-110">디렉터리 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="45139-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45139-111">주의</span><span class="sxs-lookup"><span data-stu-id="45139-111">Remarks</span></span>  
 <span data-ttu-id="45139-112">`/libpath` 참조 어셈블리의 위치를 지정 하는 옵션은 [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-112">The `/libpath` option specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="45139-113">컴파일러는 다음 순서 대로 정규화 되지 않은 어셈블리 참조를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="45139-114">현재 작업 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-114">Current working directory.</span></span> <span data-ttu-id="45139-115">컴파일러를 호출 하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="45139-116">공용 언어 런타임 시스템 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="45139-117">지정 된 경로 `/libpath`합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="45139-118">LIB 환경 변수에 지정 된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="45139-119">`/libpath` 가감; 지정 옵션은 모든 이전 값에 추가 하는 한 번 이상 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-119">The `/libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="45139-120">사용 하 여 `/reference` 어셈블리 참조를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45139-120">Use `/reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="45139-121">Visual Studio에서 /libpath를 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="45139-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="45139-122">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="45139-123">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="45139-124">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45139-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="45139-125">2.  클릭 하 고 **참조** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-125">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="45139-126">3.  클릭 하 고 **참조 경로 중... ** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-126">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="45139-127">4.  에 **참조 경로** 대화 상자에서 디렉터리 이름을 입력 합니다는 **폴더:** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="45139-127">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="45139-128">5.  클릭 **폴더 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="45139-128">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45139-129">예제</span><span class="sxs-lookup"><span data-stu-id="45139-129">Example</span></span>  
 <span data-ttu-id="45139-130">다음 코드에서는 `T2.vb` .exe 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45139-130">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="45139-131">컴파일러는 어셈블리 참조에 대 한 작업 디렉터리, c: 드라이브의 루트 디렉터리를 c: 드라이브의 새 어셈블리 디렉터리에서 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="45139-131">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="45139-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45139-132">See Also</span></span>  
 <span data-ttu-id="45139-133">[어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="45139-133">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="45139-134"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="45139-134"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="45139-135"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="45139-135"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

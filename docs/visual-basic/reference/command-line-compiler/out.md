---
title: /out(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d98a9f3cadc42021c302915cfc5b058b41e11ec6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="out-visual-basic"></a><span data-ttu-id="0cc97-102">/out(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cc97-102">/out (Visual Basic)</span></span>
<span data-ttu-id="0cc97-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc97-104">구문</span><span class="sxs-lookup"><span data-stu-id="0cc97-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="0cc97-105">인수</span><span class="sxs-lookup"><span data-stu-id="0cc97-105">Arguments</span></span>  
  
|<span data-ttu-id="0cc97-106">용어</span><span class="sxs-lookup"><span data-stu-id="0cc97-106">Term</span></span>|<span data-ttu-id="0cc97-107">정의</span><span class="sxs-lookup"><span data-stu-id="0cc97-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="0cc97-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0cc97-108">Required.</span></span> <span data-ttu-id="0cc97-109">컴파일러 출력 파일의 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="0cc97-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="0cc97-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cc97-111">설명</span><span class="sxs-lookup"><span data-stu-id="0cc97-111">Remarks</span></span>  
 <span data-ttu-id="0cc97-112">전체 이름 및 만들려는 파일의 확장명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="0cc97-113">.Exe 파일의 이름을 포함 하는 소스 코드 파일에서 사용 하지 않으면는 `Sub Main` 프로시저와 저장 프로시저.dll 파일의 첫 번째 소스 코드 파일에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="0cc97-114">.Exe 또는.dll 확장명 없이 파일 이름을 지정 하면 컴파일러가 자동으로 확장을 추가 대해 지정 된 값에 따라는 `/target` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="0cc97-115">Visual Studio 통합된 개발 환경에서 out/설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0cc97-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0cc97-116">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0cc97-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="0cc97-118">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cc97-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="0cc97-119">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="0cc97-120">3.  값을 수정 된 **어셈블리 이름** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0cc97-121">예제</span><span class="sxs-lookup"><span data-stu-id="0cc97-121">Example</span></span>  
 <span data-ttu-id="0cc97-122">다음 코드에서는 `T2.vb` 출력 파일이 생성 및 `T2.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc97-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cc97-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cc97-123">See Also</span></span>  
 [<span data-ttu-id="0cc97-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="0cc97-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0cc97-125">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cc97-125">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="0cc97-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="0cc97-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

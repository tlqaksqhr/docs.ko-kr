---
title: "/out (Visual Basic) | Microsoft 문서"
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
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
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
ms.openlocfilehash: 489a9015718a581c793cd1217ba073625929daf3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="out-visual-basic"></a><span data-ttu-id="98f80-102">/out(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98f80-102">/out (Visual Basic)</span></span>
<span data-ttu-id="98f80-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f80-104">구문</span><span class="sxs-lookup"><span data-stu-id="98f80-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="98f80-105">인수</span><span class="sxs-lookup"><span data-stu-id="98f80-105">Arguments</span></span>  
  
|<span data-ttu-id="98f80-106">용어</span><span class="sxs-lookup"><span data-stu-id="98f80-106">Term</span></span>|<span data-ttu-id="98f80-107">정의</span><span class="sxs-lookup"><span data-stu-id="98f80-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="98f80-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="98f80-108">Required.</span></span> <span data-ttu-id="98f80-109">컴파일러 생성 하는 출력 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="98f80-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="98f80-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98f80-111">주의</span><span class="sxs-lookup"><span data-stu-id="98f80-111">Remarks</span></span>  
 <span data-ttu-id="98f80-112">전체 이름 및 만들 파일의 확장명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="98f80-113">.Exe 파일은 포함 하는 소스 코드 파일에서 이름을 사용 하지 않으면는 `Sub Main` 프로시저 및.dll 파일의 첫 번째 소스 코드 파일에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="98f80-114">.Exe 또는.dll 확장명 없이 파일 이름을 지정 하면 컴파일러가 자동으로 확장을 추가 대해 지정 된 값에 따라는 `/target` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="98f80-115">Visual Studio 통합된 개발 환경에서 /out 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="98f80-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="98f80-116">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="98f80-117">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="98f80-118">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98f80-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="98f80-119">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="98f80-120">3.  값을 수정 된 **어셈블리 이름** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98f80-121">예제</span><span class="sxs-lookup"><span data-stu-id="98f80-121">Example</span></span>  
 <span data-ttu-id="98f80-122">다음 코드에서는 `T2.vb` 출력 파일을 만들고 `T2.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="98f80-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="98f80-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98f80-123">See Also</span></span>  
 <span data-ttu-id="98f80-124">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="98f80-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="98f80-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="98f80-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="98f80-126"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="98f80-126"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234071d043b2649e2438ed20fe044fb89cdb9bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655891"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="c11c3-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c11c3-102">-out (Visual Basic)</span></span>
<span data-ttu-id="c11c3-103">출력 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c11c3-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c11c3-105">인수</span><span class="sxs-lookup"><span data-stu-id="c11c3-105">Arguments</span></span>  
  
|<span data-ttu-id="c11c3-106">용어</span><span class="sxs-lookup"><span data-stu-id="c11c3-106">Term</span></span>|<span data-ttu-id="c11c3-107">정의</span><span class="sxs-lookup"><span data-stu-id="c11c3-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="c11c3-108">필수.</span><span class="sxs-lookup"><span data-stu-id="c11c3-108">Required.</span></span> <span data-ttu-id="c11c3-109">컴파일러 출력 파일의 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="c11c3-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="c11c3-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c11c3-111">설명</span><span class="sxs-lookup"><span data-stu-id="c11c3-111">Remarks</span></span>  
 <span data-ttu-id="c11c3-112">전체 이름 및 만들려는 파일의 확장명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="c11c3-113">.Exe 파일의 이름을 포함 하는 소스 코드 파일에서 사용 하지 않으면는 `Sub Main` 프로시저와 저장 프로시저.dll 파일의 첫 번째 소스 코드 파일에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="c11c3-114">.Exe 또는.dll 확장명 없이 파일 이름을 지정 하면 컴파일러가 자동으로 확장을 추가 대해 지정 된 값에 따라는 `-target` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="c11c3-115">설정 하려면-축소 Visual Studio 통합된 개발 환경에서</span><span class="sxs-lookup"><span data-stu-id="c11c3-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c11c3-116">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c11c3-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c11c3-118">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="c11c3-119">3.  값을 수정 된 **어셈블리 이름** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c11c3-120">예제</span><span class="sxs-lookup"><span data-stu-id="c11c3-120">Example</span></span>  
 <span data-ttu-id="c11c3-121">다음 코드에서는 `T2.vb` 출력 파일이 생성 및 `T2.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c3-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="c11c3-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c11c3-122">See Also</span></span>  
 [<span data-ttu-id="c11c3-123">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c11c3-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c11c3-124">-대상 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c11c3-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c11c3-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="c11c3-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

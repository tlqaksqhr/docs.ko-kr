---
title: "/win32icon | Microsoft 문서"
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: f7d451026438be722d6cb7eecfffe397ccff82ae
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="win32icon"></a><span data-ttu-id="6e8b1-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="6e8b1-102">/win32icon</span></span>
<span data-ttu-id="6e8b1-103">.Ico 파일을 출력 파일에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="6e8b1-104">이.ico 파일에 출력 파일을 나타냅니다 **파일 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8b1-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e8b1-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e8b1-106">인수</span><span class="sxs-lookup"><span data-stu-id="6e8b1-106">Arguments</span></span>  
  
|<span data-ttu-id="6e8b1-107">용어</span><span class="sxs-lookup"><span data-stu-id="6e8b1-107">Term</span></span>|<span data-ttu-id="6e8b1-108">정의</span><span class="sxs-lookup"><span data-stu-id="6e8b1-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="6e8b1-109">출력 파일에 추가 하려면.ico 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="6e8b1-110">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e8b1-111">주의</span><span class="sxs-lookup"><span data-stu-id="6e8b1-111">Remarks</span></span>  
 <span data-ttu-id="6e8b1-112">Microsoft Windows 리소스 컴파일러 (RC)으로.ico 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="6e8b1-113">리소스 컴파일러를 호출 하는 Visual c + + 프로그램을 컴파일하는 경우 .ico 파일.rc 파일에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="6e8b1-114">`/win32icon` 및 `/win32resource` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="6e8b1-115">참조 [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 참조에는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일 또는 [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 연결 하는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span> <span data-ttu-id="6e8b1-116">참조 [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) .res 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="6e8b1-117">Visual Studio IDE에서 /win32icon을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="6e8b1-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="6e8b1-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6e8b1-119">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="6e8b1-120">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="6e8b1-121">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="6e8b1-122">3.  값을 수정 된 **아이콘** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e8b1-123">예제</span><span class="sxs-lookup"><span data-stu-id="6e8b1-123">Example</span></span>  
 <span data-ttu-id="6e8b1-124">다음 코드에서는 `In.vb` .ico 파일을 연결 하 고 `Rf.ico`합니다.</span><span class="sxs-lookup"><span data-stu-id="6e8b1-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e8b1-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e8b1-125">See Also</span></span>  
 <span data-ttu-id="6e8b1-126">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e8b1-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="6e8b1-127"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="6e8b1-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

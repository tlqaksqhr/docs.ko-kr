---
title: "주 / | Microsoft 문서"
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
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
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
ms.openlocfilehash: 61aa78e131ba8903035f630a540f49848f1acd3f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="main"></a><span data-ttu-id="896e4-102">/main</span><span class="sxs-lookup"><span data-stu-id="896e4-102">/main</span></span>
<span data-ttu-id="896e4-103">클래스 또는 포함 된 모듈 지정는 `Sub Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="896e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="896e4-104">Syntax</span></span>  
  
```  
/main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="896e4-105">인수</span><span class="sxs-lookup"><span data-stu-id="896e4-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="896e4-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="896e4-106">Required.</span></span> <span data-ttu-id="896e4-107">클래스 또는 포함 된 모듈의 정규화 된 `Sub Main` 프로그램이 시작 될 때 호출 되는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-107">A full qualification to the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="896e4-108">형태로 제공 될 수 있습니다이 **/main:module** 또는 **/main:namespace.module**합니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-108">This may be in the form **/main:module** or **/main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="896e4-109">주의</span><span class="sxs-lookup"><span data-stu-id="896e4-109">Remarks</span></span>  
 <span data-ttu-id="896e4-110">실행 파일 또는 Windows 실행 프로그램을 만들 때이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="896e4-111">하는 경우는 **주/** 옵션을 생략 하면, 컴파일러는 유효한 공유에 대 한 검색 `Sub Main` 모든 공용 클래스와 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-111">If the **/main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="896e4-112">참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md) 에 대 한 다양 한 형태의 설명은 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="896e4-113">때 `location` 에서 상속 되는 클래스 <xref:System.Windows.Forms.Form>, 컴파일러는 기본 제공 `Main` 클래스가 없는 응용 프로그램을 시작 하는 프로시저 `Main` 절차.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="896e4-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="896e4-114">이렇게 하면 개발 환경에서 만든 명령줄에서 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 <span data-ttu-id="896e4-115">[!code-vb[VbVbalrCompiler #&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="896e4-115">[!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]</span></span>  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="896e4-116">Visual Studio에서 /main을 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="896e4-116">To set /main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="896e4-117">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="896e4-118">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-118">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="896e4-119">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="896e4-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="896e4-120">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-120">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="896e4-121">있는지 확인은 **응용 프로그램 프레임 워크 사용** 확인란을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-121">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="896e4-122">값을 수정 된 **시작 개체** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-122">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="896e4-123">예제</span><span class="sxs-lookup"><span data-stu-id="896e4-123">Example</span></span>  
 <span data-ttu-id="896e4-124">다음 코드에서는 `T2.vb` 및 `T3.vb`로 지정 하 여 하는 `Sub Main` 프로시저에서 찾을 수는 `Test2` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="896e4-124">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="896e4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="896e4-125">See Also</span></span>  
 <span data-ttu-id="896e4-126">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="896e4-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="896e4-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="896e4-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="896e4-128"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="896e4-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="896e4-129"> [NIB: Hello, World Visual Basic 버전](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span><span class="sxs-lookup"><span data-stu-id="896e4-129"> [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c) </span></span>  
<span data-ttu-id="896e4-130"> [Visual Basic의 main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span><span class="sxs-lookup"><span data-stu-id="896e4-130"> [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)</span></span>

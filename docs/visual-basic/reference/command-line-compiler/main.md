---
title: -기본
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51a527dfddd2b78ac1c0559420298a66eb4b63f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652924"
---
# <a name="-main"></a><span data-ttu-id="055b7-102">-기본</span><span class="sxs-lookup"><span data-stu-id="055b7-102">-main</span></span>
<span data-ttu-id="055b7-103">`Sub Main` 프로시저가 포함된 클래스 또는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="055b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="055b7-104">Syntax</span></span>  
  
```  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="055b7-105">인수</span><span class="sxs-lookup"><span data-stu-id="055b7-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="055b7-106">필수.</span><span class="sxs-lookup"><span data-stu-id="055b7-106">Required.</span></span> <span data-ttu-id="055b7-107">클래스 또는 포함 된 모듈의 이름에서 `Sub Main` 프로그램이 시작 될 때 호출 되는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="055b7-108">형태로 수도 **-main: module** 또는 **-main:namespace.module**합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="055b7-109">설명</span><span class="sxs-lookup"><span data-stu-id="055b7-109">Remarks</span></span>  
 <span data-ttu-id="055b7-110">실행 파일이 나 Windows 실행 프로그램을 만들 때이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="055b7-111">경우는 **-주** 옵션을 생략 하면, 컴파일러는 유효한 공유에 대 한 검색 `Sub Main` 모든 공용 클래스 및 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="055b7-112">참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md) 에 대 한 다양 한 형태의 설명은 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="055b7-113">때 `location` 에서 상속 되는 클래스 <xref:System.Windows.Forms.Form>, 컴파일러는 기본 제공 `Main` 클래스에 없는 경우 응용 프로그램을 시작 하는 프로시저 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="055b7-114">따라서 개발 환경에서 만든 명령줄에서 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="055b7-115">Visual Studio 통합된 개발 환경에서 기본 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="055b7-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="055b7-116">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="055b7-117">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-117">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="055b7-118">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-118">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="055b7-119">있는지 확인은 **응용 프로그램 프레임 워크 사용** 확인란을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="055b7-120">값을 수정 된 **시작 개체** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="055b7-121">예제</span><span class="sxs-lookup"><span data-stu-id="055b7-121">Example</span></span>  
 <span data-ttu-id="055b7-122">다음 코드에서는 `T2.vb` 및 `T3.vb`로 지정 하 여 하는 `Sub Main` 프로시저에 나타나게 됩니다는 `Test2` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="055b7-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="055b7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="055b7-123">See Also</span></span>  
 [<span data-ttu-id="055b7-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="055b7-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="055b7-125">-대상 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="055b7-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="055b7-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="055b7-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="055b7-127">Visual Basic의 main 프로시저</span><span class="sxs-lookup"><span data-stu-id="055b7-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)

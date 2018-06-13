---
title: -imports (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 330a5e6821c9c76f3503a35a5a5eabf24c686b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652092"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="3993a-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3993a-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="3993a-103">지정된 된 어셈블리에서 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3993a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3993a-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="3993a-105">인수</span><span class="sxs-lookup"><span data-stu-id="3993a-105">Arguments</span></span>  
  
|<span data-ttu-id="3993a-106">용어</span><span class="sxs-lookup"><span data-stu-id="3993a-106">Term</span></span>|<span data-ttu-id="3993a-107">정의</span><span class="sxs-lookup"><span data-stu-id="3993a-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="3993a-108">필수.</span><span class="sxs-lookup"><span data-stu-id="3993a-108">Required.</span></span> <span data-ttu-id="3993a-109">가져올 네임 스페이스의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3993a-110">설명</span><span class="sxs-lookup"><span data-stu-id="3993a-110">Remarks</span></span>  
 <span data-ttu-id="3993a-111">`-imports` 옵션 현재 참조 되는 어셈블리 또는 소스 파일의 집합 내에 정의 된 모든 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="3993a-112">지정 된 네임 스페이스의 멤버 `-imports` 컴파일할 때 모든 소스 코드 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="3993a-113">사용 하 여는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 단일 소스 코드 파일에서 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="3993a-114">설정 하려면 Visual Studio 통합된 개발 환경에서 가져오는 /</span><span class="sxs-lookup"><span data-stu-id="3993a-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="3993a-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3993a-116">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3993a-117">2.  **참조** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="3993a-118">3.  네임 스페이스 이름 옆의 상자에 입력 된 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="3993a-119">4.  클릭는 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3993a-120">예제</span><span class="sxs-lookup"><span data-stu-id="3993a-120">Example</span></span>  
 <span data-ttu-id="3993a-121">다음 코드를 컴파일한 경우 `/imports:system.globalization` 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="3993a-122">없으면 컴파일이 성공 있어야 중 하나는 `Imports System.Globalization` 문은 소스 코드 파일의 시작 부분에 포함 될 또는 속성으로 정규화 되어야 `System.Globalization.CultureInfo.CurrentCulture.Name`합니다.</span><span class="sxs-lookup"><span data-stu-id="3993a-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3993a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3993a-123">See Also</span></span>  
 [<span data-ttu-id="3993a-124">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3993a-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3993a-125">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="3993a-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="3993a-126">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="3993a-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

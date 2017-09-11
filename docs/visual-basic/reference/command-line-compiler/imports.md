---
title: "/imports (Visual Basic) | Microsoft 문서"
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
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
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
ms.openlocfilehash: e994e94dcc3cd00f868b6ae90e4c019eb5b9e2eb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="imports-visual-basic"></a><span data-ttu-id="8a400-102">/imports(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a400-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="8a400-103">지정된 된 어셈블리에서 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a400-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a400-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a400-105">인수</span><span class="sxs-lookup"><span data-stu-id="8a400-105">Arguments</span></span>  
  
|<span data-ttu-id="8a400-106">용어</span><span class="sxs-lookup"><span data-stu-id="8a400-106">Term</span></span>|<span data-ttu-id="8a400-107">정의</span><span class="sxs-lookup"><span data-stu-id="8a400-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="8a400-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a400-108">Required.</span></span> <span data-ttu-id="8a400-109">가져올 네임 스페이스의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a400-110">주의</span><span class="sxs-lookup"><span data-stu-id="8a400-110">Remarks</span></span>  
 <span data-ttu-id="8a400-111">`/imports` 옵션 현재 소스 파일 또는 참조 된 어셈블리에서 집합 내에 정의 된 모든 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="8a400-112">지정 된 네임 스페이스의 멤버 `/imports` 컴파일할 때 모든 소스 코드 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="8a400-113">사용 하 여는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 단일 소스 코드 파일의 네임 스페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="8a400-114">설정 하려면 Visual Studio 통합된 개발 환경에서 /imports</span><span class="sxs-lookup"><span data-stu-id="8a400-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8a400-115">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8a400-116">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="8a400-117">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a400-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="8a400-118">2.  클릭 하 고 **참조** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="8a400-119">3.  네임 스페이스 이름 옆에 있는 상자에 입력 된 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="8a400-120">4.  클릭 하 고 **사용자 가져오기 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a400-121">예제</span><span class="sxs-lookup"><span data-stu-id="8a400-121">Example</span></span>  
 <span data-ttu-id="8a400-122">다음 코드를 컴파일한 경우 `/imports:system` 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a400-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 <span data-ttu-id="8a400-123">[!code-vb[VbVbalrCompiler #&21;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8a400-123">[!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a400-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a400-124">See Also</span></span>  
 <span data-ttu-id="8a400-125">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a400-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8a400-126"> [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8a400-126"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="8a400-127"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="8a400-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

---
title: "/rootnamespace | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
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
ms.openlocfilehash: 9a7a26407e981d3aea58d970d88bf25025e6bba6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="rootnamespace"></a><span data-ttu-id="ba030-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="ba030-102">/rootnamespace</span></span>
<span data-ttu-id="ba030-103">모든 형식 선언에 대한 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba030-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba030-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba030-105">인수</span><span class="sxs-lookup"><span data-stu-id="ba030-105">Arguments</span></span>  
  
|<span data-ttu-id="ba030-106">용어</span><span class="sxs-lookup"><span data-stu-id="ba030-106">Term</span></span>|<span data-ttu-id="ba030-107">정의</span><span class="sxs-lookup"><span data-stu-id="ba030-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="ba030-108">현재 프로젝트에 대 한 모든 형식 선언을 포함할를 네임 스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba030-109">설명</span><span class="sxs-lookup"><span data-stu-id="ba030-109">Remarks</span></span>  
 <span data-ttu-id="ba030-110">사용 하 여 Visual Studio 통합된 개발 환경에서 만든 프로젝트를 컴파일하려면 Visual Studio 실행 파일 (Devenv.exe)를 사용 하는 경우 `/rootnamespace` 의 값을 지정 하는 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>속성.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="ba030-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="ba030-111">참조 [Devenv 명령줄 스위치](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) 에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-111">See [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="ba030-112">공용 언어 런타임 MSIL 디스어셈블러를 사용 하 여 (I`ldasm.exe`) 출력 파일에 네임 스페이스 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-112">Use the common language runtime MSIL Disassembler (I`ldasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="ba030-113">Visual Studio에서 /rootnamespace를 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="ba030-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="ba030-114">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ba030-115">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ba030-116">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba030-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="ba030-117">2.  **응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="ba030-118">3.  값을 수정 된 **루트 Namespace** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ba030-119">예제</span><span class="sxs-lookup"><span data-stu-id="ba030-119">Example</span></span>  
 <span data-ttu-id="ba030-120">다음 코드에서는 `In.vb` 네임 스페이스의 모든 형식 선언을 포함 하 고 `mynamespace`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba030-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba030-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba030-121">See Also</span></span>  
 <span data-ttu-id="ba030-122">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba030-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ba030-123"> [Ildasm.exe (IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1) </span><span class="sxs-lookup"><span data-stu-id="ba030-123"> [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span></span>  
<span data-ttu-id="ba030-124"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="ba030-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

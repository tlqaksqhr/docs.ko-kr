---
title: "/delaysign | Microsoft 문서"
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
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
ms.openlocfilehash: bcc819e08ca7731d91dc77dc831060bcf00a4425
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="delaysign"></a><span data-ttu-id="08ede-102">T:System.Reflection.AssemblyDelaySignAttribute</span><span class="sxs-lookup"><span data-stu-id="08ede-102">/delaysign</span></span>
<span data-ttu-id="08ede-103">어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ede-104">구문</span><span class="sxs-lookup"><span data-stu-id="08ede-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="08ede-105">인수</span><span class="sxs-lookup"><span data-stu-id="08ede-105">Arguments</span></span>  
 <span data-ttu-id="08ede-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="08ede-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="08ede-107">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="08ede-107">Optional.</span></span> <span data-ttu-id="08ede-108">어셈블리에 완전히 서명하려면 `/delaysign-`를 사용하고</span><span class="sxs-lookup"><span data-stu-id="08ede-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="08ede-109">사용 하 여 `/delaysign+` 부호 있는 해시에 대 한 어셈블리 및 예약 공간에 공개 키를 저장 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="08ede-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="08ede-110">기본값은 `/delaysign-`입니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08ede-111">주의</span><span class="sxs-lookup"><span data-stu-id="08ede-111">Remarks</span></span>  
 <span data-ttu-id="08ede-112">`/delaysign` 와 사용 하지 않는 경우 옵션은 효과가 없습니다 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 또는 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="08ede-113">완전히 서명 된 어셈블리를 요청 하는 경우 컴파일러는 매니페스트 (어셈블리 메타 데이터)를 포함 하 고 개인 키로 해당 해시에 서명 하는 파일을 해시 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="08ede-114">결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="08ede-115">어셈블리 서명이 연기 되 면 컴파일러 계산 및 나중에 서명을 추가할 수 있도록 파일에 서명을 하지만 예약 공간을 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="08ede-116">사용 하 여 예를 들어 `/delaysign+`, 개발자는 조직에서 테스터가 어셈블리를 전역 어셈블리 캐시에 등록 하 고 사용할 수 있는 어셈블리의 서명 되지 않은 테스트 버전을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="08ede-117">어셈블리 작업이 완료 되 면 회사의 개인 키를 담당 하는 사용자 어셈블리에 완전히 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="08ede-118">이 작업의 공개, 모든 개발자 들이 어셈블리에서 작동 하면서 회사의 개인 키를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="08ede-119">참조 [Creating and using strong-named Assemblies](https://msdn.microsoft.com/library/xwb8f617) 어셈블리 서명에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="08ede-120">Visual Studio에서 /delaysign을 설정 하려면 통합 개발 환경</span><span class="sxs-lookup"><span data-stu-id="08ede-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="08ede-121">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="08ede-122">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="08ede-123">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08ede-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="08ede-124">클릭 하 고 **서명** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="08ede-125">값을 설정 된 **서명만 연기** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="08ede-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ede-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08ede-126">See Also</span></span>  
 <span data-ttu-id="08ede-127">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="08ede-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="08ede-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="08ede-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="08ede-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span><span class="sxs-lookup"><span data-stu-id="08ede-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span></span>  
<span data-ttu-id="08ede-130"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="08ede-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

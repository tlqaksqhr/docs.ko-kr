---
title: "어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e88d28ef787eb57b71d94f4ee51c09e9751dbff
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="5089c-102">어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="5089c-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="5089c-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="5089c-104">링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="5089c-105">지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="5089c-106">어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="5089c-107">어셈블리 서명을 연기하려면 **서명만 연기** 확인란을 선택하고 공개 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="5089c-108">어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="5089c-109">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5089c-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="5089c-110">**오류 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="5089c-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5089c-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="5089c-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="5089c-112">따옴표 붙은 오류 메시지를 검사 하 고 항목을 검토 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="5089c-113">오류 AL1019 추가 설명과 권장 사항을</span><span class="sxs-lookup"><span data-stu-id="5089c-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="5089c-114">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5089c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5089c-115">See Also</span></span>  
 [<span data-ttu-id="5089c-116">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="5089c-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="5089c-117">프로젝트 디자이너, 서명 페이지</span><span class="sxs-lookup"><span data-stu-id="5089c-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="5089c-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5089c-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 [<span data-ttu-id="5089c-119">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="5089c-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

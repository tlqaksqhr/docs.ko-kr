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
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="e3dbc-102">어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="e3dbc-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="e3dbc-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="e3dbc-104">링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="e3dbc-105">지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="e3dbc-106">어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="e3dbc-107">어셈블리 서명을 연기하려면 **서명만 연기** 확인란을 선택하고 공개 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="e3dbc-108">어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="e3dbc-109">자세한 내용은 참조 [하는 방법: 어셈블리 서명 (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="e3dbc-110">**오류 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="e3dbc-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3dbc-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e3dbc-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="e3dbc-112">따옴표 붙은 오류 메시지를 검사 하 고 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) AL1019 오류에 대 한 자세한 설명과 권고</span><span class="sxs-lookup"><span data-stu-id="e3dbc-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="e3dbc-113">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e3dbc-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3dbc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3dbc-114">See Also</span></span>  
 [<span data-ttu-id="e3dbc-115">방법: 어셈블리 서명(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e3dbc-115">How to: Sign an Assembly (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [<span data-ttu-id="e3dbc-116">프로젝트 디자이너, 서명 페이지</span><span class="sxs-lookup"><span data-stu-id="e3dbc-116">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 [<span data-ttu-id="e3dbc-117">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="e3dbc-117">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="e3dbc-118">Al.exe 도구 오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="e3dbc-118">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="e3dbc-119">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="e3dbc-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

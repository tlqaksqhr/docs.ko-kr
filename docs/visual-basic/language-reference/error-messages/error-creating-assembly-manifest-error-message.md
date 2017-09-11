---
title: "어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
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
ms.openlocfilehash: 12e08feff09e901839c4e282d32a0a4e54e12576
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="8c3b6-102">어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="8c3b6-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="8c3b6-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="8c3b6-104">링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="8c3b6-105">지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="8c3b6-106">어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="8c3b6-107">어셈블리 서명을 연기을을 선택 해야는 **서명만 연기** 확인란을 선택 하 고 공개 키 정보에 대 한 정보가 포함 된 유효한 키 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="8c3b6-108">어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="8c3b6-109">자세한 내용은 참조 [하는 방법: 어셈블리 (Visual Studio)에 서명](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="8c3b6-110">**오류 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="8c3b6-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c3b6-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8c3b6-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="8c3b6-112">따옴표로 묶인된 오류 메시지를 검사 하는 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) AL1019 오류에 대 한 추가 설명과 권장</span><span class="sxs-lookup"><span data-stu-id="8c3b6-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="8c3b6-113">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8c3b6-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3b6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c3b6-114">See Also</span></span>  
 <span data-ttu-id="8c3b6-115">[방법: 어셈블리 서명(Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span><span class="sxs-lookup"><span data-stu-id="8c3b6-115">[How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span></span>  
<span data-ttu-id="8c3b6-116"> [프로젝트 디자이너, 서명 페이지](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span><span class="sxs-lookup"><span data-stu-id="8c3b6-116"> [Signing Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span></span>  
<span data-ttu-id="8c3b6-117"> [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="8c3b6-117"> [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="8c3b6-118"> [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="8c3b6-118"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="8c3b6-119"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="8c3b6-119"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

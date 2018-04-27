---
title: '어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59288ba7b4cec34cd2266d66aa931e92598e819a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="ce7e7-102">어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="ce7e7-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="ce7e7-103">Visual Basic 컴파일러 링커 어셈블리 만들기의 내보내기 단계에서 오류가 보고 어셈블리 링커 (Al.exe, Alink 라고도 함)는 매니페스트를 사용해 어셈블리를 생성 하려면를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="ce7e7-104">**오류 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="ce7e7-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce7e7-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ce7e7-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="ce7e7-106">따옴표 붙은 오류 메시지를 검사 하 고 항목을 검토 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="ce7e7-107">추가 설명과 권장 사항을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="ce7e7-108">어셈블리 중 하나를 사용 하 여 수동으로 서명을 시도 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 또는 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="ce7e7-109">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="ce7e7-110">어셈블리에 수동으로 서명하려면</span><span class="sxs-lookup"><span data-stu-id="ce7e7-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="ce7e7-111">[Sn.exe (강력한 이름 도구)]를 사용 하 여[Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)) 공개/개인 키 쌍 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="ce7e7-112">이 파일의 확장명은 .snk입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="ce7e7-113">프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="ce7e7-114">Windows에서 **시작** 메뉴에서 **프로그램**, 가리킨 **Microsoft Visual Studio 2008**, 가리킨 **Visual Studio Tools**, 및 클릭 **Visual Studio 2008 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="ce7e7-115">어셈블리 래퍼를 배치할 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="ce7e7-116">다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="ce7e7-117">입력할 수 있는 코드의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="ce7e7-118">경로나 파일에 공백이 있으면 큰따옴표(")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="ce7e7-119">Visual Studio에서 방금 만든 파일에 대 한.NET 어셈블리 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7e7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce7e7-120">See Also</span></span>  
 
 <span data-ttu-id="ce7e7-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e7-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="ce7e7-122">[Sn.exe (강력한 이름 도구)] [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="ce7e7-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="ce7e7-123">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="ce7e7-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="ce7e7-124">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="ce7e7-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

---
title: "어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords: BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dcf3d4bec379faa5783ca17847b91f9739df598
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="a4450-102">어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="a4450-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="a4450-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 어셈블리 생성의 내보내기 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="a4450-104">**오류 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="a4450-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a4450-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a4450-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="a4450-106">따옴표 붙은 오류 메시지를 파악한 다음 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 항목에서 추가 설명과 권장 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="a4450-107">어셈블리 중 하나를 사용 하 여 수동으로 서명을 시도 [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) 또는 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="a4450-108">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="a4450-109">어셈블리에 수동으로 서명하려면</span><span class="sxs-lookup"><span data-stu-id="a4450-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="a4450-110">사용 하 여는 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23) 공개/개인 키 쌍 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="a4450-111">이 파일의 확장명은 .snk입니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="a4450-112">프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="a4450-113">Windows에서 **시작** 메뉴에서 **프로그램**, 가리킨 **Microsoft Visual Studio 2008**, 가리킨 **Visual Studio Tools**, 및 클릭 **Visual Studio 2008 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="a4450-114">어셈블리 래퍼를 배치할 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="a4450-115">다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="a4450-116">입력할 수 있는 코드의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="a4450-117">경로나 파일에 공백이 있으면 큰따옴표(")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="a4450-118">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]에서 방금 만든 파일에 대한 .NET 어셈블리 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4450-118">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4450-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4450-119">See Also</span></span>  
 [<span data-ttu-id="a4450-120">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="a4450-120">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="a4450-121">Al.exe 도구 오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="a4450-121">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="a4450-122">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="a4450-122">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 [<span data-ttu-id="a4450-123">방법: 공개/개인 키 쌍 만들기</span><span class="sxs-lookup"><span data-stu-id="a4450-123">How to: Create a Public-Private Key Pair</span></span>](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)  
 [<span data-ttu-id="a4450-124">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="a4450-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

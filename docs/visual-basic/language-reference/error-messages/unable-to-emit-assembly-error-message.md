---
title: "어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
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
ms.openlocfilehash: d15981a1a2fb31ba377066fa421f5a9979d47a12
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="78521-102">어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="78521-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="78521-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 어셈블리 생성의 내보내기 단계에서 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="78521-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="78521-104">**오류 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="78521-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78521-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="78521-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="78521-106">따옴표로 묶인된 오류 메시지를 검사 하는 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 추가 설명과 권장 사항을 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="78521-107">어셈블리 중 하나를 사용 하 여 수동으로 서명을 시도 [Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) 또는 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="78521-108">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="78521-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="78521-109">어셈블리에 수동으로 서명하려면</span><span class="sxs-lookup"><span data-stu-id="78521-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="78521-110">사용 된 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23) 공개/개인 키 쌍 파일을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="78521-111">이 파일의 확장명은 .snk입니다.</span><span class="sxs-lookup"><span data-stu-id="78521-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="78521-112">프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="78521-113">Windows에서 **시작** 메뉴에서 **프로그램**, 가리킨 **Microsoft Visual Studio 2008**, 가리킨 **Visual Studio Tools**를 클릭 하 고 **Visual Studio 2008 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="78521-114">어셈블리 래퍼를 배치할 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="78521-115">다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="78521-116">입력할 수 있는 코드의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="78521-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="78521-117">경로나 파일에 공백이 있으면 큰따옴표(")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="78521-118">[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]에서 방금 만든 파일에 대한 .NET 어셈블리 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="78521-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78521-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78521-119">See Also</span></span>  
 <span data-ttu-id="78521-120">[Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="78521-120">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="78521-121"> [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="78521-121"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="78521-122"> [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="78521-122"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="78521-123"> [방법: 공개/개인 키 쌍 만들기](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span><span class="sxs-lookup"><span data-stu-id="78521-123"> [How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span></span>  
<span data-ttu-id="78521-124"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="78521-124"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

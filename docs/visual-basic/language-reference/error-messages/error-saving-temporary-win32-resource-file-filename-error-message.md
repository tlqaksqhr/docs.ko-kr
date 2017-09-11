---
title: "임시 Win32 리소스 파일을 저장할 수 없습니다. &quot;&lt;filename&gt;&quot;: &lt;오류 메시지&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30137
- vbc30137
dev_langs:
- VB
helpviewer_keywords:
- BC30137
ms.assetid: 61c23f48-0e06-42fc-be00-5598053c86dd
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
ms.openlocfilehash: ce0090782a930a36b65abf201baf56dc3c271a46
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="error-saving-temporary-win32-resource-file-39ltfilenamegt39-lterror-messagegt"></a><span data-ttu-id="f75c7-102">임시 Win32 리소스 파일을 저장할 수 없습니다. '&lt;filename&gt;': &lt;오류 메시지&gt;</span><span class="sxs-lookup"><span data-stu-id="f75c7-102">Error saving temporary Win32 resource file &#39;&lt;filename&gt;&#39;: &lt;error message&gt;</span></span>
<span data-ttu-id="f75c7-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커(Al.exe, Alink라고도 함)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f75c7-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="f75c7-104">링커가 메모리 내 리소스를 쓰는 데 사용할 파일 이름을 가져오는 동안 오류를 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="f75c7-104">The linker reported an error obtaining a file name for use in writing an in-memory resource.</span></span>  
  
 <span data-ttu-id="f75c7-105">**오류 ID:** BC30137</span><span class="sxs-lookup"><span data-stu-id="f75c7-105">**Error ID:** BC30137</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f75c7-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f75c7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f75c7-107">따옴표로 묶인된 오류 메시지를 검사 하는 항목을 검토 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 추가 설명과 권장 사항을 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f75c7-107">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="f75c7-108">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f75c7-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75c7-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f75c7-109">See Also</span></span>  
 <span data-ttu-id="f75c7-110">[Al.exe (어셈블리 링커)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="f75c7-110">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="f75c7-111"> [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="f75c7-111"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="f75c7-112"> [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="f75c7-112"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

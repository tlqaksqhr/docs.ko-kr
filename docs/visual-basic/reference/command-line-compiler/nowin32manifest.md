---
title: "/nowin32manifest (Visual Basic) | Microsoft 문서"
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
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
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
ms.openlocfilehash: 975711c9ee2e56b3c3c33611dd56eb6dc6082471
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nowin32manifest-visual-basic"></a><span data-ttu-id="f9c36-102">/nowin32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9c36-102">/nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="f9c36-103">실행 파일에 응용 프로그램 매니페스트를 포함하지 않도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c36-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9c36-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9c36-104">Syntax</span></span>  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="f9c36-105">주의</span><span class="sxs-lookup"><span data-stu-id="f9c36-105">Remarks</span></span>  
 <span data-ttu-id="f9c36-106">이 옵션을 사용 하는 경우 응용 프로그램 매니페스트를 Win32 리소스 파일에서 또는 이후 빌드 단계를 제공 하지 않을 경우 응용 프로그램이 Windows Vista에서 가상화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c36-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="f9c36-107">가상화에 대 한 자세한 내용은 참조 [Windows Vista의 ClickOnce 배포](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c36-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="f9c36-108">매니페스트 만들기에 대 한 자세한 내용은 참조 [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c36-108">For more information about manifest creation, see [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c36-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9c36-109">See Also</span></span>  
 <span data-ttu-id="f9c36-110">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9c36-110">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f9c36-111"> [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f9c36-111"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>

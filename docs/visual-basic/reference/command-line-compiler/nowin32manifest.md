---
title: /nowin32manifest(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce8e963e88a8080424435caea8b15ba288ae9c28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nowin32manifest-visual-basic"></a><span data-ttu-id="c7607-102">/nowin32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7607-102">/nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="c7607-103">실행 파일에 응용 프로그램 매니페스트를 포함하지 않도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="c7607-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7607-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7607-104">Syntax</span></span>  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="c7607-105">주의</span><span class="sxs-lookup"><span data-stu-id="c7607-105">Remarks</span></span>  
 <span data-ttu-id="c7607-106">이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 응용 프로그램 매니페스트를 제공하지 않으면 Windows Vista에서 응용 프로그램에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7607-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="c7607-107">가상화에 대 한 자세한 내용은 참조 [Windows Vista의 ClickOnce 배포](/visualstudio/deployment/clickonce-deployment-on-windows-vista)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7607-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="c7607-108">매니페스트 만들기에 대 한 자세한 내용은 참조 [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7607-108">For more information about manifest creation, see [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7607-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7607-109">See Also</span></span>  
 [<span data-ttu-id="c7607-110">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c7607-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c7607-111">프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7607-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)

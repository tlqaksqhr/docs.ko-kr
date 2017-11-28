---
title: "응용 프로그램 폼 액세스(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b029ce984f9cef540087181a83070b0c8aa8132
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="953ce-102">응용 프로그램 폼 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="953ce-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="953ce-103">`My.Forms` 개체는 응용 프로그램 프로젝트에 선언된 각 Windows Form의 인스턴스에 액세스하는 간편한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="953ce-104">`My.Application` 개체의 속성을 사용하여 응용 프로그램의 시작 화면 및 기본 폼에 액세스하고 응용 프로그램의 열려 있는 폼 목록을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="953ce-105">작업</span><span class="sxs-lookup"><span data-stu-id="953ce-105">Tasks</span></span>  
 <span data-ttu-id="953ce-106">다음 표에는 응용 프로그램의 양식에 액세스하는 방법을 보여 주는 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="953ce-107">후</span><span class="sxs-lookup"><span data-stu-id="953ce-107">To</span></span>|<span data-ttu-id="953ce-108">참조</span><span class="sxs-lookup"><span data-stu-id="953ce-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="953ce-109">응용 프로그램의 다른 폼에서 한 폼에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="953ce-110">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="953ce-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="953ce-111">응용 프로그램의 열려 있는 모든 폼의 제목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="953ce-112">응용 프로그램이 시작될 때 시작 화면을 상태 정보로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="953ce-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="953ce-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="953ce-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>  
 [<span data-ttu-id="953ce-114">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="953ce-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)

---
title: "사용자 데이터 액세스(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- domain names [Visual Basic], retrieving
- data [Visual Basic], accessing user data
- My.User object [Visual Basic], tasks
- user data [Visual Basic], domain
- user names [Visual Basic], retrieving
- user data [Visual Basic], accessing
- login names [Visual Basic]
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92c0b97059896e86d54069b637c9956cac9d10e8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-user-data-visual-basic"></a><span data-ttu-id="36271-102">사용자 데이터 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36271-102">Accessing User Data (Visual Basic)</span></span>
<span data-ttu-id="36271-103">이 섹션에는 `My.User` 개체 및 이 개체로 수행할 수 있는 작업을 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36271-103">This section contains topics dealing with the `My.User` object and tasks that you can accomplish with it.</span></span>  
  
 <span data-ttu-id="36271-104">`My.User` 개체는 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하는 개체를 반환하여 로그온한 사용자 정보에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36271-104">The `My.User` object provides access to information about the logged-on user by returning an object that implements the <xref:System.Security.Principal.IPrincipal> interface.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="36271-105">작업</span><span class="sxs-lookup"><span data-stu-id="36271-105">Tasks</span></span>  
  
|<span data-ttu-id="36271-106">후</span><span class="sxs-lookup"><span data-stu-id="36271-106">To</span></span>|<span data-ttu-id="36271-107">참조</span><span class="sxs-lookup"><span data-stu-id="36271-107">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="36271-108">사용자의 로그인 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="36271-108">Get the user's login name</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|<span data-ttu-id="36271-109">응용 프로그램이 Windows 인증을 사용하는 경우 사용자의 도메인 이름 가져오기</span><span class="sxs-lookup"><span data-stu-id="36271-109">Get the user's domain name, if the application uses Windows authentication</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|<span data-ttu-id="36271-110">사용자의 역할 확인</span><span class="sxs-lookup"><span data-stu-id="36271-110">Determine the user's role</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="36271-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36271-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>

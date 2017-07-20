---
title: "사용자 데이터 액세스(Visual Basic) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- domain names, retrieving
- data [Visual Basic], accessing user data
- My.User object, tasks
- user data, domain
- user names, retrieving
- user data, accessing
- login names
- examples [Visual Basic], accessing user data
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ef4607074e1e89bcafdd4262a25070693948f8ff
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="accessing-user-data-visual-basic"></a>사용자 데이터 액세스(Visual Basic)
이 섹션에는 `My.User` 개체 및 이 개체로 수행할 수 있는 작업을 설명하는 항목이 포함되어 있습니다.  
  
 `My.User` 개체는 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하는 개체를 반환하여 로그온한 사용자 정보에 대한 액세스를 제공합니다.  
  
## <a name="tasks"></a>작업  
  
|후|참조|  
|--------|---------|  
|사용자의 로그인 이름 가져오기|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|응용 프로그램이 Windows 인증을 사용하는 경우 사용자의 도메인 이름 가져오기|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|사용자의 역할 확인|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>

---
title: "Accessing User Data (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "domain names, retrieving"
  - "data [Visual Basic], accessing user data"
  - "My.User object, tasks"
  - "user data, domain"
  - "user names, retrieving"
  - "user data, accessing"
  - "login names"
  - "examples [Visual Basic], accessing user data"
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Accessing User Data (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 단원에는 `My.User` 개체와 이 개체로 수행할 수 있는 작업을 다루는 항목이 포함되어 있습니다.  
  
 `My.User` 개체를 사용하면 <xref:System.Security.Principal.IPrincipal> 인터페이스를 구현하는 개체를 반환함으로써 로그온된 사용자에 대한 정보에 액세스할 수 있습니다.  
  
## 작업  
  
|To|참조|  
|--------|--------|  
|사용자의 로그인 이름 가져오기|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|응용 프로그램에서 Windows 인증을 사용하는 경우 사용자의 도메인 이름 가져오기|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|사용자의 역할 확인|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>
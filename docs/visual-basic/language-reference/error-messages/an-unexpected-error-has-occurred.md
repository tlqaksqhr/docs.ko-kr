---
title: "An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_CantGetMemoryMappedFile"
dev_langs: 
  - "VB"
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

응용 프로그램이 필요한 운영 체제 리소스를 가져올 수 없습니다.  이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.  
  
-   응용 프로그램에 명명된 운영 체제 개체를 만들 수 있는 권한이 없습니다.  
  
-   공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 없습니다.  
  
-   응용 프로그램이 운영 체제 개체에 액세스해야 하는데 다른 프로세스에서 해당 개체를 사용하고 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  응용 프로그램에 명명된 운영 체제 개체를 만들 수 있는 권한이 있는지 확인합니다.  
  
2.  공용 언어 런타임에 메모리 매핑된 파일을 만들 수 있는 권한이 있는지 확인합니다.  
  
3.  컴퓨터를 다시 시작하여 원래 인스턴스 응용 프로그램에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.  
  
4.  오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 문의합니다.  
  
## 참고 항목  
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [디버거 기본 사항](/visual-studio/debugger/debugger-basics)   
 [의견 보내기](/visual-studio/ide/talk-to-us)
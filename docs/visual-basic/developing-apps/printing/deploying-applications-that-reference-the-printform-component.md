---
title: "Deploying Applications That Reference the PrintForm Component (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "PrintForm component [Visual Basic], deploying"
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Deploying Applications That Reference the PrintForm Component (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 참조하는 응용 프로그램을 배포하려면 대상 컴퓨터에 구성 요소를 설치해야 합니다.  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
## PrintForm을 필수 조건으로 설치  
 응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다. 필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 개발 컴퓨터에 설치될 때 Microsoft Visual Basic Power Packs 부트스트래퍼 패키지가 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 부트스트래퍼 디렉터리에 추가됩니다. 이 패키지는 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 또는 Windows Installer 배포에 대한 필수 조건을 추가하는 절차를 수행할 때 사용할 수 있습니다.  
  
 기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다. 또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.  
  
> [!NOTE]
>  부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다.[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 응용 프로그램의 경우 이는 응용 프로그램에서 지정된 보안 수준과 관계없이 응용 프로그램을 설치할 관리 권한이 사용자에게 필요함을 의미합니다. 응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.  
  
 설치하는 동안 대상 컴퓨터에 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소가 없을 경우 해당 구성 요소를 설치할지 묻는 메시지가 사용자에게 표시됩니다.  
  
 부트스트래핑 대신 Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용하여 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소를 미리 배포할 수 있습니다.  
  
## 참고 항목  
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [빌드되지 않음: 배포 전략 선택](http://msdn.microsoft.com/ko-kr/ecd632d8-063c-4028-b785-81bba045107b)   
 [PrintForm Component](../../../visual-basic/developing-apps/printing/printform-component.md)